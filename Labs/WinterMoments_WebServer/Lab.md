# ❄️ Winter Gallery Lab - Vagrant Web Server

Este repositório contém as configurações de Infraestrutura como Código (IaC) para provisionar um servidor web local utilizando Vagrant e VirtualBox. O objetivo deste projeto é demonstrar a automação de um ambiente de desenvolvimento CentOS rodando Apache.

## 📋 Visão Geral

O projeto sobe automaticamente uma Máquina Virtual (VM), configura o networking privado e público, instala o servidor HTTP Apache e serve uma aplicação web de demonstração.

* **OS:** CentOS Stream 9
* **Servidor Web:** Apache (httpd)
* **IP Privado:** 192.168.56.22
* **Memória Alocada:** 1024 MB

## 🚀 Como Usar

### Pré-requisitos
* [VirtualBox](https://www.virtualbox.org/) instalado.
* [Vagrant](https://www.vagrantup.com/) instalado.

### Passos para Execução

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/seu-usuario/winter-gallery-lab.git](https://github.com/seu-usuario/winter-gallery-lab.git)
    cd winter-gallery-lab
    ```

2.  **Inicie a Máquina Virtual:**
    O Vagrant irá baixar a box (se necessário) e provisionar o ambiente conforme definido no `Vagrantfile`.
    ```bash
    vagrant up
    ```

3.  **Acesse a Aplicação:**
    Abra seu navegador e acesse o endereço IP configurado:
    > http://192.168.56.22

4.  **Acesso SSH (Opcional):**
    Para explorar o terminal do servidor:
    ```bash
    vagrant ssh
    ```

## ⚙️ Estrutura do Vagrantfile

O arquivo de configuração define:
* A box base (`eurolinux-vagrant/centos-stream-9`).
* Configuração de rede `private_network` para acesso fixo.
* Customização do provedor VirtualBox para uso de GUI (opcional) e memória.

## 📸 Screenshots

*O ambiente evoluiu de uma configuração simples de texto para um template web completo.*

## 🤝 Contribuição

Sinta-se à vontade para fazer um fork deste projeto e testar com outros servidores web (Nginx) ou provisionadores (Ansible).

## 📄 Licença

Distribuído sob a licença MIT.