.DEFAULT_GOAL := image

# Generates a help message. Borrowed from https://github.com/pydanny/cookiecutter-djangopackage.
help: ## Display this help message
	@echo "Please run \`make <target>\` where <target> is one of"
	@perl -nle'print $& if m{^[\.a-zA-Z_-]+:.*?## .*$$}' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m  %-25s\033[0m %s\n", $$1, $$2}'

debug: ## Run and attach to container for debugging
	docker run -it --env-file .docker/env edx/repair

image: ## Build an edx/repair image
	docker build --tag edx/repair:latest .

run: ## Start a container derived from the edx/repair image
	docker run --env-file .docker/env edx/repair
