# NMT and PBSMT Error Analyses in English to Brazilian Portuguese Automatic Translations

This respository contains an automatically translated and evaluated corpus from English to Brazilian Portuguese. The original corpus is the test-a split from the [Revista Pesquisa FAPESP](http://www.nilc.icmc.usp.br/nilc/tools/Fapesp%20Corpora.htm) with texts extracted from the [Pesquisa FAPESP magazine](https://revistapesquisa.fapesp.br/).

## Corpus

The annotations can be found in files:

 * `NMT_test-a_1-300.blast`: annotations for NMT
 * `PBSMT_test-a_1-300.blast`: annotations for PBSMT


## Format

The files are in [BLAST](https://cl.lingfil.uu.se/~sara/blast/) format, which starts with two configuration lines starting with `#`, which indicate, respectively, the sentence types (source, reference and system) and the tagset file (`lalic-catsv2`).

Afterwards, the annotated corpus is written, which contains three sentences: the original English sentence, the reference sentence from the original corpus (in Portuguese) and the sentence automatically translated (in Portuguese), each one in a line. After a blank line, the annotations are presented separated by spaces.

The annotation format separates token indices with `#`, these indices keep all tokens aligned through all three sentences. If there is no alignment in a sentence, the `-1` index is used. If there is more than one token to be aligned, their indices will be separated by a comma (`,`).

Then, the last element of the annotation is the tag according to the taxonomy adopted. An example can be seen below:

```
As in the finals of a championship , it is impossible to please both teams .
Como numa decisão de campeonato , é impossível contentar os dois times .
Como na finals de um campeonato , é impossível agradar às equipes .

3#2#2#lex-notTrWord 
```

In the example, the words `finals`, `decisão` and `finals` are aligned with the `lex-notTrWord` tag.

All tags are defined in the file `lalic-catsv2`.

## Citing
A comparative analysis using the annotations provided in this corpus was published in [LREC 2020](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.446.pdf). Here, we provide the bibtex entry for citing:

```
@inproceedings{CaseliInacio2020,
  title = {{{NMT}} and {{PBSMT}} Error Analyses in {{English}} to {{Brazilian Portuguese}} Automatic Translations},
  booktitle = {Proceedings of the 12th Language Resources and Evaluation Conference},
  author = {Caseli, Helena de Medeiros and In{\'a}cio, Marcio},
  year = {2020},
  month = may,
  pages = {3623--3629},
  publisher = {{European Language Resources Association}},
  address = {{Marseille, France}},
  isbn = {979-10-95546-34-4},
  language = {English}
}
```
