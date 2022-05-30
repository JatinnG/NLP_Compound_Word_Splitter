# NLP_Compound_Word_Splitter
In this project, we will build a distributional semantics based compound word splitter that can help in word sense disambiguation for a wide array of NLP applications.


## Introduction to the problem - why split the words?

**Motivation:** In many European and Scandinavian languages (German, Dutch, Swedish, Danish, etc. and also in English), words are often combined with each other to form 'compound' words with complex meanings. Such compounds can be formed by various permutations between word-pairs and poses a challenge for NLP applications - due to their huge volume it is not possible to include all the compounds in word dictionary. This leads to exclusion of almost all the compounds from the training data, and hence the model performance decreases. For instance, in Machine Translation, if the word doesn't occur in the training corpus, it might be poorly or not even be translated. 

> *Some instances showing how decomposition of a word provide lexical advantage*
 > * *Hochschulklinik	: Hochschul | klinik (University Clinic)*
 > * *Bilderbuch	: Bilder | buch (Picture Book)*
 > * *Warmwasserbereitung : Warm | Wasser | Bereitung (Warm water system)*



**Objectives:** In this project, we aim to build a heuristic based compound word splitting tool which can be used as is in any standard NLP pre-processing pipeline. This step can be plugged-in before generating the word embeddings and allows the model to get better lexical coverage of the corpus. I have tried to wrap up everything in a single Jupyter Notebook. The results are stored in split_results.txt file and can be compared against gold standard splits for assessing the quality.

---

## DeReKo Corpus (Deutsch) Description

DeReKo is a popular word dictionary widely used as a reference for German language corpus. It was created at Leibniz Institute for German Language (IDS), Mannheim to promote NLP research - includes POS and Frequency tagged word list in a zipped format. We will be working on top 100,000 most frequent words in **German Language**. Refer to [link] https://www.ids-mannheim.de/en/s/corpus-linguistics/projects/methods-of-analysis/corpus-based-lemma-and-word-form-lists/ for more details.

---

## Methodology - that's how we do it!

The work of this project is inspired from empirical methods for compound word splitting proposed by Koehn et al., 2013. A single "lemma" may appear in different inflecled forms within its compound [For e.g. like, like(d), like(s)], first we generate all the possible splits for a given compound and then select the best one based upon a scoring metric. The lexical information from the corpus (POS tag, Frequency) is used to select the best split out of feasible split options. We have also included some basic filters and methods to provide more robustness to the method. Refer to code comments for more details.

--- 

## Future scope

I urge the readers to implement the method on their own, comment on the results and suggest any new ideas on the methodology improvement. The tool can also be extended to include more languages such as English and Swedish.

## References

*[1] Philipp Koehn and Kevin Knight. 2003. Empirical methods for compound splitting. In Proceedings of the 10th Conference of the European Chapter of the Association for Computational Linguistics (EACL), pages 187–193, Budapest, Hungary.*

*[2] Joachim Daiber, Lautaro Quiroz, Roger Wechsler, and Stella Frank. 2015. Splitting Compounds by Semantic Analogy. In Proceedings of the 1st Deep Machine Translation Workshop, pages 20–28, Praha, Czechia. ÚFAL MFF UK.*

*[3] Marion Weller-Di Marco. 2017. Simple Compound Splitting for German. In Proceedings of the 13th Workshop on Multiword Expressions (MWE 2017), pages 161–166, Valencia, Spain. Association for Computational Linguistics.*
