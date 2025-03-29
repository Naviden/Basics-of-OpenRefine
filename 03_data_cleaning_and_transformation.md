# Data Cleaning and Transformation

OpenRefine provides a powerful set of features for cleaning and transforming data.

## Text Facets and Filters

Facets allow you to:
- Group by unique values
- Count frequency of values
- Filter rows interactively

## Clustering and Editing

Clustering helps find similar but slightly different values (e.g., "USA", "U.S.A", "United States").

### Clustering Methods

- **Key Collision**: Creates keys by simplifying values (e.g., removing vowels)
- **Nearest Neighbor**: Uses algorithms like Levenshtein Distance

Steps:
1. Click column dropdown → Edit Cells → Cluster and Edit
2. Choose method and algorithm
3. Review and merge suggestions

## Transformations with GREL

General Refine Expression Language (GREL) allows custom data transformations.

Examples:
```javascript
value.trim()              // Remove leading/trailing spaces
value.toLowercase()       // Convert to lowercase
value.replace(",", "")    // Remove commas
```

## Formatting Numbers

To clean numbers that are treated as text:
```javascript
value.replace("~", "")
     .replace(",", "")
     .replace("+", "")
     .replace(" -", "")
```
Then convert column to numeric format.

## Dates

Dates can be normalized by:
1. Converting number to text
2. Parsing to date:
```javascript
value.toDate()
```

## Handling Blanks and Duplicates

- **Blank Down**: Replaces repeating values with blanks
- **Facet by Blank**: Filters rows with/without blank values

## Combining Facets

You can combine multiple facets to isolate complex subsets of data (e.g., non-numeric + blank).