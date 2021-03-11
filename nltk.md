# NLTK

Notes on Natural Language Processing in Python 3 with NLTK

## Getting Started

* [NLTK GitHub](https://github.com/nltk/nltk)
* pip install nltk
* import nltk

## Tokenization

### Sentence Tokenization

* Sentence Tokenizer using PunktSentenceTokenizer
* Marks the beginning and end of Sentences
* PunktSentenceTokenizer can be used directly with a language pickle file when processing large data
* Supports multi-language tokenization models

```python
sentences = nltk.tokenize.sent_tokenize(text)

tokenizer = nltk.data.load('tokenizers/punkt/PY3/english.pickle')
sentences = tokenizer.tokenize(text)

tokenizer = nltk.data.load('tokenizers/punkt/PY3/german.pickle')
sentences = tokenizer.tokenize(text)
```

### Word Tokenization

* Word Tokenizer using TreebankWordTokenizer
* Splits sentences into word tokens and preserves punctuation
* PunktWordTokenizer preserves punctuation with words
* WordPunctTokenizer separates punctuation from words
* RegexpTokenizer separates words using regular expressions

```python
words = nltk.tokenize.word_tokenize(sentence)

tokenizer = TreebankWordTokenizer()
words = tokenizer.tokenize(sentence)

tokenizer = PunktWordTokenizer()
words = tokenizer.tokenize(sentence)

tokenizer = WordPunctTokenizer()
words = tokenizer.tokenize(sentence)

#
# words and apostrophe groupings
#
tokenizer = RegexpTokenizer("[\w']+)
words = tokenizer.tokenize(sentence)
words = nltk.tokenize.regexp_tokenize(sentence, "[\w']+")
```

### Stop Words

```python
#
#   download the nltk english stopwords list
#
nltk.download()
stopwords = nltk.corpus.stopwords.words("english")
filtered = [word for word in wordList if not word in stopwords]
```

### Stemming

```python
ps = stem.PortStemmer()
wordstem = ps.stem(word)
```


### Parts of Speech Tagging

```python
#
#   download all packages
#
nltk.download()
posTagList = nltk.pos_tag(wordList)
```
