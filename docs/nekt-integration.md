# 🔌 Integração Nekt & IA (Claude + MCP)

Este documento define o contrato de dados e as regras de design que a Inteligência Artificial (Claude) deve seguir ao utilizar o Servidor MCP da Nekt para gerar relatórios. [cite_start]O objetivo principal do sistema é atuar transformando dado bruto em inteligência de negócio[cite: 2].

## 1. O Fluxo de Trabalho da IA
1. O usuário envia um prompt em linguagem natural.
2. [cite_start]O Claude utiliza a tool `execute_sql_query` (via Nekt MCP Server) para explorar as tabelas e testar a extração do dado bruto à informação.
3. O Claude devolve um objeto JSON contendo a query final e a configuração visual para o frontend.

## 2. Formato de Saída Esperado (JSON)
O Claude **deve** retornar estritamente um objeto JSON com esta estrutura. Não deve incluir dados hardcoded no array `data`, pois o frontend fará o fetch em tempo real via Nekt Data API.

```json
{
  "sql_query": "SELECT category, SUM(value) as total FROM sales GROUP BY category...",
  "highcharts_config": {
    "chart": { 
      "type": "column",
      "backgroundColor": "transparent" 
    },
    "title": { 
      "text": "Receita por Categoria",
      "style": { "color": "#1A2234" }
    },
    "series": [{ 
      "name": "Receita",
      "data": [] 
    }] 
  }
}
