Industrial Automation Dashboard — Node-RED, OPC-UA & MySQL

Sistema completo de controle, supervisão, histórico e monitoramento de uma planta industrial, desenvolvido como prova técnica da São Paulo Skills (Indústria 4.0). Este projeto integra Node-RED, MySQL, OPC-UA, dashboards interativos e autenticação avançada para controlar e monitorar uma célula industrial real com sensores, atuadores pneumáticos, atuadores elétricos e câmera IP.


🚀 **Visão Geral do Sistema**

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

🔐 **1. Autenticação e Segurança**

A tela inicial possui:
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

🧭 **2. Navegação (Tela Inicial)**

Recursos:
- Barra de navegação superior com hover animado
- Slider de imagens automático a cada 5s
- Barra inferior com informações da equipe animadas horizontalmente
- Acesso a todas as seções do sistema
- Layout responsivo seguindo o padrão da prova

---

⚙️ **3. Controle e Supervisão da Planta**

Tela completa que permite:

**🔧 Modo Manual / Automático**
- Botão para alternar os modos
- Modo Manual desabilita processos automáticos
- Modo Automático segue a lógica pré programada da planta

**🔩 Atuadores Pneumáticos**
- Controle individual
- Leitura de sensores AV/RC
- Comandos de avanço/recuo

**🔌 Atuadores Elétricos**
- Slider para controle de posição
- -Slider de velocidade
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

📦 **4. Tela de Estoque**

- Representação visual dos 9 slots
- Cada slot muda de cor conforme a peça armazenada
- Contador mostrando quantidade total
- Dados sincronizados ao banco MySQL

---

🗃️ **5. Histórico em Pilhas**

- Exibição das últimas 10 peças detectadas
- Itens mais novos substituem os antigos
- Gráficos atualizados em tempo real
- Botão “Limpar Histórico” com:
  * Pop-up de confirmação
  * Pop-up de senha
  * Pop-up de sucesso ou erro
  * Reset do gráfico e tabela

---

🗄️ **6. Tela Banco de Dados**

- Dropdown para escolher tabela
- Filtros por cor (vermelho, azul, verde etc.)
- Botão Reset (remove filtros sem recarregar tabela)
- Geração automática de PDF com:
  * Tabela selecionada
  * Dados reais sincronizados
  * Nome personalizado usando timestamp
  * Layout conforme especificação da prova

---

📷 **7. Tela Câmera**

- Pop-up pedindo confirmação antes de iniciar a live
- Streaming da câmera disponível em todas as telas
- Acompanhamento em tempo real da planta

---

🔑 **8. Recriação de Senha**

- Tela específica acessada via “Esqueceu a senha?”
- Altera a senha no sistema de forma real
- Pop-up de sucesso redireciona para o login

---

# 📚 **Banco de Dados (MySQL)**

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

📄 **Relatório PDF**

O sistema gera um arquivo com o nome:

```
Relatório SP (DD-MM-AAAA às HH-MM-SS).pdf
```

Inclui:
- Dados sincronizados
- Tabela atual filtrada

---

📸 **Prints das Telas**
![img57](https://github.com/user-attachments/assets/72340b35-0e8c-45fa-adc5-036d9456987d)


---


