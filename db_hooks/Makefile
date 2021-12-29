SHELL=/bin/bash


setup:
	python -m venv venv && ./venv/bin/pip install -r requirements.txt && ./venv/bin/pip install -e .

install_kernel:
	./venv/bin/python -m ipykernel install --user --name db_hooks

format:
	./venv/bin/black ./db_hooks

lint:
	./venv/bin/flake8 ./db_hooks

clear:
	rm -rf build
	rm -rf dist

package:
	./venv/bin/python setup.py check
	./venv/bin/python setup.py sdist
	./venv/bin/python setup.py bdist_wheel --universal

upload:
	./venv/bin/twine upload dist/*
