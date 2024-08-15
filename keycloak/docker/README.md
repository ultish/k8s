# Keycloak https

1. Create realm
2. Realm Settings
    1. Unmanaged Attributes: Enabled
3. Create Client
    1. Settings:
        1. Set clientID
        2. Set Valid redirect URI: http://localhost:4200/*
        3. Web Origins: *
        4. Client Authentication: off
        5. Authorization: off
        6. Standard flow: yes
        7. Implicit flow: yes
        8. Direct Access Grants: yes?
    2. Client Scopes:
        1. Root-dedicated scope:
            1. Add Mapper by configuration 
                1. User Attribute
                    1. name: x509-dn-mapper
                    2. User attribute: x509_dn
                    3. Token Claim Name: x509_dn
                    4. Add to ID token
                    5. Add to access token
4. Create User:
    1. username: root
    2. Attributes:
        1. Key: x509_dn, value: CN=root, O=jxhui, ST=Some-State, C=AU
