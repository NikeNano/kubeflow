SHELL=bash

install-deps:
	pushd ../../../py && \
	pip install -e . && \
	popd
	pip install -r requirements.txt

run:
	APP_PREFIX=/volumes \
	gunicorn -w 3 --bind 0.0.0.0:5000 --access-logfile - entrypoint:app

run-rok:
	UI_FLAVOR=rok \
	APP_PREFIX=/volumes \
	gunicorn -w 3 --bind 0.0.0.0:5000 --access-logfile - entrypoint:app

run-dev:
	UI_FLAVOR=default \
	BACKEND_MODE=dev \
	APP_PREFIX=/ \
	gunicorn -w 3 --bind 0.0.0.0:5000 --access-logfile - entrypoint:app

run-dev-rok:
	UI_FLAVOR=rok \
	BACKEND_MODE=dev \
	APP_PREFIX=/ \
	gunicorn -w 3 --bind 0.0.0.0:5000 --access-logfile - entrypoint:app
