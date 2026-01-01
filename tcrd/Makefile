##-*- makefile -*-############################################################
#
# Copyright (C) 2026 MicroEmacs User.
#
# All rights reserved.
#
# Synopsis:    
# Authors:     MicroEmacs User
#
##############################################################################

CURRENT_MAKEFILE := $(lastword $(MAKEFILE_LIST))

## argument delegation
ARGS=

## default: list existing tasks 
.PHONY: tasks
tasks:  ## list all tasks
	@grep -Eo '^[a-z0-9]+:.+' $(CURRENT_MAKEFILE) | sed -E 's/:\s+##/\t- /g'

docu:   ## create documentation
	mndoc tcrd.tcl tcrd.tmd
	TCLLIBPATH=../ tmdoc tcrd.tmd - --toc true | mndoc - tcrd.html --css tmdoc.css
test:   ## run tests
	tclsh tcrd.test
