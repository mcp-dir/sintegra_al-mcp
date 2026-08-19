---
name: sintegra_al-mcp
description: Skill da REST API do SINTEGRA: AL na MCP.AI: 1 endpoint em /api/sintegra_al. SINTEGRA: AL, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SINTEGRA: AL — REST API skill

Você tem acesso à **SINTEGRA: AL** REST API na MCP.AI.

> SINTEGRA: AL, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/sintegra_al
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/sintegra_al/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/sintegra_al/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `sintegra_al_consultar`

SINTEGRA: AL, consulta em fonte oficial. _(POST /api/sintegra_al/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `ie` | string | Não | Parâmetro de consulta "ie". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_sintegra_al` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
