DOEIFY ?= ../bin/doeify

SAMPLES ?= 12

INFILE ?= test.dat

METHODS = full_fact frac_fact plackett_burman sukharev box_behnken central_composite lhs space_filling_lhs random_k_means maximin halton uniform_random

RESULTSFILES = $(addsuffix .out, $(METHODS))

all: $(METHODS)

$(METHODS): %: %.out

full_fact.out frac_fact.out plackett_burman.out: $(INFILE)
	$(DOEIFY) --infile=$< --outfile=$@ --method=$(basename $@) --plot=$(patsubst %.out,%.png,$@)

space_filling_lhs.out random_k_means.out maximin.out halton.out uniform_random.out: $(INFILE)
	$(DOEIFY) --infile=$< --outfile=$@ --method=$(basename $@) --plot=$(patsubst %.out,%.png,$@) --samples=$(SAMPLES)

lhs.out: $(INFILE)
	$(DOEIFY) --infile=$< --outfile=$@ --method=$(basename $@) --plot=$(patsubst %.out,%.png,$@) --samples=$(SAMPLES) --dist=Normal

sukharev.out: $(INFILE)
	$(DOEIFY) --infile=$< --outfile=$@ --method=$(basename $@) --plot=$(patsubst %.out,%.png,$@) --samples=27

box_behnken.out: $(INFILE)
	$(DOEIFY) --infile=$< --outfile=$@ --method=$(basename $@) --plot=$(patsubst %.out,%.png,$@) --center=1

central_composite.out: $(INFILE)
	$(DOEIFY) --infile=$< --outfile=$@ --method=$(basename $@) --plot=$(patsubst %.out,%.png,$@) --center='(2,2)' --alpha=o --face=ccc

clean:
	$(RM) $(RESULTSFILES) $(patsubst %.out,%.png,$(RESULTSFILES))

.PHONY: all $(METHODS) clean
