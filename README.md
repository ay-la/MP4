# MP4: Text processing in NLTK

In this MP you'll use [NLTK](https://www.nltk.org/), the Natural Language Toolkit, for some basic text processing.

## Data collections

**You do not need to turn in anything for this part of the assignment.**

### What to do

First obtain the data we'll need:
 
    import nltk
    # You only need to do these two steps once.
    assert nltk.download("gutenberg")
    assert nltk.download("punkt")

We'll use Lewis Carroll's 1864 book _Alice's Adventures In Wonderland_ for our examples. The following loads the raw text into one gigantic string.

    text = nltk.corpus.gutenberg.raw("carroll-alice.txt")

## Sentence boundary detection

## What to do

Apply sentence boundary detection to `text` using the `nltk.sent_tokenize` function, which will return a list of sentence strings; call this `sentences`.

### Hints

* Don't overthink this.
* Don't be alarmed, but the sentence boundary detector is not particularly good, and makes many errors.

### Test support

    # The text has 1625 sentences in all.
    assert len(sentences) == 1625

## Tokenization

Apply word tokenization to each string in `sentences` using the `nltk.word_tokenize` function. Use this to create a list of sentences, each of which is a list of tokens; call this `tokenized_sentences`.

### Hints

* `nltk.word_tokenize` takes a single sentence string as an argument (not a list of sentence strings). So, you will have to apply it once per sentence, in a loop.
* Don't be alarmed, but the tokenizer has some interesting ideas about what a token is.

### Test support

    # We still have 1625 sentences.
    assert len(tokenized_sentences) == 1625 
    # The first sentence (after the title) has 68 tokens.
    assert len(tokenized_sentences[1]) == 68

## Word frequencies

### What to do

Import the `collections` module. Then, using the `Counter` class, compute frequencies of all tokens in `tokenized_sentences`. Finally, print the 20 most common tokens, one per line; however, **do not** print their frequencies.

### Hints

* Read the [`Counter` documentation](https://docs.python.org/3.6/library/collections.html#collections.Counter) for hints.

### Test support

The most common token is a particular punctuation character; the 13th most common token is a proper name.

## Stretch goal

### What to do

First, download some additional data:
  
    nltk.download("averaged_perceptron_tagger")
    nltk.download("universal_tagset")

Then, use the `nltk.pos_tag` function and the universal tagset to tag the sentences in `tokenized_sentences`. Then, print out a list of the tags in decreasing frequency order.

### Hints

* Read [Chapter 5 of the NLTK book](https://www.nltk.org/book/ch05.html) for hints.

### Test support

The most common tag is `VERB`.
