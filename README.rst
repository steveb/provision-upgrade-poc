Simulates an upgrade from a nova based undercloud to ironic provisioned
servers.

Create the initial stack with one nova server::

  openstack stack create --wait -e env-init.yaml -t stack.yaml provision-upgrade

Set deletion_policy: retain on the server::

  openstack stack update --wait -e env-pre.yaml -t stack.yaml provision-upgrade

Upgrade to a pre-provisioned server without deleting the nova server::

  openstack stack update --wait -e env-upgrade.yaml -t stack.yaml provision-upgrade