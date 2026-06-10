# 📋 Documentação dos Workflows

## Visão Geral

Todos os workflows estão organizados na pasta `codigo/` e podem ser importados diretamente no n8n.

## Workflows Disponíveis

### 1. Cold Outreach Email Campaign
**Arquivo**: `codigo/cold-outreach.json`

**Descrição**: Automatiza o envio de e-mails de prospecção em massa com personalização.

**Funcionalidades**:
- 📧 Lê lista de contatos de uma fonte
- 🎯 Personaliza corpo do e-mail com dados do contato
- 🤖 Gera variações de mensagens com Gemini
- ⏰ Distribui envios ao longo do tempo
- 📊 Registra rastreamento de envios

**Triggers**: Manual ou Schedule (recorrência)

**Requisitos**:
- Gmail configurado
- Google Gemini API ativa
- Arquivo CSV com contatos (email, nome, empresa)

**Como usar**:
1. Importe o workflow
2. Configure credenciais de Gmail
3. Adicione sua lista de contatos
4. Ative o workflow
5. Monitore o progresso em tempo real

---

### 2. Reply Tracking & Analysis
**Arquivo**: `codigo/reply-tracking.json`

**Descrição**: Monitora respostas de e-mails e as analisa com IA.

**Funcionalidades**:
- 📨 Verifica automaticamente caixa de entrada
- 🔍 Identifica novas respostas
- 🧠 Analisa sentimento e intenção com Gemini
- 📊 Classifica leads (hot, warm, cold)
- 💬 Gera respostas automáticas personalizadas
- 📈 Atualiza base de dados com resultados

**Triggers**: Schedule (a cada 5 minutos)

**Requisitos**:
- Gmail com label "Prospection" configurado
- Google Gemini API ativa
- Banco de dados (opcional)

**Como usar**:
1. Configure labels no Gmail
2. Importe o workflow
3. Ajuste intervalo de verificação
4. Ative o workflow
5. Revise análises geradas

---

## Componentes Principais

### Gmail Node
Responsável por:
- Envio de e-mails
- Leitura de mensagens
- Gerenciamento de labels

**Credenciais Necessárias**:
- Email
- App Password (não usar senha da conta)

### Gemini Node
Responsável por:
- Análise de textos
- Geração de respostas
- Classificação de leads

**Credenciais Necessárias**:
- API Key do Google Cloud

### Code Node (JavaScript)
Executa lógica customizada:
- Transformação de dados
- Lógica condicional
- Cálculos complexos

---

## Variáveis Disponíveis

Cada workflow possui variáveis que podem ser customizadas:

```javascript
// Exemplo de variáveis de ambiente
const delay = process.env.EMAIL_DELAY || 5000; // 5 segundos entre envios
const batchSize = process.env.BATCH_SIZE || 20; // 20 e-mails por lote
const geminiModel = process.env.GEMINI_MODEL || "gemini-1.5-pro"; // Modelo a usar
```

---

## Monitoramento e Logs

### Ver Execuções
1. Abra o workflow
2. Clique em **Execution** (lado direito)
3. Veja histórico de execuções

### Interpretar Logs
- ✅ **Verde**: Sucesso
- ⚠️ **Amarelo**: Aviso
- ❌ **Vermelho**: Erro

### Exportar Dados
```bash
# n8n CLI para exportar execuções
n8n export:workflow --id=workflow_id --output=backup.json
```

---

## Customização

### Editar Template de E-mail

Abra o workflow e localize o nó **Set email template**:

```html
<h2>Olá {{firstName}},</h2>
<p>Percebi que {{company}} está crescendo...</p>
<p>Poderia ser interessante conversar sobre como {{productName}} pode ajudar.</p>
```

### Ajustar Filtros de Resposta

No nó **Filter responses**:
```javascript
// Filtrar apenas respostas positivas
return item.sentiment > 0.7;
```

### Mudar Frequência de Execução

No **trigger**:
```
Schedule: Every 5 minutes
ou
Cron: 0 */6 * * * (a cada 6 horas)
```

---

## Boas Práticas

✅ **Faça**:
- Teste workflows em pequena escala primeiro
- Use rate limiting para não sobrecarregar APIs
- Mantenha logs de todas as ações
- Backup regular dos workflows

❌ **Não faça**:
- Não exponha chaves de API em código
- Não envie muitos e-mails simultaneamente
- Não ignore erros e warnings
- Não deixe credenciais em plain text

---

## Troubleshooting

### Workflow não executa
- Verifique se credenciais estão corretas
- Confirme se APIs estão ativas
- Veja os logs de erro

### E-mails não são enviados
- Verifique cota de API do Gmail
- Confirme se "Acesso de apps menos seguros" está habilitado
- Veja se há filtros de spam

### Gemini retorna respostas vazias
- Verifique se API Key é válida
- Confirme se quotas não foram excedidas
- Tente com um prompt mais específico

---

## Próximos Passos

1. 📖 Explore os workflows existentes
2. 🔧 Customize conforme suas necessidades
3. 🚀 Implemente em produção com cuidado
4. 📊 Monitore métricas de performance
5. 🔄 Itere e melhore continuamente

