# This repo is still WIP and not ready to be used!!!

# sap-netweaver-control [![Build Status](https://travis-ci.com/redhat-sap/sap-hana-control.svg?branch=master)](https://travis-ci.com/redhat-sap/sap-hana-control)

This role contains control operations for SAP Netweaver based applications (start, stop and restart)

## Requirements

This role is to be executed on a server where a SAP Netweaver based application is installed

## Role Variables

| variable | info | required? |
|:--------:|:----:|:---------:|
|sap_hana_control_sid|SID of the SAP HANA system|yes|
|sap_hana_control_instance_nr|Instance number of the HANA DB on which we want to operate|yes|
|sap_hana_control_function|Function that we want to execute|yes, `Start,` `Stop`, or `Change_Password`|
|sap_hana_control_user|User whose password will be changed|no, only if `sap_hana_control_function=Change_Password`|
|sap_hana_control_current_password|Current password of the user that needs to be changed|no, only if `sap_hana_control_function=Change_Password`|
|sap_hana_new_password|New password for the user to which the current one will be changed|no, only if `sap_hana_control_function=Change_Password`|

## Dependencies
This role has no dependencies

## Example Playbook

```yaml
    - hosts: servers
      roles:
      - role: sap-hana-control
```

## Example Inventory

```yaml
sap_hana_control_sid: "RHE"
sap_hana_control_instance_nr: "00"
sap_hana_control_function: "Change_Password"
sap_hana_control_user: "SAPHANADB"
sap_hana_control_current_password: "MySecretPassword"
sap_hana_control_new_password: "MyNewSecretPassword"
```

## License

GPLv3

## Author Information

Red Hat SAP Community of Practice
