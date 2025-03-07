![Version](https://img.shields.io/github/v/release/DCMLab/couperin_clavecin?display_name=tag)
[![DOI](https://zenodo.org/badge/388412801.svg)](https://doi.org/10.5281/zenodo.14984598)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/couperin_clavecin)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/couperin_clavecin](https://github.com/DCMLab/couperin_clavecin) and the corresponding
* documentation page [https://dcmlab.github.io/couperin_clavecin](https://dcmlab.github.io/couperin_clavecin)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/couperin_clavecin/introduction).

# François Couperin – L'art de toucher le clavecin

This corpus of annotated [MuseScore](https://musescore.org) files has been created within
the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora) and employs
the [DCML harmony annotation standard](https://github.com/DCMLab/standards). It represents nine pieces found in François
Couperin's 1717 treatise on harpsichord fingering, ornamentation, and interpretation. This work was intended to provide
a study supplement to Couperin's own 1713 Pieces de clavecin, published upon a grant of privilege by King Louis XIV.
This courtly and didactic music represents an elegant and archetypical example of the Baroque harmonic technique, and
our annotations stress the precision of contrapuntal detail that permeates this music. These annotations will provide
considerable support to future quantitative study of Baroque ornamentation and contrapuntal figuration.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/couperin_clavecin/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [couperin_clavecin.zip](https://github.com/DCMLab/couperin_clavecin/releases/latest/download/couperin_clavecin.zip)
  * [couperin_clavecin.datapackage.json](https://github.com/DCMLab/couperin_clavecin/releases/latest/download/couperin_clavecin.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/couperin_clavecin.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the *Allemande* has the following files:

* `MS3/00_allemande.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/00_allemande.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/00_allemande.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/00_allemande.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/00_allemande.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/00_allemande.harmonies.tsv")
notes = ms3.load_tsv("notes/00_allemande.notes.tsv"")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/couperin_clavecin/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/couperin_clavecin/issues) and/or feel free to fork and submit pull requests.

## Cite as

_Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). François Couperin – L'art de toucher le clavecin (v2.2) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.14984598_

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)


## Overview
|     file_name      |measures|labels|standard|                annotators                 |   reviewers    |
|--------------------|-------:|-----:|--------|-------------------------------------------|----------------|
|00_allemande        |      13|    66|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, Hanné Becker|
|01_premier_prelude  |      20|    40|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, Hanné Becker|
|02_second_prelude   |      18|    48|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, Hanné Becker|
|03_troisieme_prelude|      18|    80|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, Hanné Becker|
|04_quatrieme_prelude|      23|    70|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, Hanné Becker|
|05_cinquieme_prelude|      24|    96|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, Hanné Becker|
|06_sixieme_prelude  |      59|   108|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0) |DK              |
|07_septieme_prelude |      24|    87|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, Hanné Becker|
|08_huitieme_prelude |      31|   122|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, Hanné Becker|


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
