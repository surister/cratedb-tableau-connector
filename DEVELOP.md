# How to set up tests.

## 1. Install tableau desktop.
Tests need a valid Tableau desktop installation (either Windows or mac) https://www.tableau.com/support/releases, and
hence a valid tableau license. Without a license tests cannot be run.


## 2. Clone the repository
sh
git clone git@github.com:crate/cratedb-tableau-connector.git


## 3. Install poetry.
It is expected that you have a valid python installation.

sh
pipx install poetry


Check that poetry is properly installed by running

sh
poetry


In Windows systems you might need to call poetry with:
sh
python3 -m poetry


## 4. Install the poetry environment