# TryHackMe — Networking Basics (Pre Security)

**Sala:** [Networking Basics](https://tryhackme.com/room/introtolan)
**Trilha:** Pre Security
**Dificuldade:** Iniciante
**Data:** Agosto/2026

## 🎯 Objetivo

A sala introduz conceitos fundamentais de redes: modelo TCP/IP, diferença entre hub/switch/router, e como dispositivos se comunicam dentro de uma LAN. O desafio final pede para identificar o endereço IP de um dispositivo específico numa topologia de rede simulada.

## 🧠 Conceitos revisados

- **Hub** opera na camada física, retransmite tudo para todas as portas (sem inteligência)
- **Switch** opera na camada de enlace, usa endereços MAC para encaminhar o tráfego só para o destino correto
- **Router** opera na camada de rede, conecta redes diferentes usando endereços IP

## 🔧 Processo

1. Acessei a VM da sala pelo navegador (AttackBox integrada do THM)
2. Usei o comando abaixo para verificar minha própria configuração de rede:
   ```bash
   ifconfig
   ```
3. Identifiquei meu IP local e a máscara de sub-rede (`/24`), o que me permitiu calcular quantos hosts a rede suportava (254 hosts utilizáveis)
4. Analisei o diagrama de topologia fornecido pela sala e mapeei quais dispositivos estavam no mesmo domínio de broadcast
5. Para responder a pergunta final, precisei identificar qual dispositivo estava conectado à porta específica do switch, cruzando a tabela MAC fornecida com o diagrama

## ✅ Resultado

Flag: `THM{***censurado***}`

## 💡​ O que aprendi

Antes dessa sala eu confundia switch com router com frequência. Ficou claro na prática que a diferença central é **em qual camada do modelo OSI cada um decide para onde mandar o pacote** — switch decide por MAC (camada 2), router decide por IP (camada 3). Isso vai ser importante quando eu começar a analisar tráfego de rede com Wireshark mais pra frente.

## 📎 Referências

- [TryHackMe - Networking Basics](https://tryhackme.com/room/introtolan)
- Modelo OSI / TCP-IP (material próprio da sala)
