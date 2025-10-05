# Data for "FactAppeal: Identifying Epistemic Factual Appeals in News Media"

The `data/` directory contains the FactAppeal dataset, split into training (70%), development (15%), and test (15%) sets.

* **Description**: The dataset consists of 3,226 English-language sentences from news articles, manually annotated with fine-grained, span-level tags to identify factual claims and their epistemic appeals.

* **Files**:
    * `data/train.csv` (2258 sentences)
    * `data/dev.csv` (484 sentences)
    * `data/test.csv` (484 sentences)

* **Format**: The data is provided in CSV format. Each file has two columns: `sentence` for the raw sentence, and `annotation` for the annotated sentences. The annotations are provided as XML-style tags within the text.

* **License**: The dataset is released under the [CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/).

---

### Tag Descriptions

Here is a brief summary of the annotation tags used in the dataset. For the complete annotation guidelines, please refer to the paper.
A colon (`:`) is used to separate modifiers within tags (e.g. `<Fact_Appeal:Direct_Quote>`, `<Source:Named:Expert>`).

* **Factuality Tags**
    * `<Fact_No_Appeal>`: Marks a factual statement made without citing an external source.
    * `<Fact_Appeal>`: Marks a factual statement supported by an appeal to a source. It has a modifier for the quotation method:
        * `:Direct_Quote`: For direct, verbatim quotes.
        * `:Indirect_Quote`: For paraphrased or summarized claims.

* **Source Tags**
    * `<Source>`: Identifies the source of the appeal. It has modifiers for name and type:
        * `:Named` or `:Unnamed`: Indicates if the source is identified by a proper name.
        * **Source Type**: A category describing the source's authority (e.g., `:Official`, `:Expert`, `:Witness`, `:Active_Participant`, `:Direct_Evidence`, `:Expert_Document`).
    * `<Source_Attribute>`: Marks text describing the source's role, title, or credentials.

* **Contextual Tags**
    * `<Recipient>`: The entity to whom the information was communicated.
    * `<Appeal_Time>`: The time when the appeal was made (if mentioned).
    * `<Appeal_Location>`: The location where the appeal was made (if mentioned).
