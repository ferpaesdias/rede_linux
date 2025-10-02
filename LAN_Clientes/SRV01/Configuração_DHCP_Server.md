# DHCP Server

No DHCP Server iremos utilizar o software [Kea DHCP](https://www.isc.org/kea/).

<br/>


## 1. Instalação do Kea DHCP Server

<br/>

Use o comando abaixo para instalar o Kea DHCP Server:

```bash
sudo apt install kea-dhcp4-server
```

<br/>

## 2. Faça backup do arquivo de configuração padrão

<br/>

```bash
sudo mv /etc/kea/kea-dhcp4.conf /etc/kea/kea-dhcp4.conf.bak
```

<br/>

## 3. Crie o arquivo de configuração e configure o DHCP Server

<br/>

Criar o arquivo de configuração:

```bash
sudo vim /etc/kea/kea-dhcp4.conf
```

<br/>

Para configurar o DHCP Server copie o conteúdo do arquivo [kea-dhcp4.conf](./kea-dhcp4.conf) deste repositório. Altere as configurações (interface de rede, endereços de rede, etc) de acordo com a sua necessidade.

<br/>

## 4. Criar diretório para armazenar logs e o leases do DHCP

<br/>

Crie os diretórios para armazenar os logs e os leases do DHCP

```bash
sudo mkdir -p /var/log/kea /var/lib/kea
```

<br/>


## 5. Testar a configuração

<br/>

Verifique se há erros no arquivo de configuração

```bash
sudo kea-dhcp4 -c /etc/kea/kea-dhcp4.conf -W
```

<br/>


## 6. Habilitar e iniciar o serviço do DHCP Server

<br/>

Verifique se há erros no arquivo de configuração

```bash
sudo systemctl enable --now kea-dhcp4-server
```

<br/>


Verifique o status do serviço

```bash
sudo systemctl status kea-dhcp4-server
```