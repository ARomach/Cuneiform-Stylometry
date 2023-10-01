[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ARomach/Cuneiform-Stylometry/HEAD)

# Stylometric Analysis for Akkadian Cuneiform Texts

This Jupyter notebook provides code to perform stylometric analysis on cuneiform texts. The code can be accessed and used without any installation through binder.

.. image:: https://mybinder.org/badge_logo.svg
 :target: https://mybinder.org/v2/gh/ARomach/Cuneiform-Stylometry/HEAD

The code was designed specifically for Akkadian texts, however, it is likely to work well on all languages that used the cuneiform script, meaning all languages that have a transliteration system that follows the same principles. Additionally, texts written in other non-alphabetic writing systems for whose characters there are unicode representations could probably benefit from this code as well. The code is based on [*Introduction to stylometry with python* from the Programming Historian website](https://programminghistorian.org/en/lessons/introduction-to-stylometry-with-python).

It is accompanied by a metadata folder and texts folders. The texts folder currently holds one corpus as a case-study, 81 legal and administrative documents from the Neo-Babylonian period (ca. 7^th^-5^th^ centuries BCE). These texts edited in the 1975 dissertation of Raymond B. Dillard. They are currently in the Free Library of Philadelphia (FLP), after being purchased on the antiquities market in the early 20^th^ century by John Frederik Lewis.

The notebook employs the following methods on the texts:

1. Tf-idf vectorization
2. Create a distance matrix between the texts
3. T-SNE dimenstion reduction to display the distances between the texts on a scatter plot
4. Network analysis of the relationships between similar texts
5. A close reading: looking at groupings of nearest texts

The code is written so that no previous knowledge in python or stylometric methods is assumed. There are instructions throughout that explain the code, the stylometric methods, and give the necessary information to choose specific parameters.

As different parameters can give different results, it is possible to run the code several times and assess the differences.

Certain parameters are decided in advance (e.g. not to lowercase all characters) and some are left to the user (e.g. choosing 1-gram, 2-gram, or 3-gram). The idea behind this was that certain parameters are necessary for a logical parsing of cuneiform transliterations or their representation in Unicode cuneiform glyphs.

## Adding corpora

The stylometric analysis can be performed on texts which are either transliterated, or in which the signs are represented in Unicode. For transliterated texts, it is recommended that personal names and numbers be replaced with PN and NUM (or similar), depending on the focus of study (i.e. period, genre, scribal habits etc.).

The new corpora need to be added to the relevant folders before starting to use the code. This includes the following:

1. A folder which includes the texts for stylometric analysis:
- The folder should be placed under the `texts` folder.
- Each file should be a plain text file and contain one text only.
- The texts should be transliterated texts without any editorial marks (including no hyphens and dots between signs), or texts in Unicode cuneiform.
- It is recommended that each file name will be the name of the text (this is later used as the text identifier in the dataframes and CSVs produced).
2. A metadata file
- The file should be placed under the `metadata` folder.
- The file should be a CSV file.
- One of the columns **needs to be titled** `text_name`, and its values need to be identical to the file names of the texts under the `texts` folder.
- It is recommended that additional columns will have relevant information about the texts you want to study (period, genre, area, scribe, etc.).
