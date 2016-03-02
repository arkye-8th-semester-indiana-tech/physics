## Arkye's LaTeX Structure Makefile ##

# Output Name
TARGET = JonathanMoraes_Physics_HW5

# LaTeX Project Settings
MAIN_DIR = HW5
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

.PHONY: all

all:
	make -s $(TARGET).pdf

$(TARGET).pdf: $(ALL_FILES)
	$(LATEX) $<
	@mv $(MAIN_NAME).pdf $(PDF_FILE)
	make -s clean

clean:
	rm -f *.aux *.log *.fdb_latexmk *.fls *.out
