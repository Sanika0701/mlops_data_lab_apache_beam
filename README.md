# Apache Beam Text Analysis - Hamlet 🎭

## 📋 Project Overview

This repo extends the basic Apache Beam word count example by implementing **6 sophisticated data processing pipelines** on Shakespeare's *Hamlet*. The analysis demonstrates advanced Apache Beam concepts including custom transformations, stateful processing, and multi-stage aggregations.

---

## 🎯 Key Modifications from Original Lab

| Aspect | Original Lab (King Lear) | My Implementation (Hamlet) |
|--------|-------------------------|---------------------------|
| **Input Text** | King Lear | **Hamlet** |
| **Number of Pipelines** | 1 basic word count | **6 advanced pipelines** |
| **Transformations** | Simple Map/FlatMap | **Custom DoFn, filters, complex aggregations** |
| **Analysis Types** | Word frequency only | **Word count, character analysis, sentiment, vocabulary richness, scene analysis, word length distribution** |
| **Data Filtering** | None | **Case-insensitive, minimum word length** |
| **Output Files** | 1 output file | **6 different analytical outputs** |

---

## 🔬 Pipeline Descriptions

### Pipeline 1: Advanced Word Count
**Enhancement:** Case-insensitive word counting with length filtering
- Converts all text to lowercase for accurate counting
- Filters words with minimum length of 5 characters
- Returns top 20 most frequent words
- **Output:** `hamlet_analysis_top_words-*`

**Key Techniques:**
- `beam.Map()` for case conversion
- `beam.Filter()` for word length filtering
- `beam.combiners.ToList()` for sorting

---

### Pipeline 2: Character Speech Analysis
**New Feature:** Identifies and quantifies character dialogue
- Parses character names from play format
- Counts total words spoken by each character
- Ranks characters by dialogue volume
- **Output:** `hamlet_analysis_character_words-*`

**Key Techniques:**
- Regular expression pattern matching
- Custom extraction function
- `beam.CombinePerKey()` for aggregation

**Sample Output:**
