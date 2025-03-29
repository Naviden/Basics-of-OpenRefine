# Advanced Text Analysis

OpenRefine is useful for analyzing textual data such as tweets, reviews, or comments.

## Fingerprint Function

The fingerprint method helps normalize text:
- Converts to lowercase
- Removes punctuation
- Sorts tokens alphabetically

### Use Case:
```javascript
fingerprint(value)
```

## N-Grams

N-grams capture co-occurrence of words. A 4-gram of “I love OpenRefine tool” would be:
- “I love OpenRefine tool”

Use this for more granular analysis of expressions and hashtags.

## Combining N-Grams and Fingerprint

You can apply both methods for deduplication and frequency analysis.

### Example:
1. Create 3-grams from tweets
2. Use fingerprint to normalize
3. Create a text facet to explore most common patterns

## Text Cleanup

Common transformations:
- Removing accents: `value.unaccent()`
- Removing punctuation: `value.replace(/[.,!?]/, "")`
- Extracting hashtags: `value.match(/#\w+/)`

## Visualization

Cleaned text data can be exported to tools like:
- [Wordle](http://www.wordle.net/create)
- [Voyant Tools](https://voyant-tools.org/)