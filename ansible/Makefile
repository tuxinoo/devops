.PHONY: env
env-desc = "Setup local dev env"
env:
	@echo "==> $(env-desc)"

	@[ -d "${PWD}/.direnv" ] || (echo "Venv not found: ${PWD}/.direnv" && exit 1)
	@pip3 install -U pip wheel setuptools --no-cache-dir && \
	echo "[  OK  ] PIP + WHEEL + SETUPTOOLS" || \
	echo "[FAILED] PIP + WHEEL + SETUPTOOLS"

    ifeq ($(wildcard "${PWD}/requirements.txt"),) 
		@pip3 install -U --no-cache-dir -r "${PWD}/requirements.txt" && \
		echo "[  OK  ] PIP REQUIREMENTS" || \
		echo "[FAILED] PIP REQUIREMENTS"
    endif 

    ifneq ("$(wildcard ${PWD}/requirements.yml)","")
		@ansible-galaxy collection install -c -fr ${PWD}/requirements.yml && \
		echo "[  OK  ] ANSIBLE-GALAXY REQUIREMENTS" || \
		echo "[FAILED] ANSIBLE-GALAXY REQUIREMENTS"
    endif 
