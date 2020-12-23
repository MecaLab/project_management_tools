# packaging

## generation des distrib pour pypi
# install the dedicated tools
python -m pip install --user --upgrade setuptools wheel
# then create the distribution
python setup.py sdist bdist_wheel
# create another env for uploading to pypi
conda create --name pypi python=3.6
conda activate pypi
conda install twine

# then upload the distribution with this env pypi
cd /mnt/data/work/python_sandBox/slam/
python -m twine upload --repository pypi dist/*
