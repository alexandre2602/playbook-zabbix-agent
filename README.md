zabbix-agent
=========

Role responsável por instalar e configurar o Zabbix Agent nos modos passivo ou ativo em máquinas
com sistema operacional CentOS 7.x


Role Variables
--------------

Esta role faz uso das seguintes variáveis.

```
# Variável contendo a versão do Zabbix Agent.
# URL contendo as versões disponíveis: https://repo.zabbix.com/zabbix/
zabbix_agent_version: "4.0"

# Variável contendo a release do Zabbix Agent.
zabbix_agent_release: "4.0-2"

# Define se o agente será ativo ou passivo.
# ativo: o agente envia os dados para o servidor (zabbix server). Valor padrão.
# passivo: o agente aguarda do servidor (zabbix server) os pedidos de coleta de dados.
zabbix_agent_mode: "ativo"

# Variável contendo a porta utilizada pelo serviço zabbix-agent.service
zabbix_agent_port: "10050"

# Define a verbosidade do log do serviço.
# Esse valor vai de 0 a 5.
zabbix_agent_debuglevel: "2"

# IP/DNS do Zabbix Server.
zabbix_agent_server: "10.10.10.10"
```

> Os valores acima são utilizados por padrão.



Example Playbook
----------------

Como utilizar essa role na sua playbook. Exemplo:

    ---
    - name: Playbook de instalação do Zabbix Agent no CentOS 7.x
      hosts: centos-servers
      become: yes
      become_method: sudo
      roles:
       - zabbix-agent

License
-------

BSD

Author Information
------------------

LinkedIn: https://br.linkedin.com/in/ewertonsilva00
