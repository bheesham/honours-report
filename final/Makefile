STYLE:= carleton/titlepage.sty \
	carleton/abstract.sty carleton/acks.sty \
	carleton/tocandlists.sty

document.pdf: document.tex $(STYLE)
	-pdflatex document && bibtex document
	-pdflatex document
	-makeindex -s document.ist -o document.gls document.glo
	-pdflatex document
	-pdflatex document

spell: document.tex
	aspell -t -c document.tex

clean:
	rm -f *.aux *.bak *.blg \
	      *.bbl *.dvi *.idx \
	      *.ist *.gls *.glo \
	      *.lof *.log *.lot \
	      *.out *.toc document.pdf

.PHONY: clean spell 

