![Image](https://github.com/user-attachments/assets/f95ccdd4-7a2d-4bd1-9ab0-777dadd9fb7c)
# NLP-Based Ethical Evaluation of Corporate Privacy Policies
## Project Overview
Privacy policies are the primary mechanism through which organizations disclose how they collect, use, and share user data. However, despite their ubiquity, they are rarely read due to their length and complex legalistic language.

This project utilizes Natural Language Processing (NLP) techniques to analyze the landscape of contemporary privacy policies from hundreds of publicly traded companies. The goal is to evaluate whether these documents are transparent and accessible to the general public, raising key questions about data ethics.

**Context:** This project was conducted as part of the MSBA 6141: Ethics and Data Privacy course (Fall 2023) under the guidance of Professor Russell Funk.

## Objectives
- To gain a data-driven understanding of the content and structure of privacy policies.
- To analyze common themes, entities, and language patterns used by corporations.
- To quantitatively evaluate the readability of these documents and assess the "transparency gap" between corporate disclosures and user literacy.

## Tech Stack
- **Language:** Python
- **Data Manipulation:** pandas, json
- **NLP & Analysis:**
    - spacy (Tokenization, NER)
    - textacy (Text statistics, KWIC, Readability scoring)
    - gensim (Topic Modeling - LDA)
- **Visualization & Clustering:** matplotlib, umap-learn

## Methodology & Key Analysis

### 1. Data Preprocessing
- Ingested raw JSON data containing full texts of privacy policies.
- Performed data wrangling to merge paragraphs into single text strings.
- Utilized Spacy (en_core_web_lg) for tokenization, lemmatization, and part-of-speech tagging.

### 2. Topic Modeling (LDA)
- Applied Latent Dirichlet Allocation (LDA) using gensim to uncover latent semantic structures.
- Identified common topic clusters centered around keywords such as 'information', 'use', 'third-party', 'cookies', and 'service', revealing the primary focus areas of data collection.

![LDA Topic Modeling Visualization](Add your image path here)

### 3. Keyword in Context (KWIC)
- Used textacy to extract specific contexts for high-value words like "rights".
- Analyzed how companies frame user rights (e.g., "right to receive a notice", "exercise our rights"), moving beyond abstract topics to specific legal phrasing.

### 4. Named Entity Recognition (NER)
- Extracted named entities (Organizations, Persons, GPE) to identify key stakeholders.
- Result: Frequent entities included 'Google Analytics', 'Facebook', 'Twitter', 'EU', and 'GDPR', highlighting the heavy reliance on third-party tracking services and the influence of regulatory frameworks.

### 5. Readability Analysis (Key Insight)
- Calculated Flesch-Kincaid Grade Level and Gunning-Fog Index scores.
- Finding: The vast majority of policies require a university-level education (Grade 14+) to comprehend.
- Ethical Implication: Given that the average U.S. adult reads at an 8th-grade level (OECD data), this complexity creates a significant barrier to informed consent, suggesting a lack of genuine transparency.

![Readability Score Distribution](Add your image path here)

### 6. Document Embeddings & Clustering
- Vectorized full policy documents and applied UMAP for dimensionality reduction.
- Visualized the semantic similarity between different companies to detect "boilerplate" language and industry-specific clustering.

![UMAP Clustering Visualization](Add your image path here)

## Conclusion
The analysis demonstrates that while privacy policies are legally comprehensive, they fail in their ethical duty of accessibility. The high reading level and complex terminology effectively exclude a large portion of the population from understanding how their data is used. This suggests that current data privacy practices prioritize legal liability protection over user transparency.

## Acknowledgements
- Course: MSBA 6141 Ethics and Data Privacy (Fall 2023)
- Instructor: Professor Russell Funk
- Dataset: Publicly traded company privacy policies (Source: ansgarw/privacy)
