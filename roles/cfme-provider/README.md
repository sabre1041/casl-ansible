cfme-provider
=========

Role used to configure Providers for Red Hat CloudForms.

Requirements
------------

None

Available Providers
-------------

* OpenShift Container Provider (ocp)
* AWS Cloud Provider (aws)

Role Variables
--------------

The following role variables must be provided

```
cfme_host: <hostname of the CloudForms instance>
cfme_username: <Username to access CloudForms>
cfme_password: <Password to access CloudForms>
providers: <Comma separated list of providers>
```

The following role variables can also be provided to customize the generic execution

```
max_retries: <Number of retries to attempt when invoking remote resources>
retry_interval: <Amount of time between retry attempts>
```

The following are provider specific variables:

**OCP**

```
provider_ocp_master_host: <OpenShift API Host>
provider_ocp_master_port: <OpenShift API Port>
provider_ocp_hawkular_host: <Hawkular Hostname>
provider_ocp_hawkular_port: <Hawkular Port>
provider_ocp_token: <OAuth token to access OpenShift Rest API>
provider_ocp_hawkular_token: <OAuth token to access Hawkular Metrics>
provider_ocp_container_provider_name: <Name of the Container Provider in CloudForms to create for OpenShift>
provider_ocp_default_token_sa_namespace: <Namespace of the Service Account containing the OAuth token if one is not provided for OpenShift or Hawkular>
provider_ocp_default_token_sa_name: <Name of the Service Account containing the OAuth token if one is not provided for OpenShift or Hawkular>
```

**AWS**

```
provider_aws_provider_name: <Name of the Container Provider in CloudForms to create for AWS>
provider_aws_region: <AWS region>
provider_aws_username: <AWS access key id>
provider_aws_password: <AWS secret access key>
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
      providers: ocp
```

License
-------

BSD

Author Information
------------------
Red Hat Community of Practice & staff of the Red Hat Open Innovation Labs.
