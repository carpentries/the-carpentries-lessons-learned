# The Carpentries: Lessons Learned

What we have learned from delivering 3,100 workshops to over 80,000 researchers worldwide since 2010.

Contributors:

- Tim Dennis
- [Jonah Duckles](https://jduck.net)
- [Kari Jordan](http://kariljordan.com/)
- [Lex Nederbragt](https://lexnederbragt.com/)
- Maneesha Sane
- [Aleksandra Nenadic](https://github.com/anenadic)
- [Greg Wilson](http://third-bit.com/)

## Notes

- See [this article](https://f1000research.com/articles/3-62) for an earlier summary.
- See also:
  - [Data Carpentry: Workshops to Increase Data Literacy for Researchers](http://ijdc.net/index.php/ijdc/article/view/10.1.135)
  - [Building a local community of practice in scientific programming for life scientists](https://journals.plos.org/plosbiology/article/authors?id=10.1371/journal.pbio.2005561)

## Writing and generating the output formats

Writing:
* is done in `paper.md`
* cite references as [@wilson2016Software] (using the CiteKey from `references.bib`)

For the conversion:

* Requirements: [pandoc](https://pandoc.org)
* Optionally: GNU make

For generating the PDF version:

```
pandoc paper.md -o paper.pdf \
    --citeproc --csl plos-computational-biology.csl
```

Generating the `.docx` (Microsoft Word) version:

```
pandoc paper.md -t docx -o paper.docx \
	--bibliography references.bib \
	--citeproc --csl plos-computational-biology.csl \
	--reference-doc PLOS_template.docx
```

Both these can also be achieved using GNU `make`.
