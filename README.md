

## Sumário

- [Objetivo](#objetivo)
- [Ambiente Utilizado](#ambiente-utilizado)
- [Objetivos do Laboratório](#objetivos-do-laboratório)
- [Configuração](#configuração)
- [Evidências](#evidências)
- [Aprendizados](#aprendizados)
- [Próximos Passos](#próximos-passos)
- [Laboratórios do SOC Home Lab](#-laboratórios-do-soc-home-lab)

# CrowdSec Lab - Monitoramento e Detecção de Ameaças SSH

## Objetivo

Implementar e configurar o CrowdSec para monitoramento de logs, detecção de tentativas de brute force SSH e geração de alertas em ambiente Linux.

---

## Ambiente Utilizado

### Hardware

* Intel Core i7-10700T
* 16 GB RAM
* VMware Workstation

### Sistema Operacional

* Kali Linux

### Ferramentas

* CrowdSec
* OpenSSH
* VMware

---

## Objetivos do Laboratório

* Instalar e configurar o CrowdSec
* Monitorar eventos SSH
* Detectar tentativas de brute force
* Analisar métricas e alertas
* Entender o funcionamento de collections, parsers e scenarios

---

## Configuração

Arquivo de aquisição configurado:

```yaml
source: journalctl
journalctl_filter:
  - "_SYSTEMD_UNIT=ssh.service"
labels:
  type: sshd
```

---

## Evidências

### Status do Serviço

![CrowdSec Status](screenshots/crowdsec-status.png)

### Métricas do CrowdSec

![Metrics](screenshots/metrics.png)

### Alertas Gerados

![Alerts](screenshots/alerts.png)

### Cenários SSH

![SSH Scenarios](screenshots/ssh-scenarios.png)

---

## Aprendizados

Durante este laboratório foi possível compreender:

* Monitoramento de logs SSH
* Configuração de acquisition files
* Collections e Scenarios
* Parsers do CrowdSec
* Métricas e Alertas
* Conceitos de brute force detection
* Troubleshooting em Linux
* Conceitos básicos de SOC e Blue Team

---

## Próximos Passos

* Integração com Suricata
* Integração com Wazuh
* Correlação de eventos
* Construção de um mini SOC em laboratório

```
```


---

## 🔗 Laboratórios do SOC Home Lab

| Lab | Repositório | Descrição |
|-----|-------------|-----------|
| 🛡️ Wazuh SIEM/XDR | [wazuh-lab](https://github.com/gabrielzaccaferreira/wazuh-lab) | Instalação, configuração e regras customizadas do Wazuh |
| 🐉 Kali Linux | [kali-remote-access-lab](https://github.com/gabrielzaccaferreira/kali-remote-access-lab) | Setup do ambiente de ataque e acesso remoto |
| 🔍 Suricata IDS/IPS | [suricata-lab](https://github.com/gabrielzaccaferreira/suricata-lab) | Detecção de intrusão em rede, regras customizadas |
| 🛡️ CrowdSec | [soc-lab-crowdsec-kali](https://github.com/gabrielzaccaferreira/soc-lab-crowdsec-kali) | IPS colaborativo com blocklists dinâmicas |
| 🔬 Wireshark | [wireshark-analysis-lab](https://github.com/gabrielzaccaferreira/wireshark-analysis-lab) | Análise de tráfego e dissecção de protocolos |
| 🔥 pfSense | [pfsense-lab](https://github.com/gabrielzaccaferreira/pfsense-lab) | Firewall, NAT, VLANs e regras de perímetro |
| 🪟 Windows Server + Sysmon | [windows-server-soc-lab](https://github.com/gabrielzaccaferreira/windows-server-soc-lab) | Telemetria Windows, Sysmon, Red Team vs Blue Team |

> 🌐 Portfólio completo: [gabrielzacca.com.br](https://gabrielzacca.com.br)

