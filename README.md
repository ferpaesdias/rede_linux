# Rede Linux


Este projeto tem o objetivo de criar uma rede de computadores usando somente servidores Linux.

[Post no blog](https://blog.ferpdias.com.br/projetos/rede_linux/)

<br />

## Diagrama do projeto:

![Diagrama do projeto](/img/diag_rede_linux.png)


## Dados da rede:

- IP da rede: `10.10.0.0/24`
- IP do Gateway: `10.10.0.1`
- IP do servidor DNS: `10.10.0.200`
- Domínio: `totolab.lan`


## Servidores 

A rede terá dois servidores: o **Firewall** e o **Server01**. 


### Firewall

O **Firewall** será gerenciado pelo [nftables](https://wiki.nftables.org/).
- IP WAN: IP público
- IP LAN: 10.10.0.1


### Server01

O **Server01** terá os seguintes serviços: **DHCP**, **DNS**, **LDAP** e **File Server**.

<br />

Descrição de cada serviço:


#### DHCP

- Software: [Kea DHCP](https://www.isc.org/kea/)


#### DNS

- Software: [Bind 9](https://www.isc.org/bind/)


#### LDAP

- Software: [OpenLDAP](https://openldap.org/software/download/)


#### File Server

- Software: [Samba](https://www.samba.org/)

