# AXE Ninja Back-End (axeninja-be)

This is part of what makes the AXE Ninja monitoring application.
It contains:
- Private REST API (using PHP and Phalcon framework)

## Requirement:
* You will need a running website, official at https://axeninja.pl uses nginx

For the REST API:
* PHP v5.6 with mysqli
* Phalcon v2.0.x (should work with any version)
* MySQL database with AXE Ninja Database (check axeninja-db repository)

## Optional:
* AXE Ninja Control script installed and running (to feed the database through this API)

## Install:
* Go to the root of your website for AXE private API (ex: cd /home/axeninja/cmd/)
* Get latest code from github:
```shell
git clone https://github.com/axerunners/axeninja-be.git
```

* Configure php to answer only to calls to api/index.php rewriting to end-point api/

## Configuration:
The initial idea was to be able to have a central application (axeninja-be) where one or several hub of nodes connect to in order to provide monitoring.

Current implementation takes as assumption that there is only one hub configured (there can be several nodes).

Identification of this app and possible hubs are done with SSL certificates and it was designed to run on IPv6 only.
You need to configure your web server (AXE Ninja official uses nginx) with your CA and create client certificates to trusted hubs to connect to it.

Once the server is configured correctly import the client certificate CN into cmd_hub to give access to that hub (this can be a remote host or ::1). Both the certificate and IPv6 are checked to match and give access.

Rest of documentation is not done yet (if ever).

_Based on Dash Ninja by Alexandre (aka elbereth) Devilliers_
