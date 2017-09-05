cfme-ocp-provider
=========

Role used to configure OpenShift as a Container Provider to Red Hat CloudForms.


Requirements
------------

None

Role Variables
--------------

The following role variables must be provided

```
cfme_host: <hostname of the CloudForms instance>
cfme_username: <Username to access CloudForms>
cfme_password: <Password to access CloudForms>
ocp_token: OAuth token to access OpenShift Rest API and Hawkular
```

The following variables can also be provided in order to customize the configuration

```
ocp_master_host: <OpenShift API Host>
ocp_master_port: <OpenShift API Port>
hawkular_host: <Hawkular Hostname>
hawkular_port: <Hawkular Port>
ocp_container_provier_name: <Name of the Container Provider in CloudForms to create for OpenShift>
```

Dependencies
------------
None


Example Playbook
----------------

The following is a sample playbook

```
# Example
- hosts: masters[0]
  roles:
    - role: cfme-ocp-provider
      cfme_host: cloudforms.example.com
      ocp_token: <token>
```

License
-------

BSD

Author Information
------------------
Red Hat Community of Practice & staff of the Red Hat Open Innovation Labs.
