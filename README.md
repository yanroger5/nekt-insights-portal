# nekt-insights-portal
AI-Powered BI Portal using Nekt MCP, Claude, and Highcharts.

# 📊 Nekt Insights Portal

O **Nekt Insights Portal** é uma plataforma de Business Intelligence (BI) de próxima geração. Ele permite que usuários consultem dados complexos do Lakehouse da Nekt usando linguagem natural, transformando respostas em gráficos interativos do Highcharts.

## 🛠️ Stack Tecnológica
- **Framework:** Next.js 15 (App Router)
- **Estilização:** Tailwind CSS
- **Gráficos:** Highcharts (highcharts-react-official)
- **IA:** Anthropic Claude (via SDK & MCP Server)
- **Dados:** Nekt Data API v2
- **Gestão:** Linear (Metodologia Ágil)

## 🏗️ Arquitetura do Sistema
O projeto opera em dois fluxos principais:
1. **Fluxo de Criação (IA):** O Claude utiliza o Servidor MCP da Nekt para validar esquemas de tabelas e gerar queries SQL precisas + configurações de interface (JSON).
2. **Fluxo de Runtime (Data):** O Frontend consome a Data API da Nekt diretamente usando as queries armazenadas para garantir dados em tempo real sem custo de tokens de IA.

## 📋 Variáveis de Ambiente Necessárias
Crie um arquivo `.env.local` com as seguintes chaves:
- `NEXT_PUBLIC_NEKT_API_URL`
- `NEKT_API_TOKEN`
- `ANTHROPIC_API_KEY`
- `NEKT_MCP_SERVER_URL`

## 🚀 Como iniciar
1. Clone o repositório
2. `npm install`
3. `npm run dev`
