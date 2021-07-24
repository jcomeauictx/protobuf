# for helping python tests run "out of the box"
REPO := $(dir $(PWD))
PROTO_PATH ?= --proto_path $(PWD):$(REPO)src/
PYTHONPATH ?= $(PWD):$(REPO)python:$(REPO)conformance
PYTHON_SOURCES := $(wildcard *.py)
export
env python:
	$@
$(REPO)python/google/protobuf/timestamp_pb2.py:
	cd $(REPO)conformance && make
%.run: % $(REPO)python/google/protobuf/timestamp_pb2.py
	./$(@:.run=)
%: Makefile
	$(MAKE) -f $< $@
