# Industrial Automation Dashboard — Node-RED, OPC-UA & MySQL

Sistema completo de controle, supervisão, histórico e monitoramento de uma planta industrial, desenvolvido como prova técnica da São Paulo Skills (Indústria 4.0). Este projeto integra Node-RED, MySQL, OPC-UA, dashboards interativos e autenticação avançada para controlar e monitorar uma célula industrial real com sensores, atuadores pneumáticos, atuadores elétricos e câmera IP.


# 🚀 **Visão Geral do Sistema**

Este sistema permite:
- Autenticação de usuários com bloqueio por tentativas
- Acesso a múltiplas telas com navegação personalizada
- Controle e supervisão de uma planta industrial real via OPC-UA
- Consulta e manipulação de banco de dados MySQL
- Geração automática de PDF com dados sincronizados
- Histórico visual de peças produzidas (pilha) com gráficos dinâmicos
- Monitoramento por câmera IP com confirmação
- Controle de estoque com cores dinâmicas
- Modo Manual/Automático com lógica completa de processo

---

🛠️ **Tecnologias Utilizadas**
- Node-RED (Dashboard 1.0)
- OPC-UA (Integração com PLC/CLP)
- MySQL
- Charts / Dashboard UI
- Câmera IP (Streaming)
- HTML/CSS dentro do Node-RED
- Geração de PDF pelo Node-RED

---

## 🔐 **1. Autenticação e Segurança**

A tela Inicial possui:
- Campo de usuário e senha
- Usuário padrão: **senai / 1234**
- Bloqueio automático por 3 tentativas falhas
- Desbloqueio automático após 15 segundos
- Pop-ups dinâmicos para:
  - Erro
  - Sucesso
  - Tentativas bloqueadas
  - Reabilitação do login

Também inclui:
- Botão "Esqueceu a senha?" com recriação real da senha no sistema
- Logout disponível em todas as telas

---

## 🧭 **2. Navegação (Tela Inicial)**

Recursos:
- Barra de navegação superior com hover animado
- Slider de imagens automático a cada 5s
- Barra inferior com informações da equipe animadas horizontalmente
- Acesso a todas as seções do sistema
- Layout responsivo seguindo o padrão da prova

---

## ⚙️ **3. Controle e Supervisão da Planta**

Tela completa que permite:

**🔧 Modo Manual / Automático**
- Botão para alternar os modos
- Modo Manual desabilita processos automáticos
- Modo Automático segue a lógica pré-programada da planta

**🔩 Atuadores Pneumáticos**
- Controle individual
- Leitura de sensores AV/RC
- Comandos de avanço/recuo

**🔌 Atuadores Elétricos**
- Slider para controle de posição
- Slider de velocidade
- Funções:
  * Setup: reseta velocidade e posição
  * Home: envia para posição 0

**📍 Status do Processo**

Sistema mostra dinamicamente:
- “Aguardando início”
- “Separando”
- “Aguardando início da separação inteligente”
- “Separação encerrada”

---

## 📦 **4. Tela de Estoque**

- Representação visual dos 9 slots
- Cada slot muda de cor conforme a peça armazenada
- Contador mostrando quantidade total
- Dados sincronizados ao banco MySQL

---

## 🗃️ **5. Histórico em Pilhas**

- Exibição das últimas 10 peças detectadas
- Itens mais novos substituem os antigos
- Gráficos atualizados em tempo real
- Botão “Limpar Histórico” com:
  * Pop-up de confirmação
  * Pop-up de senha
  * Pop-up de sucesso ou erro
  * Reset do gráfico e tabela

---

## 🗄️ **6. Tela Banco de Dados**

- Dropdown para escolher tabela
- Filtros por cor (vermelho, azul, verde etc.)
- Botão Reset (remove filtros sem recarregar tabela)
- Geração automática de PDF com:
  * Tabela selecionada
  * Dados reais sincronizados
  * Nome personalizado usando timestamp
  * Layout conforme especificação da prova

---

## 📷 **7. Tela Câmera**

- Pop-up pedindo confirmação antes de iniciar a live
- Streaming da câmera disponível em todas as telas
- Acompanhamento em tempo real da planta

---

## 🔑 **8. Recriação de Senha**

- Tela específica acessada via “Esqueceu a senha?”
- Altera a senha no sistema de forma real
- Pop-up de sucesso redireciona para o login

---

## 📚 **Banco de Dados (MySQL)**

*Tabela Estoque*

| Coluna       | Tipo        | Explicação      |
| ------------ | ----------- | --------------- |
| id_slot      | INT PK AI   | Identificador   |
| cor          | VARCHAR(45) | Cor da peça     |
| data_entrada | DATETIME    | Data de entrada |

*Tabela Pilha*

| Coluna     | Tipo        | Explicação       |
| ---------- | ----------- | ---------------- |
| id_posicao | INT PK AI   | Identificador    |
| cor_peca   | VARCHAR(20) | Cor detectada    |
| data_hora  | DATETIME    | Registro da ação |

---

## 📄 **Relatório PDF**

O sistema gera um arquivo com o nome:

```
Relatório SP (DD-MM-AAAA às HH-MM-SS).pdf
```

Inclui:
- Dados sincronizados
- Tabela atual filtrada

---

# 📸 **Prints das Telas**

## Tela de Login
![img57](https://github.com/user-attachments/assets/72340b35-0e8c-45fa-adc5-036d9456987d)

![img61](https://github.com/user-attachments/assets/d84a18dc-0ab5-4514-aa20-daf1c79d91fd)

---

## Tela Inicial
![img68](https://github.com/user-attachments/assets/7f98b322-44d8-469a-9f98-106c2faab17e)

---


## Tela de Controle e Supervisão
![img72](https://github.com/user-attachments/assets/6a426b2d-1d5b-4eff-be21-dbf029ff53e3)

![img73](https://github.com/user-attachments/assets/ba1cbe39-948e-4925-b2a8-5aaaa3ae94d9)

---

## Tela de Estoque
![img77](https://github.com/user-attachments/assets/96208e59-ec22-4834-8162-e90011d27b57)

---

## Tela de Histórico em Pilhas
![img81](https://github.com/user-attachments/assets/4167dce4-a75b-44f1-9c7c-e663f8caba36)

![img85](https://github.com/user-attachments/assets/af02ad65-9be1-4f39-a79e-a0b2da175331)

---

## Tela Banco de Dados
![img93](https://github.com/user-attachments/assets/a8c2b0cf-45f7-473c-8f59-5f0937ac822c)

![img96](https://github.com/user-attachments/assets/b57c9b46-17d6-4b0e-90df-23bf078581cb)

---

## Tela Câmera IP
![img104](https://github.com/user-attachments/assets/a626561c-f2f2-4ad2-ba9d-fc27ebfd1fef)

---

## Tela Recriação de Senha
![img107](https://github.com/user-attachments/assets/836549d8-fdfb-48bc-80ab-305e2c14b280)

---
