---
layout: default
title: 'Scholia: Necessary Data'
parent: 'Team 3: Data Vizualization' 
nav_order: 4
---
**Date:** 11.05.2019

**Team:** Data Visualization

**Author:** [Katharina Müller](https://github.com/Lianm123)

***

# Profiles:
## Authors: 
(Example [Scholia Jens Nielsen](https://tools.wmflabs.org/scholia/author/Q16733372))
* Authors Name
* Authors Wikidata ID (e.g. [Q16733372](https://www.wikidata.org/wiki/Q16733372) with link to respective Wikidata link) 
* Small description of Author from Wikipedia site, with given link to Wikipedia page
* Related Persons in list with links to their scholia pages
* The author's Orcid link (e.g.  [Orcid](https://orcid.org/0000-0002-9593-2294)) 

### List of publications:
* Date
* Work (Titel eg.["Capturing meaning: Toward..."](https://tools.wmflabs.org/scholia/Q56876997), with link to the respective scholia page for the article)
* Type (eg. document, scholarly article, scientific conference paper…)
* Pages (anzahl)
* Venue (eg. Journal, Conference, Proceedings…; this also includes link to respective scholia page)
* Authors (this also includes co-authors and the link to their scholia pages) 

### Other representations:
* Number of publications per year 
    * Needs publication year to sort by
* Number of pages per year
    * Number of pages published
* Venue statistics
    * Needs venue information-> called venue? In querry
    * Need to be able to count how many times a venue occured
    * Need its short name (e.g. LNCS short hand for Lecture Notes in Computer Science) 
    * Venue (e.g. lecture Notes in Computer Science with link to scholia page for it) 
    * Topics (e.g. computer science)
* Co-author graph 
    * Need names of all co-authors -> with link to information so that following information can be called:
        * Tätigkeit
        * Familienname
        * Geschlecht
        * Arbeitsgebiet
        * Wohnsitz
        * Ist ein(e) (e.g. Mensch) 
        * Geburtsort
        * Wirkungsort
        * Land der Staatsangehörigkeit
        * Gesprochene oder publizierte Sprachen
        * Promotionsbetreuer -> Name
        * Doktorand -> Name oder Anzahl
        * Öffentliches Amt oder Stellung
        * Besuchte Bildungseinrichtung
        * Bedeutende Werke -> Anzahl
        * Zugehörigkeit zu  -> e.g. DABAI
        * Schüler -> Anzahl
* Topic scores
    * Need: ?score ?topic ?topicLabel and ?work
    * I’m not sure where the score comes from, but it would make sense to be the amount a certain topic appeared in all of the authors works
* Topics of authored works
    * ?count ?theme ?themeLabel ?example_work ?example_workLabel
    * Count
    * Theme (e.g Semantic MediaWiki, Wikipedia… with link to respective scholia page) 
    * Example Work (e.g. Semantic Wikipedia with link to the its scholia page) 
* Associated images

* Topics-works matrix
    * ?count ?theme_label ?work_label 
* Timeline
    * ?label ?beginning ?ending ?education_degree_label ?education_statement ?affiliation ?affiliation_statement ?affiliation_degree ?affiliation_degree_label  ?award_statement ?award_label 
    * Publications
    * Most cited publication is also noted 
    * Affiliations with Unis, Institutes -> date of beginning of relationship
    * Award, their names and date received
* Academic tree
    * ?student1 ?student1Label ?supervisor1 ?supervisor1Label
* Locations
    * ?image ?item ?itemLabel ?geo (?property_item_label AS ?layer
    * It shows world map and locations where publications etc. happened
* Citation statistics
    * Count
    * Work -> title (eg. Tissue-based map of the human protepme)
* Citations by year
    * ?citing_work ?count ?kind ?date ?year
    * Citations from others
    * Self-citations
* Citing authors
    * Count
    * Citing author with link to scholia page
    * Orcid (e.g. https://orcid.org/0000-0002-5617-4611)

## Institute Pages:
(Example: [Technical University of Denmark](https://tools.wmflabs.org/scholia/organization/Q1269766) ([Q1269766](https://www.wikidata.org/wiki/Q1269766)))
* Institute Name
* Institute Wikidata ID
* Small description of Institute from Wikipedia
* List of related Institutes with links to their respective scholia page
### Representations of data: 
* Employees and affiliated
    * Work -> number of published works
    * Researcher -> their name and link to scholia page
    * Description -> who they are (e.g researcher, Danish biomechanical    engineer, Danish bioinformatics professor, scientist …)
    * Orcid of person and link to Orcid page
* Co-author graph
    * ?author1 ?author1Label ?image1 ?rgb
    * ?author2 ?author2Label ?image2 
    * ?publication_type ?work 
* Advisor graph
    * ?author1 ?author1Label ?rgb 
    * ?author2 ?author2Label 
    * ?gender1
    * It is important to be able to display the links between the displayed persons
    * They are connected because they all have the given Institute as their Employer/Arbeitsgeber
* Recent publications
    * Publication date
    * Work -> Title
    * Name of researchers
* Page production
    * per year per author. The number of pages for a multiple-author paper is distributed among the authors. The statistics is only for papers where the "number of pages" property has been set.
    * ?year
    * ?pages_per_author ?number_of_pages
    * ?researcher ?researcher_of_paper ?researcher_label ?work ?year
    * It shows:
        * Year
        * Name of Author
        * Number of pages each author published in the given year
* Most cited papers with affiliated first author
    * ?count ?work ?workLabel 
    * ?citing_work
    * ?researcher
    * ?researcher_statement
    * It seems to count how many times a paper published from an author at the Institute was cited  
* Co-author-normalized citations per year
    * Looks at all authors, how many times each author was cited per year 
    * ?year (SUM(?citations_per_author_) AS ?citations_per_author) ?researcherLabel
    * ?work wdt:P50 | wdt:P2093 ?researcher_of_paper .
    * ?researcher .
    * ?citing_work
    * ?date . 
* Awards
    * Count
    * Award Name and Scholia page link to the Award 
    * Names of recipient/recipients without links to their pages
* Gender distribution
    * Number of males
    * Number of females 

## Journal Pages: 
(Example: [NeuroImage](https://tools.wmflabs.org/scholia/venue/Q1981225)([Q1981225](https://www.wikidata.org/wiki/Q1981225)))
* Name of Journal
* Journal Wikidata ID
* Description from Wikipedia
* Related Journals with links to their scholia pages
###  Representations of data: 
* Recently Published works: 
    * (MIN(?publication_date_) AS ?publication_date)
    *   ?work ?workLabel
    *   ?author_label; ?author
    * Publication date
    * Work -> Paper titles with links to their scholia pages
    * Names of Authors 
* Topics:
    * ?count ?topic ?topicLabel ?example_work ?example_workLabel
    * Count
    * Topic (e.g attention, neuroimaging, schizophrenia and links to the     topics respective scholia page) 
    * Title and link to an example work, in which the topic was discussed
* Authors images
    * (SAMPLE(?image_) AS ?image) 
    * ?author ?authorLabel ?count
* Prolific authors
    * Count
    * Author name with scholia page link
    * Authors Orcid 
    * Title and link to an example work of the author
* Most cited articles
    * Count
    * Work -> title and scholia link 
    * Example citing work -> Name and scholia link of article that cited     the respective work
* Most cited authors
    * Count
    * Author Name and scholia link
    * Authors Orcid
    * Example cited work -> title and scholia link of work, which was cited by other works
    * Example citing work -> title and scholia link of work, which cites the previously described work 
* Citation distribution
* Cite venues
    * Count
    * Short name 
    * Name of cited journal with scholia page
* Venues cited from
    * Count
    * Short name of cited journal
    * Name of cited journal with link to their scholia page
### Not yet completed data representations: 
* Gender distributions
* Authors
* Authorship 

## Library Pages:
(Example: [Public Library of Science](https://tools.wmflabs.org/scholia/publisher/Q233358) ([Q233358](https://www.wikidata.org/wiki/Q233358)))
* Name of Library
* Library Wikidata ID
* Description from Wikipedia
### Representations of data: 
* Journals and other collections
    * Number of works
    * BFI
    * Journal name and link to its scholia page
    * Theme of journal (e.g. science, genetics, pathogen…)
* Recently established journals
    * Journal names
    * Date the first of its kind was published
* Most cited papers
    * Number of citations
    * Work -> its title and scholia link
    * The name of the journal the work was published in
        * With the scholia page link for the journal
* As function of number of published works
    * ?work_count ?citation_count ?journal ?journalLabel 
    * ?work ?citing_work

## Topic Pages:
(Example: [Zika Virus](https://tools.wmflabs.org/scholia/topic/Q202864) ([Q202864](https://www.wikidata.org/wiki/Q202864)))
* Name of Topic
* Wikidata ID for topic
* List of related topics and their links to the Scholia pages
### Representations of data: 
* Recently published works on topic
    * ?date ?work ?workLabel ?topics ?topic ?topic_label
    * Publication date
    * Work -> title and scholia link to work
    * Topics (e.g. Zika virus) 
* Publications per year
    * ?year ?work ?number_of_publications ?article_type ?earliest_year ?type
    * Number of publications
    * Type of publication (e.g. clinical trial, erratum, film, literature review…) 
* Authors publishing about the topic
    * Count
    * Author name and scholia link
    * Authors Orcid and link to orcid page
* Co-author graph
    * The 25 most prolific authors and their co-authors
    * ?author1 ?author1Label ?rgb ?author2 ?author2Label ?gender1 ?work
    * For information necessary about author check Author page information list above
* Co-occurring topics 
    * Count
    * Topic and scholia page link (e.g. Zika virus infection or congenital Zika virus infection) 
    * Example work 
        * Article title to do with topic and link to its scholia page
* Co-occurring topics graph
    * Only a maximum of the 400 most often occuring links are shown
        * E.g. Brazil, genomics, antibody, West Nile Virus etc. 
    * ?topic1 ?topic1Label ?topic2 ?topic2Label 
    * A topic point contains following information: 
        * Zusammensetzung des Virusgenoms
        * Ursache von
        * Medizinisches Fachgebiet
        * Übergeordnetes Taxon
        * Taxonomisher Rang
        * Arbeitsliste eines Wikimedia-Projekts
        * Ist ein(e) (e.g. taxon)
        * Unterklasse von ->Anzahl
    * If a country is a topic:
        * Zeitzone
        * Amtssprache
        * Notrufnummer
        * Hauptstadt 
        * Währung
        * Flagge
        * Hymne
        * Top-Level-Domain
        * Kategorie für Personen mit Bezug
        * Diplomatische Beziehung
        * Währung
        * Liegt in der Verwaltungdeinheit
        * Leiter der Regierung
        * etc.
* Co-occurring topics map
    * Location geotags for each topic
    * Displayed on maps
    * ?location ?locationLabel
    * ?geo
    * ?example_work ?example_workLabel
* Author score
    * Authors scored according to field of work, publications within the topic and citing works within the topic.
    * Displays a weighted bubble with the Authors name
    *  ?score ?author ?authorLabel
    * ?cited_work wdt:P50 ?author .
* Author score Table
    * Score
    * Author name and scholia page link
    * Example work title and scholia page link 
* Venues and series publishing works about the topic
    * ?count ?short_name ?venue ?venueLabel ?work
    * Count
    * Short name for Venue (e.g. PLOS NTDs)
    * Venue with scholia page link (e.g. PLOS Neglected Tropical Diseases) 
* Work cited from works on the topic
    * ?count ?cited_work ?cited_workLabel ?work
    * Count
    * Cited work (its title and link to scholia page) 
    * Intends to show the most cited works for the given topic. 
* Authors cited from works on the topic
    * ?number_of_citations ?author ?authorLabel ?cited_work_example ?cited_work_exampleLabel
    * ?author ?work ?cited_work
    * Number of citations
    * Author name and link to scholia page
    * Cited work example 
        * Article name by author and link to scholia page 

## Prize/Award Pages: 
(Example: [Jorck's Prize](https://tools.wmflabs.org/scholia/award/Q27864180) ([Q27864180](https://www.wikidata.org/wiki/Q27864180)))
### Representations of data: 
* List of recipients
    * ?year
    * ?recipient ?recipientLabel 
    * ?example_work ?example_workLabel
    * ?award_statement ?time ? work
    * Year
    * Recipient name and link to their scholia page
    * Example work 
        * Title and scholia page link for given article 
* Images of recipients
    * ?year
    * ?recipient ?recipientLabel 
    * ?image
    * ?award_statement
* Topics of works by recipients
    * The most popular topic for recipients of award 
    * ?count ?topic ?topicLabel 
    * ?work ?count ?recipient
* Recent publications by recipients
    * Publication date
    * The name and scholia link of the published work
    * Recipient name and scholia link
* Co-awards
    * ?number_of_corecipients ?award ?awardLabel ?recipient 
    * Not always available 
* Location of recipients
    * Shows locations on map of the recipients
    * ?recipient ?recipientLabel ?image ?item ?itemLabel ?geo ?layer
    * ?property_item_label ?property ?property_item 
* Gender distribution
    * ?count ?gender ?genderLabel 
    * ?recipient ?gender
    * Show how many women and men have won the award respectively 

# Comparisons: 
## Organizations: 
([Example](https://tools.wmflabs.org/scholia/organizations/Q1269766,Q193196))
* The Organizations being compared:
    * Their name and scholia page links
    * Description (e.g. University)
    * Location (Name and scholia page link for location) 
    * Country Name and scholia page link
* Co-authorships
    * Name and scholia link for Author 1 
    * Name and scholia link for Author 2
    * Work they both worked on
        * Name and scholia link for the given work
    * ?author1 ?author1Label ?author2 ?author2Label ?work ?workLabel 
    * ?organization1 ?organization2
* Works per year
    * Line graphs comparing the number of works published over time between the two organizations 
    * ?year (COUNT(?work) AS ?number_of_works) ?organization ?organizationLabel 
* Citations per year
    * Line graphs comparing the amount of citations of works from each organization over time
    * ?year_of_citation
    * ?number_of_citations
    * ?organization ?organizationLabel  
    * ?citing_work ?publication_date
* Citations to works ratio
    * The ratio between the number of citations received and the works authored per organization per year.
    * (?year_of_citation AS ?year)
    * (?number_of_citations/?number_of_works AS ?citations_to_works_ratio)
    * ?number_of_works
    * ?number_of_citations
    * ?organization ?organizationLabel  
    * ?citing_publication_date
* Topics
    * Tree map of most common topics in works authored by people associated with the organizations
    * ?number_of_works
    * ?topic ?topicLabel
    * ?organization ?organizationLabel  
* Topics Table
    * Number of works 
    * For the given Topic name and scholia page link
    * The associated Organization and its scholia page link

## Authors: 
* List of Authors being compared
    * Author name and scholia page link
    * Description (e.g. prof, of Semantic Web tech) 
    * Example work
        * Name and scholia page link to given article
* List of common authored works
    * List of works in which the chosen authors were co-authors
    * Co-author count
    * Work
        * Name and scholia link to topic page
    * Name of Authors
    * ?coauthor_count ?work ?workLabel ?authors
* Number of works per publication year
    * It shows bar graphs comparing the amount each author published in each given year
    * ?year ?number_of_works ?author ?author_label
    * ?publication_date
* Number of citations per publication year
    * Compares how often each author is cited for their work in other works over time
    * ?year ?number_of_citations ?author ?author_label
    * ?work ?publication_date
* Co-author graph
    * ?author ?authorLabel ?work ?workLabel 
    * It shows how works all authors worked on connect to each other 
    * It also indicates additional co-authors not part of the comparison 
    * E.g. Tim Berners-Lee connects the other two authors as he worked with both, but they never worked together on their own.

# Notes: 
* Any information available in graphs is taken from the Wikidata database
    * As such it might not need to be added by Team #1
    * The information available also depends on type of data e.g Person, country, topic etc. which changes the information displayed in the graph 
* Locations and Countries are displayed using the Topic template 
