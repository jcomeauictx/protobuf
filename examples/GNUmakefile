# for helping python tests run "out of the box"
REPO := $(dir $(PWD))
PROTO_PATH ?= --proto_path $(PWD):$(REPO)src/
PYTHONPATH ?= $(REPO)conformance:$(REPO)python:$(PWD)
PYTHON_SOURCES := $(wildcard *.py)
export
env:
	$@
$(REPO)python/google/protobuf/timestamp_pb2.py:
	cd $(REPO)conformance && make
%.run: % $(REPO)python/google/protobuf/timestamp_pb2.py
	./$(@:.run=)
pyshell:
	python
%: Makefile
	$(MAKE) -f $< $@
