default: test
include ../../../helpers/examples.mk

RELEASE := helm-kibana-default

GOSS_CONTAINER := $(shell kubectl get pods -l release=$(RELEASE) -o name | awk -F'/' '{ print $$NF }')

install:
	helm upgrade --wait --timeout=600 --install $(RELEASE) ../../ ; \

test: install goss

purge:
	helm del --purge $(RELEASE)
