# RL Arena

**(R)ogue(L)ike Arena** — ARPG isométrico 2.5D (estilo Diablo II) em
**um único arquivo HTML**, JS puro + canvas 2D, sem engine, sem build.

## Como jogar
Salve / baixe o `RL Arena.html` e abra direto no navegador
(Chrome/Firefox/Edge). Não precisa instalar nada, não precisa de servidor.

## Controles
| Tecla | Ação |
|---|---|
| `WASD` | mover |
| Mouse (mira) + **botão esquerdo (segurar)** | atacar |
| `ESPAÇO` | esquiva (dash) |
| `Q` | poção |
| `1` / `2` / `3` | habilidades |
| `V` | próxima wave |
| `C` | abrir estatísticas |
| `ESC` | pausar |
| `T` | alternar idioma (PT/EN) |

## Classes
- **Daggers** (corpo a corpo)
- **Mage** (mago — lança a Ball Lightning)
- **Crossbow** (arco)

## Estrutura de run
- **Waves** progressivas; a cada **3 waves** aparece um **boss**
  (`bossEvery: 3` na config).
- **Zonas** trocam conforme avança: **wave 10 → Calabouço**,
  **wave 25 → Inferno** (obstáculos e clima mudam por zona).
- No fim da run: upgrades em forma de **cards**, lojinha de atributos
  (FOR / DES / VIG), e **loot com cores de raridade** no estilo ARPG.

## Detalhes técnicos
- ~4.300 linhas num arquivo só; estado global `G`, loop com
  `requestAnimationFrame` + `dt` clampado.
- Mundo simulado em **plano 2D (1800×1800)** com **projeção isométrica
  2:1 só na renderização** — a colisão/câmera compartilham o mesmo
  espaço iso.
- Configurações de balanceamento ficam no objeto `CFG` no topo do
  arquivo (dano, drops, affixes, zonas).
- Áudio sintetizado via WebAudio (`beep`/`ac`), sem assets externos.

## Convenções deste repositório
- O arquivo "final" é sempre `RL Arena.html`. Versões antigas de
  experimento ficam fora do repo (em `Arena Roguelike/`, no disco).
- Pull/push: `git pull` / `git push` direto — credential já configurado.
