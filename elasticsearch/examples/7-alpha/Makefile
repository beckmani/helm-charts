default: test
include ../../../helpers/examples.mk

GOSS_CONTAINER := seven-master-0

RELEASE := helm-es-seven

install:
	helm upgrade --wait --timeout=600 --install $(RELEASE) --values ./values.yaml ../../ ; \

restart:
	helm upgrade --set terminationGracePeriod=121 --wait --timeout=600 --install $(RELEASE) --values ./values.yaml ../../ ; \

test: install goss

purge:
	helm del --purge $(RELEASE)
