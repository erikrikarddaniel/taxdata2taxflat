DIFF = grep -v "^[ ]*$$" $@.out | diff $@.expect -

CHECK = if [ ` $(DIFF) | wc -l ` -eq 0 ]; then echo "*** $@ OK ***"; else echo "*** $@ FAILED ***"; echo "Here's a diff: "; $(DIFF); exit 1; fi

all: taxdata2taxflat

taxdata2taxflat: taxdata2taxflat.00

taxdata2taxflat.00:
	@../../src/ruby/taxdata2taxflat $@.nodes.dmp $@.names.dmp > $@.out
	@$(CHECK)
