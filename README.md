# 🔐 Lab: Auditoria de Senhas e Brute Force com Medusa

![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white) ![Medusa](https://img.shields.io/badge/Tool-Medusa-red?style=for-the-badge) ![Metasploitable](https://img.shields.io/badge/Target-Metasploitable2-black?style=for-the-badge) ![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge)

> "A segurança de um sistema é tão forte quanto a sua senha mais fraca."

Este repositório documenta o desafio prático realizado durante o **Bootcamp de Cibersegurança da DIO**. O objetivo foi configurar um ambiente de laboratório vulnerável e executar auditorias de autenticação (Ataques de Força Bruta) utilizando a ferramenta **Medusa** no Kali Linux, visando compreender vetores de ataque e implementar medidas de mitigação.

## ⚠️ Aviso Legal (Disclaimer)

**ESTE PROJETO FOI REALIZADO EM AMBIENTE CONTROLADO PARA FINS EDUCACIONAIS.**
As técnicas aqui demonstradas foram executadas em uma rede interna isolada (Host-Only) contra máquinas virtuais vulneráveis (Metasploitable 2 / DVWA) de minha propriedade. O autor não se responsabiliza pelo uso indevido dessas informações em alvos não autorizados.

## 🎯 Objetivos de Aprendizagem

* 🧱 **Infraestrutura:** Configuração de laboratório de pentest com VirtualBox (Kali Linux vs Metasploitable 2).
* ⚔️ **Offensive Security:** Execução de ataques de dicionário e força bruta em protocolos de rede (FTP, SSH) e formulários Web.
* 🛡️ **Defensive Engineering:** Análise de logs e proposta de *Hardening* (fortalecimento) de servidores.

## 🛠️ Cenário e Ferramentas

### Arquitetura do Lab
* **Atacante:** Kali Linux (Rolling Edition) via VirtualBox.
* **Alvo:** Metasploitable 2 (Linux intencionalmente vulnerável).
* **Rede:** Configuração *Host-Only* (sem acesso à internet externa para evitar vazamentos).

### Softwares Utilizados
* **Medusa:** Ferramenta de força bruta modular, paralela e rápida.
* **Nmap:** Para reconhecimento de portas e serviços ativos.
* **Wordlists:** Listas de senhas comuns (ex: `rockyou.txt` ou listas customizadas menores).

## ⚙️ Execução dos Testes (Proof of Concept)

### 1. Reconhecimento (Recon)
Antes de atacar, é necessário mapear a superfície de ataque.
```bash
# Identificando serviços e versões no alvo
nmap -sV -p- [IP_DO_METASPLOITABLE]
