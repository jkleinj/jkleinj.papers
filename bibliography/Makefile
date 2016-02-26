#===============================================================================
# Makefile to compile Latex document
#===============================================================================

#______________________________________________________________________________
# MACROS
SRCS	= papers_jk
TARGET	= papers_jk

OBJS = $(SRCS:%.tex=%.dvi)

#______________________________________________________________________________
# TARGETS
all: compile dviout pdfout
pdf: compile pdfout
dvi: compile dviout
tex: compile_tex
clean:
	rm -f $(TARGET).aux $(TARGET).bbl $(TARGET).blg $(TARGET).dvi $(TARGET).log $(TARGET).ps $(TARGET).pdf

#______________________________________________________________________________
# COMPILE
compile :
	latex $(SRCS);\
    bibtex $(TARGET);\
    latex $(SRCS);\
    latex $(SRCS);

dviout :
	xdvi $(TARGET).dvi;

pdfout :
	dvips -t a4 -o $(TARGET).ps $(TARGET).dvi;\
	ps2pdf -sPAPERSIZE=a4 $(TARGET).ps $(TARGET).pdf

compile_tex :
	latex  $(SRCS);

