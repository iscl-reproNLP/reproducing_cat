# cat🐈

This is the repository for the ACL 2020 paper embarrassingly simple aspect extraction.
In this work, we extract aspects from restaurant reviews using a new form of attention that uses RBF kernels.

## Usage

If you want to apply cat to your data, you need a couple of things.

1. An aspect set, i.e., the set of labels you would like to predict
2. A set of _in-domain_ word embeddings. This is really important, as we show in the paper.
3. A set of aspect terms which you think correspond to the aspects you want to extract.
4. A set of instances for which you want to predict the labels you define in step 1. We expect these to be tokenized, one sentence per line.

If you have all these things, you can simply look at `cat.py` and replace the paths in this file with the paths to the appropriate files/instances.
cat🐈 has two hyperparameters: the gamma of the kernel, and the aspect words, these also need to be set by hand.

If you do not have access to pre-trained embeddings or aspect words, you will need a parser to extract either nouns or tree fragments.
For maximum portability, we adopt the CoNLLu format, a format that many parsers output.
If you use [spacy](https://spacy.io/), you can use the [spacyconllu](https://github.com/andreasvc/spacyconllu) script.

To obtain the nouns and  run `train_embeddings.py`, and replace the paths with the appropriate paths to your CoNLLu parsed file.
This will train your embeddings and extract the aspect words, which you will need in the next step.

## Reproducing the experiments

You can reproduce the experiments by obtaining the data, putting it in the `/data` folder and running the experiments from `/experiments`.
In the paper, we use the SemEval 2015, 2016 and citysearch dataset.

## Citing

If you use the code or the techniques therein, please cite the paper:

```
ref
```

## License

MIT