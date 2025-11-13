# Ansible Role CSR
[![CI](https://github.com/supertarto/ansible-role-csr/actions/workflows/ci.yml/badge.svg)](https://github.com/supertarto/ansible-role-csr/actions/workflows/ci.yml)

Create a CSR with Ansible. You have to get it signed by your authority and to import your certs with other role.

## Requirements

None

## Tested plateform

* Debian 12 (Bookworm)
* Debian 13 (Trixie)

## Role variables

The path to your private key and to your csr; It will be created if absent.
```yml
csr_private_key_path: "/etc/ssl/private/"
csr_output_path: "/etc/ssl/csr"
```

Your csr common name.
```yml
csr_common_name: "csr_test.example.com"
```

Your key type and size
```yml
csr_type: "RSA"
csr_key_size: "4096"
```

Some specification about your organization
```yml
csr_country_name: "FR"
csr_organization_name: "My Orga Name"
csr_state: "My State"
csr_locality: "My town"
csr_organizational_unit: "IT"
csr_mail_address: "admin_mail@example.com"
```

Owner and group of your private kay and csr
```yml
csr_private_key_owner: "root"
csr_private_key_group: "ssl-cert"
csr_csr_owner: "root"
csr_csr_group: "ssl-cert"
```

Subject Alternative Name, if needed. "IP:" and "DNS:" will be automatically added.
```yml
csr_san: []
  # Example
  # - "alternative_name.example.com"
  # - "192.168.1.1"
  # - ""
```
## License

GPL V3.0
