# ansible-icinga2-director-import

This repository is a example on how to generate monitoring data for Icinga 2 based on facts/vars from the automation software Ansible.

The playbook simply creates a CSV with all information needed to define standard and application monitoring.

Use this as blueprint and further extend the template/vars to your needs.

### Director IDs

To run the import/sync rules we need to create them first and then use their internal IDs to reference them.

For this use the command for imports `TODO` and for sync rules `TODO`

Afterwards use those as variables in the playbook by either modifing the playbook or supplying them on the commandline with `-e`

### Variables:

Those variables are used on each host, the most important variable is the state. The var `monitoring_state` determines if the host needs to be included and also prepares the information on the host if its production, dev or test. 

**monitoring_state**: Choose between prod/dev/test to include them into the monitoring.

**monitoring_address**: Address of the host to be monitored. Also the address where 5665 is reachable.

**ansible_distribution**: Can be set manually if the facts aren't cached.

**ansible_distribution_version**: Can be set manually if the facts aren't cached.

**monitoring_applications**: List of applications to apply standardised monitoring sets for each.

**monitoring_type**: Used to define if host is monitored by ssh, agent etc.

**monitoring_exta_json**: Used to provide extra data as json.
