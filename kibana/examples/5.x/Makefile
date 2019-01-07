default: test
include ../../../helpers/examples.mk

RELEASE := helm-kibana-fivex

GOSS_CONTAINER := $(shell kubectl get pods -l release=$(RELEASE) -o name | awk -F'/' '{ print $$NF }')

install:
	helm upgrade --wait --timeout=600 --install --values ./values.yml $(RELEASE) ../../ ; \
	
purge:
	helm del --purge $(RELEASE)

test: install goss
