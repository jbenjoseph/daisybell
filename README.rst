Instructions to reproduce masking experiment
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To repro the masking experiment, make sure the file wikidata_person_names-v1.csv.gz is in
your current working directory.

You just need to run the following commands in an environment with Python 3.8 or above.

```
    python setup.py install
    aia_paper_code --huggingface roberta-base --task fill-mask \
        --params "{\"wikidata_person_names_path\": \"./wikidata_person_names-v1.csv.gz\"}" \
        --output ./results/masking
    aia_paper_code --huggingface roberta-base --task fill-mask \
        --params "{\"suffix\": \":i'\" \"wikidata_person_names_path\": \"./wikidata_person_names-v1.csv.gz\"}" \
        --output ./results/masking-with-exploit
    pip uninstall aia_paper_code


The results in CSV format will be in those directories.