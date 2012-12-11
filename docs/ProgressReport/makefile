FILE = ProgressReport
TEXFILE = "$(FILE).tex"

all:
	pdflatex $(TEXFILE)
	bibtex $(FILE)
	pdflatex $(TEXFILE)
	pdflatex $(TEXFILE)
	makeindex $(FILE).nlo -s nomencl.ist -o $(FILE).nls
	pdflatex $(TEXFILE)

clean:
	@rm -f *.tdo *.aux *.lof *.log *.lot *.nlo *.nls *.out *.pdf *.toc *.bbl *.blg *.bak *.sav *.ilg
