# Converting huggingface transformers models to spacy-transformers models

[spacy-transformers](https://github.com/explosion/spacy-transformers/tree/v0.6.2) can load any [huggingface transformers](https://github.com/huggingface/transformers/tree/v2.8.0) model because spacy-transformers is a wrapper around it, but you need an [extra conversion step](https://github.com/explosion/spacy-transformers/issues/206#issuecomment-651285379) to load this model in spacy.

This is the old way of doing it, before spacy 3.0.0, only works for `spacy-transformers==0.6.2` and `transformers>=2.4.0,<2.9.0`

For example, you want to load https://huggingface.co/nlpaueb/legal-bert-small-uncased

```
mkdir legal-bert-small-uncased
python init_model.py -n "nlpaueb/legal-bert-small-uncased" -l en legal-bert-small-uncased
```

```
ℹ Creating model for 'nlpaueb/legal-bert-small-uncased' (en)
Downloading: 100%|███████████| 141M/141M [00:14<00:00, 9.53MB/s]
✔ Initialized the model pipeline
✔ Saved 'nlpaueb/legal-bert-small-uncased' (en)
Pipeline: ['sentencizer', 'trf_wordpiecer', 'trf_tok2vec']
Location: legal-bert-small-uncased
✔ Model loads!
```
