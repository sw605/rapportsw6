TEX:=$(shell ls *.tex)
OTHER = *~ *.aux *.dvi *.toc *.bbl *.blg *.gz *.out *.thm *.ps *.idx *.ilg *.ind *.tdo *.cb *.cb2 *.lot *.soc *

pdflatex: master.tex
	pdflatex --synctex=1 master.tex
	bibtex master
	pdflatex --synctex=1 master.tex
	pdflatex --synctex=1 master.tex
	pdflatex --synctex=1 master.tex
	
fast: master.tex
	pdflatex --synctex=1 -interaction batchmode master.tex
	bibtex master
	pdflatex --synctex=1 -interaction batchmode master.tex
	pdflatex --synctex=1 -interaction batchmode master.tex
	pdflatex --synctex=1 -interaction batchmode master.tex
	
clean:
	git clean -x -f -e master.pdf

live: clean
	latexmk -pvc -pdflatex='pdflatex -file-line-error -synctex=1' -pdf master.tex