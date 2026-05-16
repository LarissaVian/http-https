# Relatório — Laboratório de Inspeção HTTP/HTTPS — Fluxo A (Administrador)

> **Como usar este template.** Preencha cada campo `[...]` com sua resposta e arraste as capturas de tela diretamente para os locais indicados. Preserve a formatação Markdown.
>
> **Escopo:** este fluxo inclui HTTP em texto claro, HTTPS sem decriptação e HTTPS com decriptação TLS pelo Fiddler Classic.

---

## Como anexar capturas de tela

1. Faça a captura de tela e salve como PNG.
2. No editor do GitHub ou GitHub.dev, posicione o cursor no local indicado.
3. Arraste o PNG para o editor. O GitHub inserirá uma linha `![image](...)`.

---

## Identificação

| Campo | Valor |
|---|---|
| Nome | [Larissa Conceição Viana / Luana Fernandes Careira] |
| RA | [197375 / 231572] |
| Disciplina | Redes de Computadores |
| Turma | [SI/ N A]|
| Data | [15/05/2026] |
| Fluxo | **A — Aluno com privilégio de administrador** |
| SO utilizado | [Windows 10 ] |
| Ferramenta de proxy | Fiddler Classic |
| Navegador(es) | [Chrome] |
| Decriptação HTTPS habilitada? | [sim] |
| Certificado Fiddler instalado durante a atividade? | [sim] |

---

## Atividade 1 — Primeira captura

### Captura
<img width="1387" height="992" alt="Capturar" src="https://github.com/user-attachments/assets/4d2eb657-fff7-42dc-af78-9315f4ac42d6" />


**Request-line:**

```http
[ex: GET / HTTP/1.1]
GET http://example.com/ HTTP/1.1
```

**Status-line:**

```http
[ex: HTTP/1.1 200 OK]
HTTP/1.1 200 OK
```

**Cabeçalhos do request:**

| Cabeçalho | Função |
|---|---|
| [Host] | [example.com] |
| [Connection] | [keep-alive] |
| [Upgrade-Insecure-Requests] | [1] |
| [User-Agent] | [Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36] |
| [Accept] | [text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7] |
| [Accept-Encoding] | [gzip, deflate] |
| [Accept-Language] | [pt-PT,pt;q=0.9,en-US;q=0.8,en;q=0.7] |

**Resposta:**

| Campo | Valor observado |
|---|---|
| `Content-Type` | [text/html] |
| `Content-Length` ou `Transfer-Encoding` | [gzip] |

---

## Atividade 2 — Anatomia de um GET

### Captura

<!-- arraste a captura aqui: Request Raw e Response JSON -->
<img width="1902" height="987" alt="Capturar" src="https://github.com/user-attachments/assets/a20ef0a3-e280-47f8-851a-9db6328ea3c1" />

**Request-line completa:**

```http
[GET https://httpbingo.org/ HTTP/1.1

```

**Cabeçalhos-chave:**

| Cabeçalho | Valor |
|---|---|
| `Host` | [httpbingo.org] |
| `User-Agent` | [Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36] |
| `Accept` | [text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7] |

**Campos do JSON de resposta:**

```json
{
  "args": [colar valor],
  "headers": [colar valor resumido],
  "origin": [colar valor]
}
```

**Resposta curta:** o que o campo `origin` representa? O `User-Agent` retornado coincide com o enviado?

[resposta]

---

## Atividade 3 — POST e envio de formulário

### Captura
<!-- arraste a captura aqui: POST para /post em Request Raw -->
<img width="1904" height="1006" alt="Capturar" src="https://github.com/user-attachments/assets/320b73d1-64cb-4786-b6d0-5e454336d487" />


**Request-line do POST:**

```http
GET https://httpbingo.org/forms/post HTTP/1.1


```

| Cabeçalho | Valor |
|---|---|
| `Content-Type` | [application/x-www-form-urlencoded] |
| `Content-Length` | [165] |

**Corpo do request:**

```text
POST https://httpbingo.org/post HTTP/1.1
Host: httpbingo.org
Connection: keep-alive
Content-Length: 165
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="142", "Google Chrome";v="142", "Not_A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Origin: https://httpbingo.org
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: https://httpbingo.org/forms/post
Accept-Encoding: gzip, deflate, br, zstd
Accept-Language: pt-PT,pt;q=0.9,en-US;q=0.8,en;q=0.7

custname=LARISSA&custtel=3123456987&custemail=LARIVIANA%40GMAIL.COM&size=large&topping=bacon&topping=cheese&topping=onion&topping=mushroom&delivery=20%3A30&comments=<img width="1912" height="1004" alt="Capturar" src="https://github.com/user-attachments/assets/377da0c1-cf85-49e2-b5ca-e00b71c48726" />

```

**Campo `form` da resposta:**

```json
[colar trecho relevante]
```

**Resposta curta:** qual formato codifica o corpo? Qual aba mostra literalmente os bytes enviados: `WebForms` ou `Raw`?

[resposta]

---

## Atividade 4 — Status codes

### Captura

<!-- arraste a captura aqui: lista do Fiddler com as quatro sessões -->
<img width="1912" height="1004" alt="Capturar" src="https://github.com/user-attachments/assets/edfa360f-1a05-4423-9a3c-7d7f6c01272b" />


| # | Método | URL | Status-line | Tamanho/body |
|---|---|---|---|---|
| 1 | GET | `https://httpbingo.org/status/200` | [HTTP/1.1 200 OK] | [0] |
| 2 | GET | `https://httpbingo.org/redirect-to?status_code=301&url=/get` | [HTTP/1.1 301 Moved Permanently] | [0] |
| 3 | GET | `https://httpbingo.org/status/404` | [HTTP/1.1 404 Not Found] | [0] |
| 4 | GET | `https://httpbingo.org/status/500` | [HTTP/1.1 500 Internal Server Error] | [0] |

**Resposta curta:** no `301`, qual cabeçalho informa o destino do redirecionamento?

[location: /get]

---

## Atividade 5 — Cabeçalhos essenciais

### Captura

<!-- arraste a captura aqui: Inspectors → Headers -->
<img width="1700" height="1018" alt="Capturar" src="https://github.com/user-attachments/assets/9e410be8-81ce-4fb2-b838-5d9f98dc6a39" />

| Cabeçalho | Req/Resp | Valor capturado | Função |
|---|---|---|---|
| `Host` | [Req] | [http.aulasrede.com.br] | [Nome de domínio do servidor] |
| `User-Agent` | [Req] | [Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36] | [Identificação do cliente/navegador] |
| `Accept` | [Req] | [text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7] | [Tipos MIME aceitos na resposta] |
| `Content-Type` | [Resp] | [: application/json; charset=utf-8
] | [MIME do corpo enviado (em POST/PUT)] |
| `Content-Length` / `Transfer-Encoding` | [Resp] | [3078
] | [Tamanho do corpo em bytes quando o tamanho é conhecido antecipadamente] |
| `Content-Encoding` | [Resp] | [gzip] | [Compressão aplicada ao corpo] |
| `Set-Cookie` | [Resp] | [teste=1; domain=http.aulasrede.com.br; path=/; secure] | [Cookie a ser armazenado pelo cliente] |
| `Cache-Control` | [Resp] | [no-store] | [Política de cache (no-store, max-age=3600, public)] |
| `Strict-Transport-Security` | [Resp] | [max-age=31536000; includeSubDomains] | [Força uso de HTTPS em acessos futuros (HSTS)] |

**Resposta curta:** qual é o papel de `Content-Encoding` e de `Strict-Transport-Security`?
O primeiro otimiza a transferência de dados e o segundo garante a segurança da comunicação.


[resposta]

---

## Atividade 6 — HTTP vs HTTPS

### Captura — HTTP puro

<!-- arraste a captura aqui: http://http.aulasrede.com.br/get com redirecionamento 301 para HTTPS -->
<img width="1915" height="773" alt="Capturar" src="https://github.com/user-attachments/assets/e21f8d9c-306e-447e-8eb9-66d773f510a5" />

### Captura — HTTPS sem decriptação

<!-- arraste a captura aqui: https://http.aulasrede.com.br/get sem decriptação -->
<img width="1902" height="816" alt="Capturar" src="https://github.com/user-attachments/assets/76986dbc-549d-4ecc-8cdb-3631c3bb0a7c" />

### Captura — HTTPS com decriptação

<!-- arraste a captura aqui: https://http.aulasrede.com.br/get com decriptação -->
<img width="1908" height="1016" alt="Capturar" src="https://github.com/user-attachments/assets/3e54257c-f2fb-49fd-89b7-50f5777fa891" />

[site caiu/ não funcionou mais]
| Situação | O que ficou visível? | O que ficou oculto? |
|---|---|---|
| HTTP puro | [...] | [...] |
| HTTPS sem decriptação | [...] | [...] |
| HTTPS com decriptação | [...] | [...] |

**Resposta curta:** por que a decriptação HTTPS pelo Fiddler exige instalar um certificado raiz?

[resposta]

---

## Atividade 7 — Cookies e sessão

### Captura

<!-- arraste a captura aqui: sequência cookies/set e cookies -->

| # | URL | `Set-Cookie` recebido | `Cookie` enviado |
|---|---|---|---|
| 1 | `/cookies/set?...` | [...] | [...] |
| 2 | `/cookies` | [...] | [...] |
| 3 | `/cookies` após recarregar | [...] | [...] |

**Resposta curta:** `Set-Cookie` apareceu em toda requisição ou apenas quando o servidor definiu/atualizou cookies? Quais atributos foram observados?

[resposta]

---

## Atividade 8 — Manipulação simples com breakpoint *(Opcional)*

### Captura

<!-- arraste a captura aqui: breakpoint com User-Agent editado -->

**JSON de resposta:**

```json
{
  "user-agent": ["[valor observado]"]
}
```

**Resposta curta:** o que este teste mostra sobre o papel ativo de um proxy?

[resposta]

- [ ] Breakpoints desabilitados ao final

---

## Reflexão final (opcional)

[até 10 linhas]

---

## Encerramento — Higiene de segurança

### Captura antes da remoção

<!-- arraste aqui a captura do certmgr.msc mostrando DO_NOT_TRUST_FiddlerRoot presente -->

### Captura depois da remoção

<!-- arraste aqui a captura mostrando o certificado ausente -->

- [ ] `Decrypt HTTPS traffic` desabilitado no Fiddler
- [ ] Certificado `DO_NOT_TRUST_FiddlerRoot` removido do Windows
- [ ] Certificado `DO_NOT_TRUST_FiddlerRoot` removido do Firefox, se aplicável
- [ ] Fiddler fechado

**Por que esta etapa é importante?**

[resposta curta]

---

## Checklist de entrega

- [ ] Campos `[...]` substituídos
- [ ] Capturas inseridas
- [ ] Atividades 1 a 7 preenchidas; Atividade 8 preenchida se executada
- [ ] Encerramento com duas capturas concluído
- [ ] PDF gerado como `SOBRENOME_NOME_RA_LAB_HTTP_FLUXOA.pdf`
- [ ] PDF submetido no Microsoft Teams
