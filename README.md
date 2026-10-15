# Índice de TESTE — mods gen1recomp

Índice **de teste**, não é o oficial. Serve para validar a instalação e a
atualização automática pelo gerenciador de mods do gen1recomp antes de publicar
no índice real (`LordSangreal/gen1recomp-mod-index`).

## Usar no app

No gen1recomp: **Configurações → Mods → Índices → adicionar**

```
LordSangreal/gen1recomp-indice-teste
```

O app busca `https://lordsangreal.github.io/gen1recomp-indice-teste/data/index.json`.

## Remover depois do teste

Apague a mesma linha da lista de índices. Nada mais muda.

## Como o app lê

`ModIndex.resolveSource` deriva três endereços de um `owner/repo`:

| Uso | URL |
|---|---|
| feed | `https://lordsangreal.github.io/gen1recomp-indice-teste/data/index.json` |
| base | `https://lordsangreal.github.io/gen1recomp-indice-teste/` |
| fallback | `https://raw.githubusercontent.com/LordSangreal/gen1recomp-indice-teste/main/site/data/index.json` |

O fallback só é consultado se o fetch do feed falhar — o GitHub Pages atrasa
algum minutos depois de um push, e ele cobre essa janela.

## Atualizar o feed

Edite `data/index.json`, espelhe em `site/data/index.json`, e faça push.

Para o app oferecer instalar/atualizar, o mod precisa de um **release com um
`.zip`** no repositório dele — o índice em si não carrega o binário.

## Quando estiver validado

A entrada pronta e já validada contra o schema oficial está em
`LordSangreal/gen1recomp-mod-index` → `mods/LordSangreal@firered-legenda-ptbr/`
(mesmo `meta.json` e `description.md` daqui). É só commitar lá quando quiser
publicar de verdade.
