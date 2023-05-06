# Tokenization #

Tokenization is the process of breaking down text into individual words, phrases, symbols, or other meaningful elements called tokens. I will use the same sample text from the previous section.

## 1. Dataset ##

```python
sample_data = [
    "IKEA är ett svenskt möbelföretag med huvudkontor i Älmhult.",
    "Stockholm är huvudstad i Sverige.",
    "Skåne ligger i södra Sverige och är känt för sina vackra landskap."
]
```

## 2. Tokenizing the Set ##

```python
# Using SpaCy
spacy_tokens = [[token.text for token in nlp_spacy(text)] for text in sample_data]

# Using Polyglot
polyglot_tokens = [[word for word in Text(text, hint_language_code="sv").words] for text in sample_data]

for i, (spacy_token_list, polyglot_token_list) in enumerate(zip(spacy_tokens, polyglot_tokens)):
    print(f"Text {i + 1}:")
    print(f"SpaCy Tokens: {spacy_token_list}")
    print(f"Polyglot Tokens: {polyglot_token_list}\n")
```

## 3. Comparing the Results ##

```yaml
Text 1:
SpaCy Tokens: ['IKEA', 'är', 'ett', 'svenskt', 'möbelföretag', 'med', 'huvudkontor', 'i', 'Älmhult', '.']
Polyglot Tokens: ['IKEA', 'är', 'ett', 'svenskt', 'möbelföretag', 'med', 'huvudkontor', 'i', 'Älmhult', '.']

Text 2:
SpaCy Tokens: ['Stockholm', 'är', 'huvudstad', 'i', 'Sverige', '.']
Polyglot Tokens: ['Stockholm', 'är', 'huvudstad', 'i', 'Sverige', '.']

Text 3:
SpaCy Tokens: ['Skåne', 'ligger', 'i', 'södra', 'Sverige', 'och', 'är', 'känt', 'för', 'sina', 'vackra', 'landskap', '.']
Polyglot Tokens: ['Skåne', 'ligger', 'i', 'södra', 'Sverige', 'och', 'är', 'känt', 'för', 'sina', 'vackra', 'landskap', '.']
```

SpaCy and Polyglot produce very similar tokenization results for the Swedish text. In this specific example, there are no significant differences in how they handle punctuation, contractions, or other language-specific elements; however, results may vary in larger datasets.
