# Capas esticadas e com cantos arredondados no KOReader

User patch do KOReader que deixa todas as capas da **grade de capas (mosaico)** na mesma proporção (2:3) e com **cantos arredondados**. Este repositório traz o patch pronto para usar junto com os **ícones dos cantos**, que ele precisa e que não vêm no KOReader.

## ✅ Aparelhos testados

| Aparelho | Firmware | KOReader | Resultado |
|---|---|---|---|
| **Kindle Colorsoft Signature Edition** | 5.20.1 | v2026.07.2 | ✅ Capas com cantos arredondados na pasta de livros (mosaico 3×2), junto com o plugin SimpleUI |

*Teste feito em novembro de 2026.*

## Crédito

O patch `2--stretched-rounded-covers.lua` é de **[SeriousHornet](https://github.com/SeriousHornet/KOReader.patches)** e está aqui **sem alterações**, sob a mesma licença (GPL-3.0). Os ícones `rounded.corner.*.svg` deste repositório foram feitos do zero: são máscaras brancas simples, com um raio de canto que fica visível na tela de alta resolução do Colorsoft.

## Instalação

1. Copie `patches/2--stretched-rounded-covers.lua` para a pasta `koreader/patches/` do aparelho (crie a pasta se ela não existir).
2. Copie os quatro arquivos de `icons/` para a pasta `koreader/icons/` (crie a pasta se ela não existir).
3. Reinicie o KOReader (**Menu → Sair → Reiniciar KOReader**).
4. Abra a pasta de livros na visualização em **mosaico**.

No Kindle, o caminho é `/mnt/us/koreader/`. No Android, normalmente `/sdcard/koreader/`.

## O que esperar

- **Onde funciona:** só na grade de capas do navegador de arquivos (e nas listas de histórico e coleções em mosaico). A tela inicial do plugin SimpleUI não muda.
- **Capas esticadas:** capas que já estão em 2:3 ficam iguais; as de outros formatos são esticadas até a proporção 2:3 (no máximo 50% além do tamanho original).
- **Faixa "Novo":** nos livros ainda não abertos, a faixa "Novo" cobre o canto superior direito.
- **Modo noturno:** os cantos são brancos e acompanham a inversão de cores do modo noturno.

## Ajustes

- **Proporção e esticamento:** no começo do patch, mude `aspect_ratio` (padrão `2 / 3`), `stretch_limit` (padrão `50`) ou `Fill` (`true` faz a capa ocupar a célula inteira).
- **Tamanho do arredondamento:** nos quatro SVGs, o número `45` em `H45 A45 45 0 0 0 0 45` é o raio, numa escala de 0 a 100. Aumente para cantos mais redondos ou diminua para cantos mais discretos, mudando o mesmo número nos quatro arquivos.

## Desinstalar

Apague `koreader/patches/2--stretched-rounded-covers.lua` e os arquivos `koreader/icons/rounded.corner.*.svg`, e reinicie o KOReader.

## English summary

KOReader user patch that stretches mosaic (cover grid) covers to a uniform 2:3 aspect ratio and adds rounded corners. The patch is by [SeriousHornet](https://github.com/SeriousHornet/KOReader.patches), included unchanged under GPL-3.0; the corner icons here are new, simple white masks sized to be visible on high-resolution screens. Copy `patches/2--stretched-rounded-covers.lua` to `koreader/patches/` and `icons/*.svg` to `koreader/icons/`, then restart KOReader. Tested on a Kindle Colorsoft Signature Edition (FW 5.20.1, KOReader v2026.07.2).
