# python-packaging-playground

learn python packaging via [Packaging Python Projects](https://packaging.python.org/tutorials/packaging-projects/)

view example package at <https://test.pypi.org/project/example-pkg-pfeilbr/>

```sh

python3 -m venv .venv
source .venv/bin/activate
mkdir example-pkg-pfeilbr
touch example-pkg-pfeilbr/__init__.py
python3 -m pip install --user --upgrade setuptools wheel
python3 setup.py sdist bdist_wheel
pip install --upgrade pip
pip install wheel
pip install twine
python3 -m twine upload --repository-url https://test.pypi.org/legacy/ dist/*

# testing
mkdir tmp
cd tmp
python3 -m venv .venv
source .venv/bin/activate
pip list
python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps example-pkg-pfeilbr

# to install specific version.  did this because it was using 0.0.1 from a cache
python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps 'example-pkg-pfeilbr==0.0.2'

pip list

# test using package
echo -e "import example_pkg_pfeilbr\nprint(example_pkg_pfeilbr.name)" | python
```

![](https://www.evernote.com/l/AAFV5Z92tLtH4bxLDZj52Ok7WpUvaabNZ4kB/image.png)

![](https://www.evernote.com/l/AAGOtALBRBRHtZgMsWnV1JArEJRyT9SjZQ4B/image.png)

---

# Example Package

This is a simple example package. You can use
[Github-flavored Markdown](https://guides.github.com/features/mastering-markdown/)
to write your content.