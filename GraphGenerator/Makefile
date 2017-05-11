# ====================================================================
#   "Mixed Finite Element Methods for Coupled 3D/1D Fluid Problems"
#      Course on Advanced Programming for Scientific Computing
#                     Politecnico di Milano
#                         A.Y. 2014-2015
#
#                    Copyright D. Notaro 2015
# ====================================================================
#   FILE        : Makefile
#   DESCRIPTION : makefile for test simulations
#   AUTHOR      : Domenico Notaro <domenico.not@gmail.com>
#   DATE        : November 2015
# ====================================================================

.PHONY: all doc clean distclean library exec1 

all: library
#	$(MAKE) -C src/1_uncoupled


library: 
	$(MAKE) -C include
	$(MAKE) -C src/SingleBranch

doc:
	install -d doc
	doxygen Doxyfile
	
exec1: all
	makedir vtk -C src/1_uncoupled
	./M3D1D input.param

pdf: doc
	$(MAKE) -C doc/latex pdf

clean:
	$(RM) -r *~ *.log
	$(MAKE) -C include clean
#	$(MAKE) -C src/1_uncoupled clean

distclean: clean
	$(RM) -r doc/*
	$(MAKE) -C include distclean
#	$(MAKE) -C src/1_uncoupled distclean
