# ldap-stack
    ldap stack for authen proxy with nginx
    Use ldap to store internal users, and use these users to authen by using nginx
    to pass to your internal service

# Start openldap
    Start openldap with example.org
    'example.org' is only a example, you can re-configure follow your domain ...

# Start phpldapadmin
    Start phpldapadmin to connect ldap db, also configure user for ldap service
    You need to using this 'phpldapadmin' to create a admin root -  and then create a security object
    After that, you can use this security object to authen (user,pass) to pass yo your internal services
    EX: I have capture a picture 'db-ldap-example.png' to show you the root of security object i have used to
    authen to my internal service.


# Start nginx proxy
    Start nginx proxy and use user (security object) to authen to access the specific example subdomain you want

# NOTES:
