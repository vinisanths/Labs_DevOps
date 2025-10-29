# Lab: Automação de Ambientes Locais com Vagrant

Este projeto documenta o uso do **Vagrant** e **VirtualBox** para criar e gerenciar ambientes de desenvolvimento virtuais, isolados e reprodutíveis.

O objetivo é demonstrar como a Infraestrutura como Código (IaC) pode ser aplicada localmente para padronizar ambientes, evitando o clássico "mas funciona na minha máquina".

## 🎯 Objetivo

* Aprender a provisionar VMs (Máquinas Virtuais) via linha de comando.
* Criar ambientes de desenvolvimento padronizados e descartáveis.
* Entender o fluxo de trabalho básico do Vagrant.

## 🛠️ Tecnologias Utilizadas

* **[Vagrant](https://www.vagrantup.com/)**: Ferramenta para construir e gerenciar ambientes de máquinas virtuais.
* **[VirtualBox](https://www.virtualbox.org/)**: Provedor de virtualização que executa as VMs.

## 📋 Passos do Laboratório

O fluxo de trabalho para provisionar e acessar as VMs foi o seguinte:

### 1. Pré-requisitos

* [Instalar o VirtualBox](https://www.virtualbox.org/wiki/Downloads).
* [Instalar o Vagrant](https://developer.hashicorp.com/vagrant/downloads).

### 2. Provisionando um Ambiente (Ubuntu)

1.  **Criar um diretório de trabalho:**
    ```bash
    mkdir vagrant-ubuntu
    cd vagrant-ubuntu
    ```
2.  **Inicializar o Vagrant:** Este comando cria um `Vagrantfile` e especifica a "box" (imagem) que queremos usar.
    ```bash
    # (Usado nas capturas de tela)
    vagrant init ubuntu/jammy64
    ```
3.  **Ligar a VM:** Este comando lê o `Vagrantfile` e faz todo o trabalho: baixa a box (se não existir localmente), cria a VM no VirtualBox e a inicializa.
    ```bash
    vagrant up
    ```

### 3. Acessando a VM

* Uma vez que a VM está "running", o acesso é feito de forma simples via SSH:
    ```bash
    vagrant ssh
    ```
* (Dentro da VM) Para confirmar, verificamos o usuário:
    ```bash
    vagrant@ubuntu-jammy:~$ whoami
    vagrant
    ```

### 4. Gerenciando Múltiplas VMs

* O mesmo processo foi repetido para um ambiente **CentOS** em um diretório separado, provando a capacidade de gerenciar múltiplos ambientes distintos sem conflito.

### 5. Comandos Essenciais de Gerenciamento

* **Verificar o status:** `vagrant status`
* **Desligar a VM:** `vagrant halt`
* **Destruir a VM (remover do disco):** `vagrant destroy`

## 🏁 Resultado

Com o Vagrant, é possível definir ambientes de desenvolvimento complexos em um único arquivo de configuração (`Vagrantfile`), garantindo que todos na equipe tenham um ambiente idêntico e funcional com apenas um `vagrant up`.