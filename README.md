# wikitimeline19
WikiPossessions: Possession timeline generation as an evaluation benchmark for machine reading comprehension of long texts.

Temporally-oriented possession: A corpus for tracking possession over time

Official release, January 3, 2019.

Paper:
---------------------------------------------------------------------------------------------------------------------------------------
Dhivya Chinnappa, Alexis Palmer, Eduardo Blanco. 2020.
WikiPossessions: Possession timeline generation as an evaluation benchmark for machine reading comprehension of long texts.
In Proceedings of The 12th Language Resources and Evaluation Conference (LREC).

Dhivya Chinnappa, Alexis Palmer and Eduardo Blanco. 2019.
Temporally-oriented possession: A corpus for tracking possession over time. 
In Proceedings of the second meeting on Society for Computation in Linguistics(SCiL), Extended abstracts. New York City, United States.
---------------------------------------------------------------------------------------------------------------------------------------

Dhivya Chinnappa - Department of Computer Science and Computer Engineering, University of North Texas, Denton, TX.

Alexis Palmer - Department of Linguistics, University of North Texas, Denton, TX.

Eduardo Blanco - Department of Computer Science and Computer Engineering, University of North Texas, Denton, TX.

Contact: dhivyainfantchinnappa@my.unt.edu, alexis.palmer@unt.edu, eduardo.blanco@unt.edu
========================================================================================

The file annotations.csv provides annotations for tracking possession over time from 92 Wikipedia pages.

-------------
CORPORA
-------------
Annotations are done on top of 92 Wikipedia HTML pages downloaded on June 9 2017.
Refer paper for how the annotations are done.

-----------------
FILES and FOLDERS
-----------------
annotations			Folder containing the annotated XML file
html_annotated			Contains 92 HTML Wikipedia pages used to track possessions over time
read_annotations.py		Python file to read the annotations
print_wiki_annotations.py	Python file to print the contents of Wikipedia and annotations
data_structures.py		Python file used to build data structures from the annotations
print_wiki_annotations_output	Output after running print_wiki_annotations.py

       
------------------------
ANNOTATIONS EXPLANATION
------------------------

1. Possessor type - PER/ORG/GPE denoting if the possessor is a person, organization, or a geo political entity (location). Note that the possessors are not just typical named entities. Entities like thieves, sister are considered possessors.
2. Possessor - name of the possessor
3. Attributes of possession
	3.1 Possessor certainty - PC/PUC denoting if the annotator is certain (PC) that the possessor possessed the artifact or not (PUC).
	3.2 Order of possession - a number denoting the order of possession
	3.3 Possession duration - a year, range of years, or an event denoting the possession duration
	3.4 Temporal anchor of possession - Bef/Dur/Aft indicating when the possession exists with respect to possession duration. i.e., Before/During/After the possession duration.
	3.5 Possession duration certainty - C/UC denoting if the annotator is certain (C) that the possession is true during the possession duration (UC).
**In cases where a possession duration is not found (Unknown), there is no temporal anchor of possession and possession duration certainty.


Example:

Consider the output of the article The Conspiracy of Claudius Civilis.

Gold_Annotations
PER Claes Grill ['PC', '4', 'Unknown']
PER Sophia Grill ['PC', '2', '1767', 'Dur', 'UC']
ORG Nationalmuseum ['PC', '6.2', '1864', 'Dur', 'C']
ORG Nationalmuseum ['PC', '8', 'Unknown-Now', 'Dur', 'C']
GPE Sweden ['PC', '2', '1767', 'Dur', 'UC']
GPE Amsterdam ['PC', '7', 'Unknown']
GPE Stockholm ['PC', '8', 'Unknown-Now', 'Dur', 'C']
ORG Rijksmuseum ['PC', '7', 'Unknown']
PER Rembrandt ['PC', '1', '1661-1662', 'Dur', 'C']
GPE Stockholm ['PC', '6.2', '1864', 'Dur', 'C']
ORG Royal Palace ['PC', '6.1', 'Unknown']
GPE Amsterdam ['PC', '2', '1734', 'Dur', 'C']
ORG Royal Swedish Academy of Arts ['PC', '6', 'Unknown-Now', 'Dur', 'C']
PER Nicolaas Kohl ['PC', '2', '1734', 'Dur', 'C']
PER Henrik Wilhelm Peill ['PC', '5', 'Unknown']

In the annotation,
PER Sophia Grill ['PC', '2', '1767', 'Dur', 'UC']

1. The possessor is a person.
2. The name of the possessor is Sophia Grill.
3.1 The annotator is certain that Sophia Grill is a possessor.
3.2 Sophia Grill is the first possessor of the artifact The Conspiracy of Claudius Civilis.
3.3 The possession duration for Sophia Grill possessing the artifact is 1767.
3.4 The possessor Sophia Grill possessed the artifact DURING the possession duration 1767.
3.5 The annotator is NOT certain if the possession duration is correct.


In the annotation
GPE Sweden ['PC', '2', '1767', 'Dur', 'UC']

The annotations are similar to the previously explained annotation, but the type of the possessor is GPE and the possessor's name is Sweden.


Consider the annotations,
ORG Royal Swedish Academy of Arts ['PC', '6', 'Unknown-Now', 'Dur', 'C']
ORG Royal Palace ['PC', '6.1', 'Unknown']
GPE Stockholm ['PC', '6.2', '1864', 'Dur', 'C']

It is clear from the article that the Royal Swedish Academy of Arts is the possessor of the painting, during which the painting was also possessed by the Royal Palace and by the city Stockholm. The possession duration for the possessor Royal Palace is unknown, and hence there is no temporal anchor of possession or possession duration certainty.



############################################################################################################################################################
