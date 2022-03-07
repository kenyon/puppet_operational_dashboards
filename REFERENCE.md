# Reference

<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

### Classes

* [`puppet_operational_dashboards`](#puppet_operational_dashboards)
* [`puppet_operational_dashboards::profile::dashboards`](#puppet_operational_dashboardsprofiledashboards)
* [`puppet_operational_dashboards::profile::postgres_access`](#puppet_operational_dashboardsprofilepostgres_access)
* [`puppet_operational_dashboards::telegraf::agent`](#puppet_operational_dashboardstelegrafagent)

### Defined types

* [`puppet_operational_dashboards::telegraf::config`](#puppet_operational_dashboardstelegrafconfig)

### Functions

* [`puppet_operational_dashboards::hosts_with_pe_profile`](#puppet_operational_dashboardshosts_with_pe_profile)
* [`puppet_operational_dashboards::pe_profiles_on_host`](#puppet_operational_dashboardspe_profiles_on_host)

## Classes

### <a name="puppet_operational_dashboards"></a>`puppet_operational_dashboards`

The puppet_operational_dashboards class.

#### Parameters

The following parameters are available in the `puppet_operational_dashboards` class:

* [`manage_influxdb`](#manage_influxdb)
* [`manage_grafana`](#manage_grafana)
* [`influxdb_host`](#influxdb_host)
* [`influxdb_port`](#influxdb_port)
* [`influxdb_token`](#influxdb_token)
* [`telegraf_token`](#telegraf_token)
* [`initial_org`](#initial_org)
* [`initial_bucket`](#initial_bucket)
* [`telegraf_token_name`](#telegraf_token_name)
* [`manage_telegraf`](#manage_telegraf)
* [`manage_telegraf_token`](#manage_telegraf_token)
* [`use_ssl`](#use_ssl)

##### <a name="manage_influxdb"></a>`manage_influxdb`

Data type: `Boolean`



Default value: ``true``

##### <a name="manage_grafana"></a>`manage_grafana`

Data type: `Boolean`



Default value: ``true``

##### <a name="influxdb_host"></a>`influxdb_host`

Data type: `String`



Default value: `lookup(influxdb::host, undef, undef, $facts['networking']['fqdn'])`

##### <a name="influxdb_port"></a>`influxdb_port`

Data type: `Integer`



Default value: `lookup(influxdb::port, undef, undef, 8086)`

##### <a name="influxdb_token"></a>`influxdb_token`

Data type: `Optional[Sensitive[String]]`



Default value: `lookup(influxdb::token, undef, undef, undef)`

##### <a name="telegraf_token"></a>`telegraf_token`

Data type: `Optional[Sensitive[String]]`



Default value: ``undef``

##### <a name="initial_org"></a>`initial_org`

Data type: `String`



Default value: `lookup(influxdb::initial_org, undef, undef, 'puppetlabs')`

##### <a name="initial_bucket"></a>`initial_bucket`

Data type: `String`



Default value: `lookup(influxdb::initial_bucket, undef, undef, 'puppet_data')`

##### <a name="telegraf_token_name"></a>`telegraf_token_name`

Data type: `String`



Default value: `'puppet telegraf token'`

##### <a name="manage_telegraf"></a>`manage_telegraf`

Data type: `Boolean`



Default value: ``true``

##### <a name="manage_telegraf_token"></a>`manage_telegraf_token`

Data type: `Boolean`



Default value: ``true``

##### <a name="use_ssl"></a>`use_ssl`

Data type: `Boolean`



Default value: ``true``

### <a name="puppet_operational_dashboardsprofiledashboards"></a>`puppet_operational_dashboards::profile::dashboards`

The puppet_operational_dashboards::profile::dashboards class.

#### Parameters

The following parameters are available in the `puppet_operational_dashboards::profile::dashboards` class:

* [`token`](#token)
* [`grafana_host`](#grafana_host)
* [`grafana_port`](#grafana_port)
* [`grafana_password`](#grafana_password)
* [`grafana_version`](#grafana_version)
* [`grafana_datasource`](#grafana_datasource)
* [`grafana_install`](#grafana_install)
* [`use_ssl`](#use_ssl)
* [`influxdb_host`](#influxdb_host)
* [`influxdb_port`](#influxdb_port)
* [`initial_bucket`](#initial_bucket)

##### <a name="token"></a>`token`

Data type: `Sensitive[String]`



Default value: `$puppet_operational_dashboards::telegraf_token`

##### <a name="grafana_host"></a>`grafana_host`

Data type: `String`



Default value: `$facts['networking']['fqdn']`

##### <a name="grafana_port"></a>`grafana_port`

Data type: `Integer`



Default value: `3000`

##### <a name="grafana_password"></a>`grafana_password`

Data type: `Sensitive[String]`



Default value: `Sensitive('admin')`

##### <a name="grafana_version"></a>`grafana_version`

Data type: `String`



Default value: `'8.2.2'`

##### <a name="grafana_datasource"></a>`grafana_datasource`

Data type: `String`



Default value: `'influxdb_puppet'`

##### <a name="grafana_install"></a>`grafana_install`

Data type: `String`



Default value: `$facts['os']['family']`

##### <a name="use_ssl"></a>`use_ssl`

Data type: `Boolean`



Default value: ``true``

##### <a name="influxdb_host"></a>`influxdb_host`

Data type: `String`



Default value: `$puppet_operational_dashboards::influxdb_host`

##### <a name="influxdb_port"></a>`influxdb_port`

Data type: `Integer`



Default value: `$puppet_operational_dashboards::influxdb_port`

##### <a name="initial_bucket"></a>`initial_bucket`

Data type: `String`



Default value: `$puppet_operational_dashboards::initial_bucket`

### <a name="puppet_operational_dashboardsprofilepostgres_access"></a>`puppet_operational_dashboards::profile::postgres_access`

The puppet_operational_dashboards::profile::postgres_access class.

#### Parameters

The following parameters are available in the `puppet_operational_dashboards::profile::postgres_access` class:

* [`postgres_hosts`](#postgres_hosts)

##### <a name="postgres_hosts"></a>`postgres_hosts`

Data type: `Array`



Default value: `puppet_operational_dashboards::hosts_with_pe_profile('Database')`

### <a name="puppet_operational_dashboardstelegrafagent"></a>`puppet_operational_dashboards::telegraf::agent`

The puppet_operational_dashboards::telegraf::agent class.

#### Parameters

The following parameters are available in the `puppet_operational_dashboards::telegraf::agent` class:

* [`token`](#token)
* [`influxdb_host`](#influxdb_host)
* [`influxdb_port`](#influxdb_port)
* [`influxdb_org`](#influxdb_org)
* [`influxdb_bucket`](#influxdb_bucket)
* [`use_ssl`](#use_ssl)
* [`manage_ssl`](#manage_ssl)
* [`ssl_cert_file`](#ssl_cert_file)
* [`ssl_key_file`](#ssl_key_file)
* [`ssl_ca_file`](#ssl_ca_file)
* [`version`](#version)
* [`collection_method`](#collection_method)
* [`config_file`](#config_file)
* [`config_dir`](#config_dir)
* [`collection_interval`](#collection_interval)
* [`puppetserver_hosts`](#puppetserver_hosts)
* [`puppetdb_hosts`](#puppetdb_hosts)
* [`postgres_hosts`](#postgres_hosts)
* [`profiles`](#profiles)
* [`local_services`](#local_services)

##### <a name="token"></a>`token`

Data type: `Sensitive[String]`



##### <a name="influxdb_host"></a>`influxdb_host`

Data type: `String`



Default value: `$facts['networking']['fqdn']`

##### <a name="influxdb_port"></a>`influxdb_port`

Data type: `Integer`



Default value: `8086`

##### <a name="influxdb_org"></a>`influxdb_org`

Data type: `String`



Default value: `'puppetlabs'`

##### <a name="influxdb_bucket"></a>`influxdb_bucket`

Data type: `String`



Default value: `'puppet_data'`

##### <a name="use_ssl"></a>`use_ssl`

Data type: `Boolean`



Default value: ``true``

##### <a name="manage_ssl"></a>`manage_ssl`

Data type: `Boolean`



Default value: ``true``

##### <a name="ssl_cert_file"></a>`ssl_cert_file`

Data type: `String`



Default value: `"${facts['puppet_ssldir']}/certs/${trusted['certname']}.pem"`

##### <a name="ssl_key_file"></a>`ssl_key_file`

Data type: `String`



Default value: `"${facts['puppet_ssldir']}/private_keys/${trusted['certname']}.pem"`

##### <a name="ssl_ca_file"></a>`ssl_ca_file`

Data type: `String`



Default value: `"${facts['puppet_ssldir']}/certs/ca.pem"`

##### <a name="version"></a>`version`

Data type: `String`



Default value: `'1.21.2'`

##### <a name="collection_method"></a>`collection_method`

Data type: `Enum['all', 'local', 'none']`



Default value: `'all'`

##### <a name="config_file"></a>`config_file`

Data type: `String`



Default value: `'/etc/telegraf/telegraf.conf'`

##### <a name="config_dir"></a>`config_dir`

Data type: `String`



Default value: `'/etc/telegraf/telegraf.d'`

##### <a name="collection_interval"></a>`collection_interval`

Data type: `String`



Default value: `'10m'`

##### <a name="puppetserver_hosts"></a>`puppetserver_hosts`

Data type: `Array`



Default value: `puppet_operational_dashboards::hosts_with_pe_profile('Master')`

##### <a name="puppetdb_hosts"></a>`puppetdb_hosts`

Data type: `Array`



Default value: `puppet_operational_dashboards::hosts_with_pe_profile('Puppetdb')`

##### <a name="postgres_hosts"></a>`postgres_hosts`

Data type: `Array`



Default value: `puppet_operational_dashboards::hosts_with_pe_profile('Database')`

##### <a name="profiles"></a>`profiles`

Data type: `Array[String]`



Default value: `puppet_operational_dashboards::pe_profiles_on_host()`

##### <a name="local_services"></a>`local_services`

Data type: `Array[String]`



Default value: `[]`

## Defined types

### <a name="puppet_operational_dashboardstelegrafconfig"></a>`puppet_operational_dashboards::telegraf::config`

The puppet_operational_dashboards::telegraf::config class.

#### Parameters

The following parameters are available in the `puppet_operational_dashboards::telegraf::config` defined type:

* [`hosts`](#hosts)
* [`service`](#service)
* [`ensure`](#ensure)

##### <a name="hosts"></a>`hosts`

Data type: `Array[String[1]]`



##### <a name="service"></a>`service`

Data type: `String`



Default value: `$title`

##### <a name="ensure"></a>`ensure`

Data type: `Enum['present', 'absent']`



Default value: `'present'`

## Functions

### <a name="puppet_operational_dashboardshosts_with_pe_profile"></a>`puppet_operational_dashboards::hosts_with_pe_profile`

Type: Puppet Language

The puppet_operational_dashboards::hosts_with_pe_profile function.

#### `puppet_operational_dashboards::hosts_with_pe_profile(String $profile)`

The puppet_operational_dashboards::hosts_with_pe_profile function.

Returns: `Array`

##### `profile`

Data type: `String`



### <a name="puppet_operational_dashboardspe_profiles_on_host"></a>`puppet_operational_dashboards::pe_profiles_on_host`

Type: Puppet Language

The puppet_operational_dashboards::pe_profiles_on_host function.

#### `puppet_operational_dashboards::pe_profiles_on_host()`

The puppet_operational_dashboards::pe_profiles_on_host function.

Returns: `Array`
