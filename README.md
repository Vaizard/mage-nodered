# mage-nodered

An Ansible role to install Node-RED, a flow-based programming tool (IFTTT alternative). Selected nodes and flows are
installed by default too. Node-red defaults to listening on all IPv4s, port 1880. This role changes only the default
listen port to 2880. Basic security on the installation is enforced - at least one admin user must be defined.

By default this role configures also a basic auth mechanism built in into Node-RED. This acts only as a basic safeguard
to protect all node paths, as only a single user can be defined. You will probably want to use something more flexible,
and fine-grained, such as the included node-red-contrib-auth. This configuration option will most likely cause 
node-red-contrib-auth to fail spectacularly. To disable this built in auth, just set `nodered_nodeauth_user` and 
`nodered_nodeauth_pass` to empty strings.

NOTE that basic authentication is only secure if traffic over https is enforced. While node-red has the ability to run
over https only, any sane deployment should have a propper reverse proxy infront of it. If you look for a role that
is tested and supported, try https://github.org/vaizard/mage-haproxy.
