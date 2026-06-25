# Ls-Optimizer-Assets

Ícones (PNG) dos jogos usados pelo **Game Mode** do **LS Optimizer**, hospedados
de graça em um repositório público do GitHub e servidos pelo CDN do **jsDelivr**.

## 📐 Convenção de nomes (IMPORTANTE)

O backend do app **deriva a URL do ícone a partir do `id` do jogo**, então o nome
do arquivo precisa bater exatamente com o `id`:

```
nome do arquivo = {id do jogo, em minúsculo, sem espaço} + .png
```

- ✅ `valorant.png`, `cs2.png`, `gta5.png`, `rocketleague.png`
- ❌ `Valorant.png`, `CS2.PNG`, `gta 5.png`, `rocket-league.png`

Se o nome não bater com o `id`, o app **não encontra o ícone** e cai no monograma
de reserva. Todos os arquivos ficam na pasta [`icons/`](icons/).

## 🔗 Padrão da URL (jsDelivr)

```
https://cdn.jsdelivr.net/gh/Luqtta/Ls-Optimizer-Assets@main/icons/{id}.png
```

Exemplo (Valorant):

```
https://cdn.jsdelivr.net/gh/Luqtta/Ls-Optimizer-Assets@main/icons/valorant.png
```

> `@main` aponta sempre para o último commit da branch `main`.

## 🖼️ Especificação das imagens

| Item            | Valor                                  |
|-----------------|----------------------------------------|
| Formato         | PNG                                    |
| Dimensões       | quadrado, **256×256** (ou 512×512)     |
| Fundo           | **transparente**                       |
| Nome do arquivo | `{id}.png` — minúsculo, sem espaço     |

## ➕ Como adicionar um ícone novo

1. Gere o PNG quadrado (256×256, fundo transparente).
2. Renomeie para o `id` do jogo em minúsculo, ex.: `apex.png`.
3. Coloque em `icons/`.
4. Commit e push:
   ```bash
   git add icons/apex.png
   git commit -m "add apex icon"
   git push
   ```
5. Em ~1 min o ícone já está disponível em:
   `https://cdn.jsdelivr.net/gh/Luqtta/Ls-Optimizer-Assets@main/icons/apex.png`

## ♻️ Cache do jsDelivr e como forçar atualização

- O jsDelivr **cacheia agressivamente** a versão de `@main` (por volta de **~7 dias**
  na borda do CDN). **Arquivo novo** aparece rápido; **arquivo trocado** (mesmo nome)
  pode continuar servindo a versão antiga até o cache expirar.
- Para forçar a atualização de um arquivo que você **substituiu**, faça o *purge*
  abrindo no navegador (ou via `curl`):
  ```
  https://purge.jsdelivr.net/gh/Luqtta/Ls-Optimizer-Assets@main/icons/valorant.png
  ```
- Alternativa sem purge: **versionar pela URL** (ex.: trocar `@main` por uma tag ou
  commit fixo como `@v1` / `@<sha>`), assim cada versão tem cache eterno e imutável.

## 🆔 IDs já existentes

`valorant`, `cs2`, `fortnite`, `warzone`, `minecraft`, `league`, `roblox`,
`gta5`, `apex`, `rocketleague`

---

Servido por [jsDelivr](https://www.jsdelivr.com/) · Repositório público mantido por
[@Luqtta](https://github.com/Luqtta).
