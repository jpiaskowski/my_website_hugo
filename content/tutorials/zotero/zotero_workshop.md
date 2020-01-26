---
date: "2018-03-18 10:50:02 -0700"
draft: false
linktitle: Using Zotero
menu:
  Zotero:
    name: Using Zotero
    weight: 2
title: Using Zotero
toc: true
type: docs
weight: 1
---


### Installation

Step 1: install [**Zotero**](https://www.zotero.org/download/). It now comes automatically bundled with an extension for inserting citations into Microsoft Word and Libre Writer.

Once installed, you should be able to open Zotero and see this:

![zotero](zotero.png)

You should also consider creating an [**online account**](https://www.zotero.org/user/register/) so your local library can sync with the cloud service. This is free. You can link the Zotero app to your account under "Zotero" > "Preferences":

![zotero sync](zotero_sync.png)

The Zotero tab should be present on Microsoft Word. This works on Windows and Mac versions, and it also works with Libre Office.

![zotero_cwyw](Word_zotero.png)

There is also a large number of [**plugins**](https://www.zotero.org/support/plugins) to consider.

### Adding references
#### Formats

Many journals provide options for direct import of a reference into. NCBI, Springer, ASA-CSSA-SSSA and many more are quite good at this.

Often many formats are offered, each specifc to a particular software. If you see an option for Zotero, clearly that will work fine for importation. Otherwise, a plain .RIS file is the best option. I often choose "RefWorks" as the format for that program is compatible with Zotero.

#### Importing References
* Example: _Springer_.  [Mapping of a major gene for the slow ripening character in peach: co-location with the maturity date gene and development of a candidate gene-based diagnostic marker for its selection](https://link.springer.com/article/10.1007/s10681-015-1445-9)
* Example: _NCBI_.  [QTL analysis of quality traits in an advanced backcross between Prunus persica cultivars and the wild relative species <i>P. davidiana</i>](https://www.ncbi.nlm.nih.gov/pubmed/15168024)
* Example: _PMC Full text_.  [The impact of genetic relationship information on genome-assisted breeding values](https://www.ncbi.nlm.nih.gov/pubmed/18073436)
* Example: _ASHS_.  [Variability in sugars, acids, firmness, and color characteristics of 12 peach genotypes](http://journal.ashspublications.org/content/116/6/1004.abstract)
* Example: _Multiple References_.  [Fixed-length haplotypes can improve genomic prediction accuracy in an admixed dairy cattle population](https://gsejournal.biomedcentral.com/articles/10.1186/s12711-017-0329-y)

#### Manual Addition

A references can always be entered by hand under "File" > "New Item". This is laborious and likely to result in errors, so I do not recommend it. However, sometimes there is no choice.

PDFs and other attachments are usually added manually. Use the paperclip icon to attached local files. An exception is importing an existing library.

#### Other Reference Types

Zotero offers many reference types. The default item type used by Zotero (and scientists) is "Journal Article". However, there are a number of other types to consider. Here is a sampling of other commonly-used item types:

 * **Book or Book Section**

 ![zotero_book](zotero_book.png)

 ![zotero_bookSec](zotero_book_section.png)


 * **Dissertation**

 ![zotero_dissertation](zotero_dissertation.png)


 * **Conference Paper**

 ![zotero_conf_paper](zotero_conference_paper.png)


 * **Webpage**

 ![zotero_webpage](zotero_webpage.png)

Using these different types enables users to capture the information essential to the particular reference. For citation purposes, journals have developed a set of formatting guidelines for each reference type. By using the correct reference type, references are more likely to be properly formatted within documents.

#### Editing References

Regardless of how references are added, all references should be inspected once to ensure all elements are as expected. Sometimes, article titles or author names are in all caps. Often, each word in an article title is capitalized. Occasionally, the abstract and title are merged, making for an epically long title. For books, editors may not be included or may be improperly labelled. The citation manager will not be able to correct these issues - it is up to users to do this.

The most notable drawback to Zotero is that you will lose italics. This can be ignored in abstracts, but if you plan on citing an article with an italicized word in the title, it is best to fix this. To do so, flank the italized text in the following html code:

```
<i> your italicized text </i>
```
Which will look like this after inserted into a list of references:
<i> your italized text </i>

Journal names are not always standardized. This can sometimes be ignored since the Medline abbreviations are used. For example, here are several variations in name of a reputable journal commonly called "PNAS":

 * PNAS
 * PNAS USA
 * Proc Natl Acad Sci
 * Proc Natl Acad Sci USA
 * Proc. Natl Acad. Sci. USA
 * Proceeding of the National Academy of Sciences
 * Proceedings of the National Academy of Sciences

### Manipulating Zotero

For dedicated users, a reference library can become quite large and unwieldy. Hence knowelge on how to organize, filter and search a library are essential to taking full advantage of the information stored in personal or shared reference library.

#### Organize References into Collections
References can be organized into many collections. Collections or subcollections can be created by right clicking within the left menu and choosing the appropriate option. References are added to collections by highlighting and dropping and dragging them to the appropriate collection. References can belong to multiple collections. Collections are not hierarchical: membership in a subcollection does not guarantee membership in the higher collection.

Group collections are a shared resource. These are created on the Zotero website and other zotero users can be invited to join. These can be private or public.

#### Finding References
You can sort references by several of the fields in the references: date, title author, date added, attachments. References can be searched with the search bar by "everything" or "all fields and tags" or "Title, creator, date". Tags are the equivalent of "keywords" used in classifying journal articles. Searches can also be restricted to within collections.

<img src="zotero_filter.png" alt="zotero_filter" style="width: 450px;"/>
 ![zotero_filter](/zotero_filter.png)

### Citations

Automated citation management is perhaps the most useful aspects of a reference software. With Zotero, it's also very easy to use.

First, you need to install the desired citation style. Major journals have made their styles available on the [**Zotero Style Repository**](https://www.zotero.org/styles). To download one, you can directly download it from the Zotero style repository webpage and import into Zotero. Alternatively, Zotero provides an option directly in their user interface through "Zotero" > "Preferences" > "Cite":

<img src="zotero_styles.png" alt="zotero_styles" style="width: 450px;"/>
 ![zotero_styles](zotero_styles.png)

**Inserting and Editing References**

Open a word document and try to insert a reference where your cursor is located in the document with "Add/Edit Citation". It will prompt you to choose a style the first time you do this.

To change the content in a single group of references, place your cursor in the reference and click "Add/Edit Citation". You can delete and/or add references.

References can be moved around as whole text or deleted entirely like any normal document text. Zotero will automatically detect their removal and update the bibliography.

Users may want to cite papers as such: "Coombe (1976) found that...". In this example, the default format "Coombe (Coombe 1976) found that..." is incorrect. To remove the author name from the citation, choose "classic view" from the dropdown menu:

![zotero_webpage](zotero_dropdown.png)

and click "suppress author":

![zotero_author](zotero_author.png)

**Adding a Bibliography**

To add a list of ordered cited works to a document, place your cursor where you would like the reference list inserted and click "Add/Edit Bibliography". This can be added and deleted repeatedly if needed.

The button "Document Preferences" can be used to change the citation style across the entire document if needed.

Note that the bibliography formatting will default to the text type defined for the block (usually "normal"). If you want it to look different (smaller, different font, etc), you will have to redefine that block or the elements of that type.

**Unlink Citations**

This will remove all links between references, so be careful using this button, as you will have to manually edit references from this point forward. It is probably best to copy your document first.

### Troubleshooting

**For some reason, normal journals are being formatted as webpages.**
This can happen if the URL field is filled out. Delete or move that content for the references in question.

**I accidentially added the wrong PDF to the article.**
Duplicate the reference within Zotero, delete the old reference and add the correct attachment.

**Oh snap - my whole library was wiped. What should I do?**
You should back it up from this point forward. [**Here are some instructions**](https://www.zotero.org/support/zotero_data). There are some [**file recovery tools**](https://www.techradar.com/news/the-best-free-data-recovery-software) for individual systems. There is also a [**Zotero plugin**](https://rintze.zelle.me/ref-extractor/) for pulling references out of your papers.

**I accidentially imported all references from a single article rather than only the citation for that article.**
Sort the references from the date added and remove all those added at that particular time stamp.

**I think there are tons of duplicates in my library - how can I fix this?**
Zotero has a feature for removing duplicates. Look on the left menu for "Duplicate Items" to clean those up.

**Help! I'm having some mystery issue that no one has ever experienced.**
Zotero has a huge userbase who take advantage of the [**forums**](https://forums.zotero.org/discussions) for troubleshooting. If you cannot find your solution there, then post your problem, and the community is likely to help you.
