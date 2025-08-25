# Firewall

Segue um passo a passo para a configuração clássica dde um servidor Firewall.

<br/>


## 1. Habilitar o encaminhamento de pacotes (IP Forwarding)

<br/>

Crie o arquivo `/etc/sysctl.d/99-custom-forwarding.conf`:

```bash
sudo vim /etc/sysctl.d/99-custom-forwarding.conf
```

<br/>

E, adicione o conteúdo abaixo:

```bash
net.ipv4.ip_forward=1
```

<br/>

Aplique a configuração:

```bash
sudo sysctl -p
```

<br/>

## 2. Configuração do NFTables 

<br/>

Substitua o conteúdo do arquivo `/etc/nftables.conf` pelo conteúdo do arquivo [nftables.conf](./nftables.conf) deste repositório.

<br/>

## 3. Aplicar a configuração e habilitar o Firewall

<br/>

Testar e aplicar a configuração:

```bash
sudo nft -f /etc/nftables.conf
```

<br/>

Verificar as regras ativas:

```bash
sudo nft list ruleset
```

<br/>

Habilitar o serviço do NFTables

```bash
sudo systemctl enable nftables
sudo systemctl start nftables
```

