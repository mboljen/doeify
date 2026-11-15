DOEIFY  := ../bin/doeify

SAMPLES ?= 12

INFILE  ?= test.dat

METHODS = full_fact frac_fact plackett_burman sukharev box_behnken central_composite lhs space_filling_lhs random_k_means maximin halton uniform_random

default: $(METHODS)

full_fact:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@)

frac_fact:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@)

plackett_burman:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@)

sukharev:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --samples=27

box_behnken:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --center=1

central_composite:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --center='(2,2)' --alpha=o --face=ccc

lhs:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --samples=$(SAMPLES) --dist=Normal

space_filling_lhs:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --samples=$(SAMPLES)

random_k_means:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --samples=$(SAMPLES)

maximin:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --samples=$(SAMPLES)

halton:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --samples=$(SAMPLES)

uniform_random:
	$(DOEIFY) --infile=$(INFILE) --outfile=$(addsuffix .out, $@) --method=$@ --plot=$(addsuffix .png, $@) --samples=$(SAMPLES)

clean:
	$(RM) $(addsuffix .png, $(METHODS)) $(addsuffix .out, $(METHODS))

.PHONY: default clean
