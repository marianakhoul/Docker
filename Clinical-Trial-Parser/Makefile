TAG = clinical_trial_parser:20.04.2

img:
	docker build --tag=$(TAG) .

shell:
	docker run --rm -it $(TAG) bash

save:
	docker save $(TAG) | gzip > $(shell echo $(TAG) | sed "s/:/-/").tar.gz
