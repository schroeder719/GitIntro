cc=g++
gccargs = 
package = HelloWorld 
version = 1.0
tarname = $(package)
distdir = $(package)-$(version)

sources=hw.c

all procom:$(sources)
	$(cc) $(gccargs) $(sources) -o  $(package)

debug: procom_debug

procom_debug: $(sources)
	$(cc) -DDEBUG=1 $(sources) -o $(package) -ggdb  

dist: $(distdir).tar

$(distdir).tar: $(distdir)
	tar chof $@ $(distdir) 
	rm -rf $(distdir)

$(distdir):
	mkdir -p $(distdir)
	cp Makefile $(distdir)
	cp $(sources) $(distdir)
	cp AUTHORS $(distdir)

clean:
	rm -f *o
	rm -f *.h.gch

cleanall:
	rm -f *o
	rm -f *a

.PHONY: all debug dist clean cleanall
