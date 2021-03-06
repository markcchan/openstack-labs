---
date: "2015-10-06"
draft: false
weight: 17
title: "Lab 17 - Edit the tempest.conf file"
---

<pre>
[DEFAULT]

#
# From oslo.log
#

# If set to true, the logging level will be set to DEBUG instead of
# the default INFO level. (boolean value)
# Note: This option can be changed without restarting.
#debug = false

# DEPRECATED: If set to false, the logging level will be set to
# WARNING instead of the default INFO level. (boolean value)
# This option is deprecated for removal.
# Its value may be silently ignored in the future.
#verbose = true

# The name of a logging configuration file. This file is appended to
# any existing logging configuration files. For details about logging
# configuration files, see the Python logging module documentation.
# Note that when logging configuration files are used then all logging
# configuration is set in the configuration file and other logging
# configuration options are ignored (for example,
# logging_context_format_string). (string value)
# Deprecated group/name - [DEFAULT]/log_config
#log_config_append = <None>

# Defines the format string for %%(asctime)s in log records. Default:
# %(default)s . This option is ignored if log_config_append is set.
# (string value)
#log_date_format = %Y-%m-%d %H:%M:%S

# (Optional) Name of log file to send logging output to. If no default
# is set, logging will go to stderr as defined by use_stderr. This
# option is ignored if log_config_append is set. (string value)
# Deprecated group/name - [DEFAULT]/logfile
#log_file = <None>

# (Optional) The base directory used for relative log_file  paths.
# This option is ignored if log_config_append is set. (string value)
# Deprecated group/name - [DEFAULT]/logdir
#log_dir = <None>

# Uses logging handler designed to watch file system. When log file is
# moved or removed this handler will open a new log file with
# specified path instantaneously. It makes sense only if log_file
# option is specified and Linux platform is used. This option is
# ignored if log_config_append is set. (boolean value)
#watch_log_file = false

# Use syslog for logging. Existing syslog format is DEPRECATED and
# will be changed later to honor RFC5424. This option is ignored if
# log_config_append is set. (boolean value)
#use_syslog = false

# Syslog facility to receive log lines. This option is ignored if
# log_config_append is set. (string value)
#syslog_log_facility = LOG_USER

# Log output to standard error. This option is ignored if
# log_config_append is set. (boolean value)
#use_stderr = true

# Format string to use for log messages with context. (string value)
#logging_context_format_string = %(asctime)s.%(msecs)03d %(process)d %(levelname)s %(name)s [%(request_id)s %(user_identity)s] %(instance)s%(message)s

# Format string to use for log messages when context is undefined.
# (string value)
#logging_default_format_string = %(asctime)s.%(msecs)03d %(process)d %(levelname)s %(name)s [-] %(instance)s%(message)s

# Additional data to append to log message when logging level for the
# message is DEBUG. (string value)
#logging_debug_format_suffix = %(funcName)s %(pathname)s:%(lineno)d

# Prefix each line of exception output with this format. (string
# value)
#logging_exception_prefix = %(asctime)s.%(msecs)03d %(process)d ERROR %(name)s %(instance)s

# Defines the format string for %(user_identity)s that is used in
# logging_context_format_string. (string value)
#logging_user_identity_format = %(user)s %(tenant)s %(domain)s %(user_domain)s %(project_domain)s

# List of package logging levels in logger=LEVEL pairs. This option is
# ignored if log_config_append is set. (list value)
#default_log_levels = amqp=WARN,amqplib=WARN,boto=WARN,qpid=WARN,sqlalchemy=WARN,suds=INFO,oslo.messaging=INFO,iso8601=WARN,requests.packages.urllib3.connectionpool=WARN,urllib3.connectionpool=WARN,websocket=WARN,requests.packages.urllib3.util.retry=WARN,urllib3.util.retry=WARN,keystonemiddleware=WARN,routes.middleware=WARN,stevedore=WARN,taskflow=WARN,keystoneauth=WARN,oslo.cache=INFO,dogpile.core.dogpile=INFO

# Enables or disables publication of error events. (boolean value)
#publish_errors = false

# The format for an instance that is passed with the log message.
# (string value)
#instance_format = "[instance: %(uuid)s] "

# The format for an instance UUID that is passed with the log message.
# (string value)
#instance_uuid_format = "[instance: %(uuid)s] "

# Enables or disables fatal status of deprecations. (boolean value)
#fatal_deprecations = false

#
# From tempest.config
#

# Prefix to be added when generating the name for test resources. It
# can be used to discover all resources associated with a specific
# test run when running tempest on a real-life cloud (string value)
#resources_prefix = tempest


[auth]

#
# From tempest.config
#

# Path to the yaml file that contains the list of credentials to use
# for running tests. If used when running in parallel you have to make
# sure sufficient credentials are provided in the accounts file. For
# example if no tests with roles are being run it requires at least `2
# * CONC` distinct accounts configured in  the `test_accounts_file`,
# with CONC == the number of concurrent test processes. (string value)
#test_accounts_file = <None>

# Allows test cases to create/destroy projects and users. This option
# requires that OpenStack Identity API admin credentials are known. If
# false, isolated test cases and parallel execution, can still be
# achieved configuring a list of test accounts (boolean value)
# Deprecated group/name - [auth]/allow_tenant_isolation
# Deprecated group/name - [compute]/allow_tenant_isolation
# Deprecated group/name - [orchestration]/allow_tenant_isolation
#use_dynamic_credentials = true

# Roles to assign to all users created by tempest (list value)
#tempest_roles =

# Default domain used when getting v3 credentials. This is the name
# keystone uses for v2 compatibility. (string value)
# Deprecated group/name - [auth]/tenant_isolation_domain_name
#default_credentials_domain_name = Default

# If use_dynamic_credentials is set to True and Neutron is enabled
# Tempest will try to create a usable network, subnet, and router when
# needed for each project it creates. However in some neutron
# configurations, like with VLAN provider networks, this doesn't work.
# So if set to False the isolated networks will not be created
# (boolean value)
#create_isolated_networks = true

# Username for an administrative user. This is needed for
# authenticating requests made by project isolation to create users
# and projects (string value)
# Deprecated group/name - [identity]/admin_username
#admin_username = <None>

# Project name to use for an administrative user. This is needed for
# authenticating requests made by project isolation to create users
# and projects (string value)
# Deprecated group/name - [auth]/admin_tenant_name
# Deprecated group/name - [identity]/admin_tenant_name
#admin_project_name = <None>

# Password to use for an administrative user. This is needed for
# authenticating requests made by project isolation to create users
# and projects (string value)
# Deprecated group/name - [identity]/admin_password
#admin_password = <None>

# Admin domain name for authentication (Keystone V3).The same domain
# applies to user and project (string value)
# Deprecated group/name - [identity]/admin_domain_name
#admin_domain_name = <None>


[baremetal]
# When enabling baremetal tests, Nova must be configured to use the
# Ironic driver. The following parameters for the [compute] section
# must be disabled: console_output, interface_attach, live_migration,
# pause, rescue, resize shelve, snapshot, and suspend

#
# From tempest.config
#

# Catalog type of the baremetal provisioning service (string value)
#catalog_type = baremetal

# Whether the Ironic nova-compute driver is enabled (boolean value)
#driver_enabled = false

# Driver name which Ironic uses (string value)
#driver = fake

# The endpoint type to use for the baremetal provisioning service
# (string value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#endpoint_type = publicURL

# Timeout for Ironic node to completely provision (integer value)
#active_timeout = 300

# Timeout for association of Nova instance and Ironic node (integer
# value)
#association_timeout = 30

# Timeout for Ironic power transitions. (integer value)
#power_timeout = 60

# Timeout for unprovisioning an Ironic node. Takes longer since Kilo
# as Ironic performs an extra step in Node cleaning. (integer value)
#unprovision_timeout = 300


[compute]

#
# From tempest.config
#

# Valid primary image reference to be used in tests. This is a
# required option (string value)
#image_ref = <None>

# Valid secondary image reference to be used in tests. This is a
# required option, but if only one image is available duplicate the
# value of image_ref above (string value)
#image_ref_alt = <None>

# Valid primary flavor to use in tests. (string value)
#flavor_ref = 1

# Valid secondary flavor to be used in tests. (string value)
#flavor_ref_alt = 2

# Time in seconds between build status checks. (integer value)
#build_interval = 1

# Timeout in seconds to wait for an instance to build. Other services
# that do not define build_timeout will inherit this value. (integer
# value)
#build_timeout = 300

# Additional wait time for clean state, when there is no OS-EXT-STS
# extension available (integer value)
#ready_wait = 0

# Name of the fixed network that is visible to all test projects. If
# multiple networks are available for a project, this is the network
# which will be used for creating servers if tempest does not create a
# network or s network is not specified elsewhere. It may be used for
# ssh validation only if floating IPs are disabled. (string value)
#fixed_network_name = <None>

# Catalog type of the Compute service. (string value)
#catalog_type = compute

# The compute region name to use. If empty, the value of
# identity.region is used instead. If no such region is found in the
# service catalog, the first found one is used. (string value)
#region =

# The endpoint type to use for the compute service. (string value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#endpoint_type = publicURL

# Expected device name when a volume is attached to an instance
# (string value)
#volume_device_name = vdb

# Time in seconds before a shelved instance is eligible for removing
# from a host.  -1 never offload, 0 offload when shelved. This time
# should be the same as the time of nova.conf, and some tests will run
# for as long as the time. (integer value)
#shelved_offload_time = 0

# The minimum number of compute nodes expected. This will be utilized
# by some multinode specific tests to ensure that requests match the
# expected size of the cluster you are testing with. (integer value)
#min_compute_nodes = 1

# Lower version of the test target microversion range. The format is
# 'X.Y', where 'X' and 'Y' are int values. Tempest selects tests based
# on the range between min_microversion and max_microversion. If both
# values are not specified, Tempest avoids tests which require a
# microversion. Valid values are string with format 'X.Y' or string
# 'latest' (string value)
# Deprecated group/name - [compute-feature-enabled]/min_microversion
#min_microversion = <None>

# Upper version of the test target microversion range. The format is
# 'X.Y', where 'X' and 'Y' are int values. Tempest selects tests based
# on the range between min_microversion and max_microversion. If both
# values are not specified, Tempest avoids tests which require a
# microversion. Valid values are string with format 'X.Y' or string
# 'latest' (string value)
# Deprecated group/name - [compute-feature-enabled]/max_microversion
#max_microversion = <None>


[compute-feature-enabled]

#
# From tempest.config
#

# If false, skip disk config tests (boolean value)
#disk_config = true

# A list of enabled compute extensions with a special entry all which
# indicates every extension is enabled. Each extension should be
# specified with alias name. Empty list indicates all extensions are
# disabled (list value)
#api_extensions = all

# Does the test environment support changing the admin password?
# (boolean value)
#change_password = false

# Does the test environment support obtaining instance serial console
# output? (boolean value)
#console_output = true

# Does the test environment support resizing? (boolean value)
#resize = false

# Does the test environment support pausing? (boolean value)
#pause = true

# Does the test environment support shelving/unshelving? (boolean
# value)
#shelve = true

# Does the test environment support suspend/resume? (boolean value)
#suspend = true

# Does the test environment support live migration available? (boolean
# value)
#live_migration = true

# Does the test environment support metadata service? Ignored unless
# validation.run_validation=true. (boolean value)
#metadata_service = true

# Does the test environment use block devices for live migration
# (boolean value)
#block_migration_for_live_migration = false

# Does the test environment block migration support cinder iSCSI
# volumes. Note, libvirt doesn't support this, see
# https://bugs.launchpad.net/nova/+bug/1398999 (boolean value)
#block_migrate_cinder_iscsi = false

# Enable VNC console. This configuration value should be same as
# [nova.vnc]->vnc_enabled in nova.conf (boolean value)
#vnc_console = false

# Enable Spice console. This configuration value should be same as
# [nova.spice]->enabled in nova.conf (boolean value)
#spice_console = false

# Enable RDP console. This configuration value should be same as
# [nova.rdp]->enabled in nova.conf (boolean value)
#rdp_console = false

# Does the test environment support instance rescue mode? (boolean
# value)
#rescue = true

# Enables returning of the instance password by the relevant server
# API calls such as create, rebuild or rescue. (boolean value)
#enable_instance_password = true

# Does the test environment support dynamic network interface
# attachment? (boolean value)
#interface_attach = true

# Does the test environment support creating snapshot images of
# running instances? (boolean value)
#snapshot = true

# Does the test environment have the nova cert running? (boolean
# value)
#nova_cert = true

# Does the test environment support server personality (boolean value)
#personality = true

# Does the test environment support attaching an encrypted volume to a
# running server instance? This may depend on the combination of
# compute_driver in nova and the volume_driver(s) in cinder. (boolean
# value)
#attach_encrypted_volume = true

# Enable special configuration drive with metadata. (boolean value)
#config_drive = true

# A list of enabled filters that nova will accept as hints to the
# scheduler when creating a server. A special entry 'all' indicates
# all filters are enabled. Empty list indicates all filters are
# disabled. The full available list of filters is in nova.conf:
# DEFAULT.scheduler_available_filters (list value)
#scheduler_available_filters = all


[data-processing]

#
# From tempest.config
#

# Catalog type of the data processing service. (string value)
# Deprecated group/name - [data_processing]/catalog_type
#catalog_type = data-processing

# The endpoint type to use for the data processing service. (string
# value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
# Deprecated group/name - [data_processing]/endpoint_type
#endpoint_type = publicURL


[data-processing-feature-enabled]

#
# From tempest.config
#

# List of enabled data processing plugins (list value)
# Deprecated group/name - [data_processing-feature-enabled]/plugins
#plugins = vanilla,cdh


[database]

#
# From tempest.config
#

# Catalog type of the Database service. (string value)
#catalog_type = database

# Valid primary flavor to use in database tests. (string value)
#db_flavor_ref = 1

# Current database version to use in database tests. (string value)
#db_current_version = v1.0


[debug]

#
# From tempest.config
#

# A regex to determine which requests should be traced.
#
# This is a regex to match the caller for rest client requests to be
# able to
# selectively trace calls out of specific classes and methods. It
# largely
# exists for test development, and is not expected to be used in a
# real deploy
# of tempest. This will be matched against the discovered
# ClassName:method
# in the test environment.
#
# Expected values for this field are:
#
#  * ClassName:test_method_name - traces one test_method
#  * ClassName:setUp(Class) - traces specific setup functions
#  * ClassName:tearDown(Class) - traces specific teardown functions
#  * ClassName:_run_cleanups - traces the cleanup functions
#
# If nothing is specified, this feature is not enabled. To trace
# everything
# specify .* as the regex.
#  (string value)
#trace_requests =


[identity]

#
# From tempest.config
#

# Catalog type of the Identity service. (string value)
#catalog_type = identity

# Set to True if using self-signed SSL certificates. (boolean value)
#disable_ssl_certificate_validation = false

# Specify a CA bundle file to use in verifying a TLS (https) server
# certificate. (string value)
#ca_certificates_file = <None>

# Full URI of the OpenStack Identity API (Keystone), v2 (string value)
#uri = <None>

# Full URI of the OpenStack Identity API (Keystone), v3 (string value)
#uri_v3 = <None>

# Identity API version to be used for authentication for API tests.
# (string value)
#auth_version = v2

# The identity region name to use. Also used as the other services'
# region name unless they are set explicitly. If no such region is
# found in the service catalog, the first found one is used. (string
# value)
#region = RegionOne

# The admin endpoint type to use for OpenStack Identity (Keystone) API
# v2 (string value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#v2_admin_endpoint_type = adminURL

# The public endpoint type to use for OpenStack Identity (Keystone)
# API v2 (string value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
# Deprecated group/name - [identity]/endpoint_type
#v2_public_endpoint_type = publicURL

# The endpoint type to use for OpenStack Identity (Keystone) API v3
# (string value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#v3_endpoint_type = adminURL

# Role required to administrate keystone. (string value)
#admin_role = admin

# ID of the default domain (string value)
#default_domain_id = default


[identity-feature-enabled]

#
# From tempest.config
#

# Does the identity service have delegation and impersonation enabled
# (boolean value)
#trust = true

# Is the v2 identity API enabled (boolean value)
#api_v2 = true

# Is the v3 identity API enabled (boolean value)
#api_v3 = true

# A list of enabled identity extensions with a special entry all which
# indicates every extension is enabled. Empty list indicates all
# extensions are disabled. To get the list of extensions run:
# 'keystone discover' (list value)
#api_extensions = all


[image]

#
# From tempest.config
#

# Catalog type of the Image service. (string value)
#catalog_type = image

# The image region name to use. If empty, the value of identity.region
# is used instead. If no such region is found in the service catalog,
# the first found one is used. (string value)
#region =

# The endpoint type to use for the image service. (string value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#endpoint_type = publicURL

# http accessible image (string value)
#http_image = http://download.cirros-cloud.net/0.3.1/cirros-0.3.1-x86_64-uec.tar.gz

# Timeout in seconds to wait for an image to become available.
# (integer value)
#build_timeout = 300

# Time in seconds between image operation status checks. (integer
# value)
#build_interval = 1

# A list of image's container formats users can specify. (list value)
#container_formats = ami,ari,aki,bare,ovf,ova

# A list of image's disk formats users can specify. (list value)
#disk_formats = ami,ari,aki,vhd,vmdk,raw,qcow2,vdi,iso


[image-feature-enabled]

#
# From tempest.config
#

# Is the v2 image API enabled (boolean value)
#api_v2 = true

# Is the v1 image API enabled (boolean value)
#api_v1 = true

# Is the deactivate-image feature enabled. The feature has been
# integrated since Kilo. (boolean value)
#deactivate_image = false


[input-scenario]

#
# From tempest.config
#

# Matching images become parameters for scenario tests (string value)
#image_regex = ^cirros-0.3.1-x86_64-uec$

# Matching flavors become parameters for scenario tests (string value)
#flavor_regex = ^m1.nano$

# SSH verification in tests is skippedfor matching images (string
# value)
#non_ssh_image_regex = ^.*[Ww]in.*$

# List of user mapped to regex to matching image names. (string value)
#ssh_user_regex = [["^.*[Cc]irros.*$", "cirros"]]


[negative]

#
# From tempest.config
#

# Test generator class for all negative tests (string value)
#test_generator = tempest.common.generator.negative_generator.NegativeTestGenerator


[network]

#
# From tempest.config
#

# Catalog type of the Neutron service. (string value)
#catalog_type = network

# The network region name to use. If empty, the value of
# identity.region is used instead. If no such region is found in the
# service catalog, the first found one is used. (string value)
#region =

# The endpoint type to use for the network service. (string value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#endpoint_type = publicURL

# The cidr block to allocate project ipv4 subnets from (string value)
# Deprecated group/name - [DEFAULT]/tenant_network_cidr
#project_network_cidr = 10.100.0.0/16

# The mask bits for project ipv4 subnets (integer value)
# Deprecated group/name - [DEFAULT]/tenant_network_mask_bits
#project_network_mask_bits = 28

# The cidr block to allocate project ipv6 subnets from (string value)
# Deprecated group/name - [DEFAULT]/tenant_network_v6_cidr
#project_network_v6_cidr = 2003::/48

# The mask bits for project ipv6 subnets (integer value)
# Deprecated group/name - [DEFAULT]/tenant_network_v6_mask_bits
#project_network_v6_mask_bits = 64

# Whether project networks can be reached directly from the test
# client. This must be set to True when the 'fixed' ssh_connect_method
# is selected. (boolean value)
# Deprecated group/name - [DEFAULT]/tenant_networks_reachable
#project_networks_reachable = false

# Id of the public network that provides external connectivity (string
# value)
#public_network_id =

# Default floating network name. Used to allocate floating IPs when
# neutron is enabled. (string value)
#floating_network_name = <None>

# Id of the public router that provides external connectivity. This
# should only be used when Neutron's 'allow_overlapping_ips' is set to
# 'False' in neutron.conf. usually not needed past 'Grizzly' release
# (string value)
#public_router_id =

# Timeout in seconds to wait for network operation to complete.
# (integer value)
#build_timeout = 300

# Time in seconds between network operation status checks. (integer
# value)
#build_interval = 1

# List of dns servers which should be used for subnet creation (list
# value)
#dns_servers = 8.8.8.8,8.8.4.4

# vnic_type to use when Launching instances with pre-configured ports.
# Supported ports are: ['normal','direct','macvtap'] (string value)
# Allowed values: <None>, normal, direct, macvtap
#port_vnic_type = <None>

# List of ip pools for subnetpools creation (list value)
#default_network = 1.0.0.0/16,2.0.0.0/16


[network-feature-enabled]

#
# From tempest.config
#

# Allow the execution of IPv6 tests (boolean value)
#ipv6 = true

# A list of enabled network extensions with a special entry all which
# indicates every extension is enabled. Empty list indicates all
# extensions are disabled. To get the list of extensions run: 'neutron
# ext-list' (list value)
#api_extensions = all

# Allow the execution of IPv6 subnet tests that use the extended IPv6
# attributes ipv6_ra_mode and ipv6_address_mode (boolean value)
#ipv6_subnet_attributes = false

# Does the test environment support changing port admin state (boolean
# value)
#port_admin_state_change = true


[object-storage]

#
# From tempest.config
#

# Catalog type of the Object-Storage service. (string value)
#catalog_type = object-store

# The object-storage region name to use. If empty, the value of
# identity.region is used instead. If no such region is found in the
# service catalog, the first found one is used. (string value)
#region =

# The endpoint type to use for the object-store service. (string
# value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#endpoint_type = publicURL

# Number of seconds to time on waiting for a container to container
# synchronization complete. (integer value)
#container_sync_timeout = 600

# Number of seconds to wait while looping to check the status of a
# container to container synchronization (integer value)
#container_sync_interval = 5

# Role to add to users created for swift tests to enable creating
# containers (string value)
#operator_role = Member

# User role that has reseller admin (string value)
#reseller_admin_role = ResellerAdmin

# Name of sync realm. A sync realm is a set of clusters that have
# agreed to allow container syncing with each other. Set the same
# realm name as Swift's container-sync-realms.conf (string value)
#realm_name = realm1

# One name of cluster which is set in the realm whose name is set in
# 'realm_name' item in this file. Set the same cluster name as Swift's
# container-sync-realms.conf (string value)
#cluster_name = name1


[object-storage-feature-enabled]

#
# From tempest.config
#

# A list of the enabled optional discoverable apis. A single entry,
# all, indicates that all of these features are expected to be enabled
# (list value)
#discoverable_apis = all

# Execute (old style) container-sync tests (boolean value)
#container_sync = true

# Execute object-versioning tests (boolean value)
#object_versioning = true

# Execute discoverability tests (boolean value)
#discoverability = true


[orchestration]

#
# From tempest.config
#

# Catalog type of the Orchestration service. (string value)
#catalog_type = orchestration

# The orchestration region name to use. If empty, the value of
# identity.region is used instead. If no such region is found in the
# service catalog, the first found one is used. (string value)
#region =

# The endpoint type to use for the orchestration service. (string
# value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#endpoint_type = publicURL

# Role required for users to be able to manage stacks (string value)
#stack_owner_role = heat_stack_owner

# Time in seconds between build status checks. (integer value)
#build_interval = 1

# Timeout in seconds to wait for a stack to build. (integer value)
#build_timeout = 1200

# Instance type for tests. Needs to be big enough for a full OS plus
# the test workload (string value)
#instance_type = m1.micro

# Name of existing keypair to launch servers with. (string value)
#keypair_name = <None>

# Value must match heat configuration of the same name. (integer
# value)
#max_template_size = 524288

# Value must match heat configuration of the same name. (integer
# value)
#max_resources_per_stack = 1000


[oslo_concurrency]

#
# From oslo.concurrency
#

# Enables or disables inter-process locks. (boolean value)
# Deprecated group/name - [DEFAULT]/disable_process_locking
#disable_process_locking = false

# Directory to use for lock files.  For security, the specified
# directory should only be writable by the user running the processes
# that need locking. Defaults to environment variable OSLO_LOCK_PATH.
# If external locks are used, a lock path must be set. (string value)
# Deprecated group/name - [DEFAULT]/lock_path
#lock_path = <None>


[scenario]

#
# From tempest.config
#

# DEPRECATED: Directory containing image files (string value)
# This option is deprecated for removal.
# Its value may be silently ignored in the future.
#img_dir = /opt/stack/new/devstack/files/images/cirros-0.3.1-x86_64-uec

# Image file name (string value)
# Deprecated group/name - [DEFAULT]/qcow2_img_file
#img_file = cirros-0.3.1-x86_64-disk.img

# Image disk format (string value)
#img_disk_format = qcow2

# Image container format (string value)
#img_container_format = bare

# Glance image properties. Use for custom images which require them
# (dict value)
#img_properties = <None>

# DEPRECATED: AMI image file name (string value)
# This option is deprecated for removal.
# Its value may be silently ignored in the future.
#ami_img_file = cirros-0.3.1-x86_64-blank.img

# DEPRECATED: ARI image file name (string value)
# This option is deprecated for removal.
# Its value may be silently ignored in the future.
#ari_img_file = cirros-0.3.1-x86_64-initrd

# DEPRECATED: AKI image file name (string value)
# This option is deprecated for removal.
# Its value may be silently ignored in the future.
#aki_img_file = cirros-0.3.1-x86_64-vmlinuz

# DHCP client used by images to renew DCHP lease. If left empty,
# update operation will be skipped. Supported clients: "udhcpc",
# "dhclient" (string value)
# Allowed values: udhcpc, dhclient, ''
#dhcp_client = udhcpc


[service_available]

#
# From tempest.config
#

# Whether or not cinder is expected to be available (boolean value)
#cinder = true

# Whether or not neutron is expected to be available (boolean value)
#neutron = false

# Whether or not glance is expected to be available (boolean value)
#glance = true

# Whether or not swift is expected to be available (boolean value)
#swift = true

# Whether or not nova is expected to be available (boolean value)
#nova = true

# Whether or not Heat is expected to be available (boolean value)
#heat = false

# Whether or not Sahara is expected to be available (boolean value)
#sahara = false

# Whether or not Ironic is expected to be available (boolean value)
#ironic = false

# Whether or not Trove is expected to be available (boolean value)
#trove = false


[stress]

#
# From tempest.config
#

# Directory containing log files on the compute nodes (string value)
#nova_logdir = <None>

# Maximum number of instances to create during test. (integer value)
#max_instances = 16

# Controller host. (string value)
#controller = <None>

# Controller host. (string value)
#target_controller = <None>

# ssh user. (string value)
#target_ssh_user = <None>

# Path to private key. (string value)
#target_private_key_path = <None>

# regexp for list of log files. (string value)
#target_logfiles = <None>

# time (in seconds) between log file error checks. (integer value)
#log_check_interval = 60

# The number of threads created while stress test. (integer value)
#default_thread_number_per_action = 4

# Prevent the cleaning (tearDownClass()) between each stress test run
# if an exception occurs during this run. (boolean value)
#leave_dirty_stack = false

# Allows a full cleaning process after a stress test. Caution : this
# cleanup will remove every objects of every project. (boolean value)
#full_clean_stack = false


[validation]

#
# From tempest.config
#

# Enable ssh on created servers and creation of additional validation
# resources to enable remote access (boolean value)
#run_validation = false

# Enable/disable security groups. (boolean value)
#security_group = true

# Enable/disable security group rules. (boolean value)
#security_group_rules = true

# Default IP type used for validation: -fixed: uses the first IP
# belonging to the fixed network -floating: creates and uses a
# floating IP (string value)
# Allowed values: fixed, floating
# Deprecated group/name - [compute]/use_floatingip_for_ssh
#connect_method = floating

# Default authentication method to the instance. Only ssh via keypair
# is supported for now. Additional methods will be handled in a
# separate spec. (string value)
# Allowed values: keypair
# Deprecated group/name - [compute]/ssh_auth_method
#auth_method = keypair

# Default IP version for ssh connections. (integer value)
#ip_version_for_ssh = 4

# Timeout in seconds to wait for ping to succeed. (integer value)
# Deprecated group/name - [compute]/ping_timeout
#ping_timeout = 120

# Timeout in seconds to wait for the TCP connection to be successful.
# (integer value)
#connect_timeout = 60

# Timeout in seconds to wait for the ssh banner. (integer value)
#ssh_timeout = 300

# User name used to authenticate to an instance. (string value)
# Deprecated group/name - [compute]/image_ssh_user
# Deprecated group/name - [compute]/ssh_user
# Deprecated group/name - [scenario]/ssh_user
#image_ssh_user = root

# Password used to authenticate to an instance. (string value)
# Deprecated group/name - [compute]/image_ssh_password
#image_ssh_password = password

# Shell fragments to use before executing a command when sshing to a
# guest. (string value)
# Deprecated group/name - [compute]/ssh_shell_prologue
#ssh_shell_prologue = set -eu -o pipefail; PATH=$$PATH:/sbin;

# The packet size for ping packets originating from remote linux hosts
# (integer value)
# Deprecated group/name - [compute]/ping_size
#ping_size = 56

# The number of ping packets originating from remote linux hosts
# (integer value)
# Deprecated group/name - [compute]/ping_count
#ping_count = 1

# Unallocated floating IP range, which will be used to test the
# floating IP bulk feature for CRUD operation. This block must not
# overlap an existing floating IP pool. (string value)
# Deprecated group/name - [compute]/floating_ip_range
#floating_ip_range = 10.0.0.0/29

# Network used for SSH connections. Ignored if connect_method=floating
# or run_validation=false. (string value)
# Deprecated group/name - [compute]/network_for_ssh
#network_for_ssh = public


[volume]

#
# From tempest.config
#

# Time in seconds between volume availability checks. (integer value)
#build_interval = 1

# Timeout in seconds to wait for a volume to become available.
# (integer value)
#build_timeout = 300

# Catalog type of the Volume Service (string value)
#catalog_type = volume

# The volume region name to use. If empty, the value of
# identity.region is used instead. If no such region is found in the
# service catalog, the first found one is used. (string value)
#region =

# The endpoint type to use for the volume service. (string value)
# Allowed values: public, admin, internal, publicURL, adminURL, internalURL
#endpoint_type = publicURL

# A list of backend names separated by comma. The backend name must be
# declared in cinder.conf (list value)
#backend_names = BACKEND_1,BACKEND_2

# Backend protocol to target when creating volume types (string value)
#storage_protocol = iSCSI

# Backend vendor to target when creating volume types (string value)
#vendor_name = Open Source

# Disk format to use when copying a volume to image (string value)
#disk_format = raw

# Default size in GB for volumes created by volumes tests (integer
# value)
#volume_size = 1


[volume-feature-enabled]

#
# From tempest.config
#

# Runs Cinder multi-backend test (requires 2 backends) (boolean value)
#multi_backend = false

# Runs Cinder volumes backup test (boolean value)
#backup = true

# Runs Cinder volume snapshot test (boolean value)
#snapshot = true

# Runs Cinder volume clone test (boolean value)
#clone = true

# A list of enabled volume extensions with a special entry all which
# indicates every extension is enabled. Empty list indicates all
# extensions are disabled (list value)
#api_extensions = all

# Is the v1 volume API enabled (boolean value)
#api_v1 = true

# Is the v2 volume API enabled (boolean value)
#api_v2 = true

# DEPRECATED: Update bootable status of a volume Not implemented on
# icehouse  (boolean value)
# This option is deprecated for removal.
# Its value may be silently ignored in the future.
#bootable = true

# Extract correct host info from host@backend (boolean value)
#volume_services = false
</pre>
