# CrateDB tableau's connector.
[![Validate and Release connector](https://github.com/crate/cratedb-tableau-connector/actions/workflows/tests_and_release.yml/badge.svg)](https://github.com/crate/cratedb-tableau-connector/actions/workflows/tests_and_release.yml)
![GitHub Release](https://img.shields.io/github/v/release/crate/cratedb-tableau-connector)
![Static Badge](https://img.shields.io/badge/tdvt_compatibility-81%25-brightgreen?style=flat&logo=cratedb)
![Static Badge](https://img.shields.io/badge/CrateDB-5.10.1-brightgreen?style=flat&logo=cratedb)

For simple queries and graphs, you can use the default PostgresSQL connector,
but for more advance usage SQL compatibility issues and nuanced SQL functionalities get into play,
we circumvent/fix those limitations with our custom connector.

## How to use.

You will need two things:

The `postgresql jdbc driver` and the `cratedb` connector..

### Get the Postgresql jdbc driver.

Download the driver from [here](https://jdbc.postgresql.org/download/) and put it in:

- Windows: `C:\Program Files\Tableau\Drivers`
- Mac: `~/Library/Tableau/Drivers`
- Linux: `/opt/tableau/tableau_driver/jdbc` 

The latest PostgreSQL jdbc tested driver is `postgresql-42.7.4.jar`.

The latest CrateDB jdbc tested driver is `cratedb-jdbc-standalone-2.7.0`

Note: `postgresql-42.7.5.jar` does not seem to work.

### Get the CrateDB connector.

You can find the connector in the [release section.](https://github.com/crate/cratedb-tableau-connector/releases)

Put it in: 

#### Tableau Desktop

- Windows: `C:\Users\[Windows User]\Documents\My Tableau Repository\Connectors`
- MacOS: `/Users/[user]/Documents/My Tableau Repository/Connectors`

#### Tableau Prep Builder

- Windows:  `C:\Users\[Windows User]\Documents\My Tableau Prep Repository\Connectors`
- MacOS: `/Users//Documents/My Tableau Prep Repository/Connectors`

#### Tableau Server
- Windows: `C:\Program Files\Tableau\Connectors`
- Linux: `/opt/tableau/connectors`

For older versions see https://help.tableau.com/current/pro/desktop/en-us/examples_connector_sdk.htm

## Disabling signature verification.

The current release of the connector is not signed. This issue is being addressed, but in the meantime, verification can be disabled.

* On _Tableau Desktop_, please use this command-line argument: `-DDisableVerifyConnectorPluginSignature=true`

* On _Tableau Server_, you can disable signature verification by setting `native_api.disable_verify_connector_plugin_signature` to `true` via TSM.

More information can be found [here](https://tableau.github.io/connector-plugin-sdk/docs/run-taco)


## State of the driver.

This custom connector aims to offer the best Tableau experience possible, this is a work in progress since 
PostgresSQL compatibility is not 100% and is bound to change over time.

We test compatibility issues with Tableau's connector sdk: [TDVT suite](https://tableau.github.io/connector-plugin-sdk/docs/tdvt).
Progress is tracked in https://github.com/crate/cratedb-tableau-connector/issues/2