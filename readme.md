# ansible-tinc
A role for Ansible to setup [tinc][tinc].

## Usage
The example playbook below should be pretty self explanatory. The `name` key is
optional for nodes. So is the `master` key, but in order to have a functional
tinc network, you need at least one of these. The nodes that have a `master` key
will be used in the `ConnectTo` directives of the tinc configuration.

### Example playbook
```yaml
---
- hosts: all
  vars:
    network:
      name: tyilnet
      cidr: 10.0.1.0/24
      nodes:
        sessifet:
          ip: 10.0.1.1
          rsa: |
            MIIBCgKCAQEAuS2aZQZoVBF33AJEQQItlHgH4rg4tbA8OriJcOq9kZ/xvr53k5q4
            zubunvfkf4Bnwq4LLFDbXpOjKWjG2uZya+BTAwhyXkIcYdcf7JRv6EPmOM3G2p2q
            zBSc65b92S0waEhlkI8QwpRL6C8JXQ5sAByrJYInAFbhVuRJoa5GRpUUH97Owix0
            uX8zbfUFfjlGuhqpiHD+2wn9zShAWrz7TYLBIBvAtVoXr8Yx7uaVi5Ramjye0aCM
            /iijMYX4FhjXRF6X4nYOPuYDI/we+I3QuBLv69vgYQm3ITM6WeqkwP+pV45dqx98
            ozkzqs1p5lESUkNgOrnCK4IOJ3tIY/+deQIDAQAB
        krata:
          name: web1
          ip: 10.0.1.2
          rsa: |
            MIIBCgKCAQEAuS2aZQZoVBF33AJEQQItlHgH4rg4tbA8OriJcOq9kZ/xvr53k5q4
            zubunvfkf4Bnwq4LLFDbXpOjKWjG2uZya+BTAwhyXkIcYdcf7JRv6EPmOM3G2p2q
            zBSc65b92S0waEhlkI8QwpRL6C8JXQ5sAByrJYInAFbhVuRJoa5GRpUUH97Owix0
            uX8zbfUFfjlGuhqpiHD+2wn9zShAWrz7TYLBIBvAtVoXr8Yx7uaVi5Ramjye0aCM
            /iijMYX4FhjXRF6X4nYOPuYDI/we+I3QuBLv69vgYQm3ITM6WeqkwP+pV45dqx98
            ozkzqs1p5lESUkNgOrnCK4IOJ3tIY/+deQIDAQAB
        seibee:
          ip: 10.0.1.3
          master: true
          rsa: |
            MIIBCgKCAQEAuS2aZQZoVBF33AJEQQItlHgH4rg4tbA8OriJcOq9kZ/xvr53k5q4
            zubunvfkf4Bnwq4LLFDbXpOjKWjG2uZya+BTAwhyXkIcYdcf7JRv6EPmOM3G2p2q
            zBSc65b92S0waEhlkI8QwpRL6C8JXQ5sAByrJYInAFbhVuRJoa5GRpUUH97Owix0
            uX8zbfUFfjlGuhqpiHD+2wn9zShAWrz7TYLBIBvAtVoXr8Yx7uaVi5Ramjye0aCM
            /iijMYX4FhjXRF6X4nYOPuYDI/we+I3QuBLv69vgYQm3ITM6WeqkwP+pV45dqx98
            ozkzqs1p5lESUkNgOrnCK4IOJ3tIY/+deQIDAQAB
  roles:
    - tinc
```

## Todo
- Remove unused files in the `hosts` directory

## License

[tinc]: https://www.tinc-vpn.org/
