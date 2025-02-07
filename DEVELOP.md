# How to set up tests.

# Setting up the environment:

## 1. Install tableau desktop.
Tableau test sdk needs a valid Tableau desktop installation (either Windows or MacOs) https://www.tableau.com/support/releases, and
hence a valid tableau license. Without a license tests cannot be run.

Once Tableu Desktop is installed, log in selecting 'tableau cloud'.

## 2. Install tdvt

MacOS
```shell
python3 -m pip install "tdvt @ git+https://github.com/tableau/connector-plugin-sdk/#subdirectory=tdvt"
```

Windows
```shell
py -m pip install "tdvt @ git+https://github.com/tableau/connector-plugin-sdk/#subdirectory=tdvt"
```

Check that the installation was done correctly by running:

```
python -m tdvt.tdvt
```

## 3. Clone ``cratedb-tableau-connector``
```shell
git clone git@github.com:crate/cratedb-tableau-connector.git
```

# Setting up the database and connector:

Now that the environment is set up, we need to also set up the tableau test files and data.