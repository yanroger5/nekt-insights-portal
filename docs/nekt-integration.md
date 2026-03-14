# Integração Nekt & Highcharts

## Formato de Saída Esperado (JSON)
Para que o frontend renderize corretamente, o Claude deve gerar um objeto seguindo este padrão:

```json
{
  "sql_query": "SELECT column_a, column_b FROM table...",
  "highcharts_config": {
    "chart": { "type": "column" },
    "title": { "text": "Título Gerado pela IA" },
    "series": [{ "data": [] }] 
  }
}
