# soc-lab-crowdsec-kali
Laboratório de monitoramento e detecção de eventos utilizando CrowdSec no Kali Linux.

# CrowdSec no Kali Linux: Monitoramento e Detecção de Ataques SSH

## Objetivo

Configurar um laboratório básico de monitoramento e detecção de eventos de segurança utilizando CrowdSec no Kali Linux.

---

## Ambiente

### Hardware

* Intel Core i7-10700T
* 16 GB RAM
* VMware Workstation

### Máquina Virtual

* Sistema Operacional: Kali Linux
* Interface monitorada: eth0

---

## Ferramentas Utilizadas

* CrowdSec
* OpenSSH Server
* VMware
* Windows Host

---

## Cenário de Teste

O objetivo foi validar a capacidade do CrowdSec de monitorar logs SSH e identificar tentativas de autenticação inválidas.

Fluxo utilizado:

Windows Host → SSH → Kali Linux → CrowdSec → Logs → Alertas

---

## Etapas Realizadas

### 1. Instalação do CrowdSec

Instalação do serviço e validação da versão instalada.

### 2. Ativação do serviço

Configuração para inicialização automática e validação do status do serviço.

### 3. Instalação das coleções

Coleções utilizadas:

* crowdsecurity/linux
* crowdsecurity/sshd

### 4. Configuração da aquisição de logs

Arquivo configurado:

/etc/crowdsec/acquis.yaml

Configuração utilizada:

source: journalctl
journalctl_filter:

* "_SYSTEMD_UNIT=ssh.service"
  labels:
  type: sshd

### 5. Troubleshooting

Durante a configuração foram encontrados alguns problemas:

* Interface sem obtenção de IP via DHCP
* Parser SSH não processando eventos
* Configuração incorreta do acquis.yaml
* Eventos sendo ignorados por whitelist

A análise das métricas e dos logs permitiu identificar e corrigir cada etapa.

### 6. Simulação de Ataque

Foram realizadas múltiplas tentativas de autenticação SSH inválidas a partir da máquina host.

Exemplo:

ssh kali@IP_DO_KALI

### 7. Validação

Comandos utilizados:

sudo cscli metrics

sudo cscli alerts list

sudo cscli decisions list

sudo journalctl -u ssh.service

sudo cscli explain

---

## Aprendizados

* Funcionamento do CrowdSec
* Estrutura de parsers
* Coleções e cenários
* Monitoramento via journalctl
* Logs SSH
* Processo de troubleshooting
* Whitelists
* Decisões de bloqueio
* Conceitos de detecção de brute force

---

## Próximos Passos

* Instalar Suricata
* Criar ambiente Wazuh
* Integrar múltiplas fontes de log
* Implementar arquitetura básica de SOC doméstico

---

## Habilidades Desenvolvidas

* Linux
* Segurança de Redes
* Análise de Logs
* Monitoramento de Eventos
* Troubleshooting
* Blue Team
* SIEM
* SOC
