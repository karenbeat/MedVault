# 🏥 MedVault: Cofre Médico Descentralizado (DApp)

**Privacidade em Primeiro Lugar. Controle Total sobre seus Dados Médicos. Potencializado pela CESS Network.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

## 🌐 Visão Geral do Projeto

O **MedVault** é uma aplicação descentralizada (DApp) de ponta projetada para resolver o maior desafio da saúde digital: a soberania do paciente sobre seus dados.

Ao casar o **Armazenamento Descentralizado Criptografado (DeOSS) da CESS Network** com a segurança de **Smart Contracts EVM**, o MedVault elimina servidores centrais, intermediários de confiança e senhas.

Este projeto não apenas utiliza a CESS Network para armazenamento, mas a estabelece como a **infraestrutura de confiança e auditabilidade** necessária para um futuro ético da saúde.

### Por que a CESS Network? 🌍

O MedVault é a prova de conceito ideal para a CESS porque demonstra:

* **Camada de Confiança Global:** Uso da CESS como fonte imutável de verdade (Proof-of-Existence) para dados sensíveis.
* **Caso de Uso de Saúde no Mundo Real:** Solução direta para silos de dados e questões de privacidade médica.
* **Fundação Ética:** Criação de uma alternativa descentralizada e resiliente para a saúde digital.

---

## 🧠 Arquitetura do Sistema: Descentralização Pura

O MedVault adota uma arquitetura híbrida descentralizada, eliminando a necessidade de um servidor backend tradicional, confiando inteiramente no cliente e na blockchain.



### 🔹 1. Front-End (Cliente)
O orquestrador da DApp. Toda a criptografia, autenticação e comunicação direta com a CESS e o Smart Contract ocorrem no lado do cliente.

* **Tecnologias Core:** **Next.js**, **TypeScript**, **Ethers.js**, **MetaMask**, **CESS DeOSS REST API**.

### 🔹 2. Back-End On-Chain (Smart Contract EVM)
A camada de lógica de negócios e segurança. Gerencia a **identidade** e as **permissões**.

* **Funções:** `uploadFile`, `grantAccess`, `revokeAccess`, `hasAccess`, `recordAccess`.
* **Responsabilidade:** Garantir a **propriedade imutável** e as **regras de acesso temporal**.

### 🔹 3. Armazenamento Off-Chain (CESS DeOSS)
Onde o arquivo médico criptografado reside. A segurança é garantida pela própria rede CESS.

* **Garantias CESS:** Fragmentação, Redundância Geográfica, Deduplicação e o rigor do **PoDR² (Proof of Data Reduplication and Recovery)**.

---

## 🎨 Funcionalidades do Front-End (Soberania do Paciente)

O Front-End é projetado para ser intuitivo e dar ao paciente o controle total sobre seu histórico médico.

### 🔐 Autenticação Wallet-Based
A identidade é o endereço da carteira. Sem senhas, sem contas centralizadas.
### 📤 Upload Seguro (CESS DeOSS)
O arquivo é enviado diretamente ao DeOSS.

```bash
PUT /file
# Headers obrigatórios: Territory, Account, Message, Signature (garantindo autorização de gateway)
