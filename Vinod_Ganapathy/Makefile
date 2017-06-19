# Makefile for the dissertation.

TEXSRC=$(shell find . |grep tex)
FIGSRC=$(shell ls figures/pdf/*.pdf figures/fig/*.fig)
MISCSRC=$(shell ls styles/*.sty bib/references.bib)

default: pdf 

all: pdf pdfbm

pdf: phd-diss.pdf

ps: phd-diss.ps

pdfbm: phd-diss.pdf

web: phd-diss.pdf
	cp phd-diss.pdf /u/v/g/vg/public/html/.

# Use this to produce PDFs with bookmarks.
phd-diss.pdf: $(TEXSRC) $(FIGSRC) $(MISCSRC)
	cd figures; make; cd -
	pdflatex phd-diss
	bibtex phd-diss
	pdflatex phd-diss
	pdflatex phd-diss
	rm -f *.log *.aux *.blg *.cb *.out *.bbl *.lof *.lot *.toc \
		chapters/abstract/*.aux \
		chapters/prelude/*.aux \
		chapters/introduction/*.aux \
		chapters/overview/*.aux \
		chapters/fingerprints/*.aux \
		chapters/dynamic-mining/*.aux \
		chapters/static-mining/*.aux \
		chapters/matching/*.aux \
		chapters/limitations/*.aux \
		chapters/relatedwork/*.aux \
		chapters/conclusions/*.aux \
		chapters/appendix/*.aux \
	
phd-diss.ps: phd-diss.pdf
	pdftops phd-diss.pdf
	
clean:
	cd figures; make clean; cd -
	rm -f stdout stderr;
	rm -f *.cb *.bak *.bbl *.blg *.log *.aux *.ps *.dvi *.pdf *.out \
		chapters/*.bak chapters/*.aux *.lof *.lot *.toc \
		chapters/abstract/*.bak \
		chapters/prelude/*.bak \
		chapters/introduction/*.bak \
		chapters/overview/*.bak \
		chapters/fingerprints/*.bak \
		chapters/dynamic-mining/*.bak \
		chapters/static-mining/*.bak \
		chapters/matching/*.bak \
		chapters/limitations/*.bak \
		chapters/relatedwork/*.bak \
		chapters/conclusions/*.bak \
		chapters/appendix/*.bak 
