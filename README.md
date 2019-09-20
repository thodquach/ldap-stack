# LDAP Stack Helm Chart

## Prerequisites Details
* Kubernetes 1.8+
* PV support on the underlying infrastructure

## Chart Details
This chart will do the following:

* Instantiate an instance of OpenLDAP server
* Instantiate an instance of PhpLdapAdmin connect to above OpenLDAP server
* Instantiate an instance of Nginx using above OpenLDAP server to authenticate and proxy pass to the service you want to keep out of public internet

## Installing the Chart

To install the chart with the release name `ldap-stack`:

```bash
$ helm install --name ldap-stack .
```

## Flow of this helm chart

* Start openldap:
    Start openldap with 'example.org domain', but 'example.org' is only an example, you can re-configure follow your domain ...

* Start phpldapadmin:
    Start phpldapadmin to connect above openldap server, also configure user use for nginx authenticate
    You need to using this 'phpldapadmin' to create a admin root - and then create a simple security object
    After that, you can use this simple security object to authen (user, pass) to pass yo your internal service
    EX: I have capture some pictures in images directory to demonstrate the root of security object i have used to
    authenticate to internal service.

* Start nginx proxy
    Start nginx proxy and use user (the simple security object) to authenticate and access the specific internal service you configre.

# NOTES:

