# [PT-BR] Versão Brasileira (FRLG)

## Créditos

| Responsabilidade | Autor |
|---|---|
| **Tradução (a legenda)** | **BRENO** |
| **Criação do mod para o G1R** | **LordSangreal** |
| **Revisão** | **LordSangreal** e **Solid One** |

Tradução para português do Brasil dos **diálogos** de *Pokémon FireRed* e
*Pokémon LeafGreen*, no formato de **mod para o gen1recomp** (fork
`bryanthaboi/gen1recomp`, suporte a Gen 3 em beta).

Não é patch de ROM: o mod conversa com o motor pelo registro `text` e
sobrescreve as falas em tempo de execução. A ROM permanece intocada.

## O que está traduzido

| Catálogo | Entradas | O que é |
|---|---:|---|
| `lang/dialogue.lua` | 41 | chaves **nomeadas** do motor — o motor usa o mesmo identificador nas duas versões, então valem para FireRed **e** LeafGreen |
| `lang/dialogue_firered.lua` | 3541 | falas próprias da ROM de FireRed |
| `lang/dialogue_leafgreen.lua` | 3400 | falas próprias da ROM de LeafGreen |

`main.lua` detecta a versão em execução (`GameVersion.get()`) e aplica o
catálogo comum mais o específico daquela ROM.

**192 diálogos de LeafGreen ficaram em inglês de propósito:** neles o texto da
ROM de LeafGreen é realmente diferente do de FireRed, e aplicar a tradução de
FireRed mostraria a frase errada na tela.

## O que **não** está traduzido

Nomes de golpes, itens, Pokémon, cidades, menus e textos próprios do motor
continuam em inglês. Esta versão cobre apenas o que havia traduzido na fonte.

## Acentos

O motor renderiza os acentos portugueses por duas tabelas — `TextIR.CHARMAP`
(decode) e `FrlgFont.LATIN_GLYPHS` (render). A união cobre `é ê á ç í ó É Á Í ô
à ú Ó Ç Ê â Â Ú Ô À º ª ♂ ♀ Ë Ì`, então esses caracteres aparecem como no dump
de origem.

O **tilde** não existe em nenhuma das duas: `ã`, `Ã`, `õ`, `Õ` caem no fallback
`0x00` e a letra sai **em branco**. Deixar produziria `n o` no lugar de `não` e
`POK M N` no lugar de `POKéMON`, então foram degradados para `a`/`A`/`o`/`O`.
Quando alguém adicionar os glifos de tilde ao motor, é reverter quatro
substituições.

## Instalação

Pelo próprio gen1recomp: adicione o índice `LordSangreal/gen3-ptbr-firered-leafgreen-index`
em Configurações → Mods → Índices, e instale por lá. Assim recebe atualizações
automáticas.

Ou manualmente, colocando a pasta em:

```
%APPDATA%\pokemon-love2d\mods\firered-legenda-ptbr\
```

## Estado

Validado: sintaxe Lua, aridade de placeholder (0 divergências), escapes, e todo
caractere conferido contra o conjunto de glifos do motor. Os 3400 offsets de
LeafGreen foram verificados **por conteúdo** — decodificando a ROM em cada
offset e confirmando que o texto é o esperado, não apenas que o endereço
existe.

A confirmação visual em tela depende de abrir o jogo.

## Licença e ROM

O repositório **não contém ROM nem dado da Nintendo**. A tradução é trabalho
autoral derivado; para usar é necessário uma ROM obtida legalmente. O texto em
inglês das tabelas é citação do jogo para fins de tradução.
