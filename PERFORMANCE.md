# Performance and Scalability #

Performance refers to the speed at which each library can process text, while scalability indicates the ability to handle larger datasets without significantly impacting performance. I will use a new, larger sample dataset for this occasion.

```python
sample_data = " ".join(["Jag älskar det här stället. Personalen är mycket vänlig. Det är en fruktansvärd upplevelse. Jag kommer aldrig tillbaka hit. Maten var okej, men servicen kunde varit bättre."] * 1000)
```

Using a timer module, we can measure the processing time of both libraries.

```python
import time

# Using SpaCy
start_time_spacy = time.time()
doc_spacy = nlp_spacy(sample_data)
end_time_spacy = time.time()

# Using Polyglot
start_time_polyglot = time.time()
doc_polyglot = Text(sample_data, hint_language_code="sv")
end_time_polyglot = time.time()
```

Let's compare the results for both libraries.

```python
SpaCy processing time: 1.9483599662780762 seconds
Polyglot processing time: 3.369850158691406 seconds
```

As it is already known, SpaCy is generally optimized for performance and is faster when processing large amounts of text.
