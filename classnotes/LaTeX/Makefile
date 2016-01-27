## Arkye's LaTeX Structure Makefile ##

# Output Name
TARGET = JonathanMoraes_Physics_ClassNotes_03

# LaTeX Project Settings
MAIN_DIR = daily_notes/01_27
MAIN_NAME = main
MAIN_FILE = main.tex

# Project Files Directories
OUTPUT_DIR = $(MAIN_DIR)/output/
SOURCES_DIR = $(MAIN_DIR)/sources/
HEADERS_DIR = headers/

# Project Files Tracking
SOURCES_FILES = $(foreach dir,$(SOURCES_DIR),$(wildcard $(dir)*.tex))
HEADERS_FILES = $(foreach dir,$(HEADERS_DIR),$(wildcard $(dir)*.tex))

# All Files From Project
ALL_FILES = $(MAIN_FILE) $(SOURCES_FILES) $(HEADERS_FILES)

# Compilation Settings
LATEX_COMMON = latexmk -pdf
LATEX_SILENT = latexmk -pdf -silent
LATEX_QUIET = latexmk -pdf -quiet
LATEX = $(LATEX_COMMON)
#LATEX = $(LATEX_SILENT)
#LATEX = $(LATEX_QUIET)
PDF_FILE = $(OUTPUT_DIR)$(TARGET).pdf


# All Settings
ALL_DIR = daily_notes
ALL_NAME = all
ALL_FILE = all.tex
ALL_TARGET = JonathanMoraes_Physics_ClassNotes
OUTPUT_ALL_DIR = $(ALL_DIR)/
SOURCES_ALL_DIR = $(ALL_DIR)/
ALL_SOURCES_FILES = $(foreach dir,$(SOURCES_ALL_DIR),$(wildcard $(dir)*.tex))
ALL_ALL_FILES = $(ALL_FILE) $(ALL_SOURCES_FILES) $(HEADERS_FILES)
ALL_PDF_FILE = $(OUTPUT_ALL_DIR)$(ALL_TARGET).pdf

.PHONY: all

all:
	make -s $(TARGET).pdf

total:
	make -s $(ALL_TARGET).pdf

$(TARGET).pdf: $(ALL_FILES)
	$(LATEX) $<
	@mv $(MAIN_NAME).pdf $(PDF_FILE)
	make -s clean

$(ALL_TARGET).pdf: $(ALL_ALL_FILES)
	$(LATEX) $<
	@mv $(ALL_NAME).pdf $(ALL_PDF_FILE)
	make -s clean

clean:
	rm -f *.aux *.log *.fdb_latexmk *.fls *.out
