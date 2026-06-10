# AI Email Automation 📧🤖

Sistema inteligente de automação de prospecção e acompanhamento de e-mails utilizando **IA**, **n8n** e **Google Gemini**.

## 📋 Sobre o Projeto

Este projeto automatiza o processo de:
- 📧 **Envio de e-mails** de prospecção em massa
- 🔄 **Rastreamento de respostas** automático
- 🧠 **Análise inteligente** com Google Gemini
- ⚙️ **Orquestração de workflows** com n8n
- 📊 **Acompanhamento de campanhas** personalizadas

## 🚀 Funcionalidades

- ✅ Automação completa de prospecção por e-mail
- ✅ Análise de respostas com IA
- ✅ Rastreamento inteligente de engajamento
- ✅ Integração com Google Gemini
- ✅ Workflows customizáveis via n8n
- ✅ Respostas automáticas e personalizadas

## 🎬 Visualização do Fluxo de Automação

### Fluxo n8n - Cold Outreach Email Campaign with Automated Reply Tracking

![N8N Workflow - Cold Outreach Email Campaign](Captura%20de%20Tela%20(2803).png)

*Fluxo completo da automação de e-mails com rastreamento de respostas, integração com Google Gemini e envio automático via Gmail*

## 🛠️ Tech Stack

| Tecnologia | Descrição |
|------------|-----------|
| **n8n** | Plataforma de automação workflow |
| **Google Gemini** | IA para análise de e-mails |
| **Node.js** | Runtime JavaScript |
| **JSON** | Configuração de workflows |

## 📁 Estrutura do Projeto

```
ai-email-automation/
├── README.md
├── .env.example              # Variáveis de ambiente (modelo)
├── codigo/                   # Pasta com workflows JSON
│   ├── 01-cold-outreach.json
│   ├── 02-reply-tracking.json
│   └── ...
└── docs/
    ├── SETUP.md              # Guia de instalação
    └── WORKFLOWS.md          # Documentação dos workflows
```

## 🔐 Configuração & Segurança

### Variáveis de Ambiente Necessárias

Crie um arquivo `.env` na raiz do projeto:

```env
# Google Gemini API
GEMINI_API_KEY=seu_gemini_api_aqui

# Credenciais de E-mail
EMAIL_USER=seu_email@gmail.com
EMAIL_PASSWORD=sua_senha_de_app_aqui

# Configurações n8n
N8N_HOST=localhost
N8N_PORT=5678

# Base de Dados (opcional)
DATABASE_URL=sua_url_de_conexao_aqui

# Configurações de Proxy (opcional)
PROXY_URL=seu_proxy_aqui
```

> ⚠️ **IMPORTANTE**: Nunca comita o arquivo `.env` com dados sensíveis. Use `.env.example` como template.

## 📦 Workflows Disponíveis

Os workflows estão organizados na pasta `codigo/`:

| Arquivo | Descrição |
|---------|-----------|
| `cold-outreach.json` | Campanha de envio em massa de e-mails de prospecção |
| `reply-tracking.json` | Rastreamento automático de respostas |

## 🔧 Como Usar

### Pré-requisitos

- Node.js v16+ instalado
- n8n instalado (`npm install -g n8n`)
- Conta Google Cloud com API Gemini ativada
- Conta Gmail com [senha de app](https://support.google.com/accounts/answer/185833) gerada

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/Ricardo0800/ai-email-automation.git
cd ai-email-automation
```

2. Configure as variáveis de ambiente:
```bash
cp .env.example .env
# Edite o arquivo .env com suas credenciais
nano .env
```

3. Inicie o n8n:
```bash
n8n start
```

4. Acesse o painel em `http://localhost:5678`

5. Importe os workflows da pasta `codigo/`

## 📋 Importar Workflows no n8n

1. Abra o dashboard do n8n
2. Clique em **Workflows** → **Import from file**
3. Selecione um arquivo JSON da pasta `codigo/`
4. Configure as credenciais necessárias
5. Teste e ative o workflow

## 🤖 Integrações

### Google Gemini
- Análise automática de e-mails recebidos
- Geração de respostas inteligentes
- Classificação de leads

### Gmail
- Envio de e-mails em massa
- Recebimento e monitoramento de respostas
- Integração com labels e categorias

## 📚 Documentação

- [Guia de Configuração Completa](docs/SETUP.md)
- [Documentação dos Workflows](docs/WORKFLOWS.md)

## 🤝 Contribuindo

Contribuições são bem-vindas! Por favor:

1. Faça um Fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 👨‍💻 Autor

**Ricardo0800**  
GitHub: [@Ricardo0800](https://github.com/Ricardo0800)

## 📧 Suporte

Para dúvidas ou sugestões, abra uma [Issue](https://github.com/Ricardo0800/ai-email-automation/issues) no repositório.

---

⭐ Se este projeto foi útil para você, considere dar uma estrela!
