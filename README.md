# Force 10 Z9000

## Connecting 

```
ssh -o KexAlgorithms=diffie-hellman-group1-sha1,diffie-hellman-group14-sha1,diffie-hellman-group-exchange-sha1 -o HostKeyAlgorithms=+ssh-rsa -o Ciphers=3des-cbc admin@192.168.1.1
```

## Firmware

- Latest - https://www.dell.com/support/home/en-au/drivers/driversdetails?driverid=jwxx1&oscode=naa&productcode=force10-z9000
- Archive of files
    - [FTOS-ZB-9.7.0.0P19.bin](FTOS-ZB-9.7.0.0P19.bin)
    - [FTOSBOOT-ZB-3.0.1.5.bin](FTOSBOOT-ZB-3.0.1.5.bin)

## Ansible

- https://github.com/ansible-collections/dellemc.os9

```
os9_system:
  hostname: core-switch01
  reload_type:
      auto_save: true
      boot_type: normal-reload
      boot_type_state: absent
      config_scr_download: true
      dhcp_timeout: 5
      retry_count: 3
      relay: true
      relay_remote_id: ho
      vendor_class_identifier: aa
```
