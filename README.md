# Thiago no Bar

App web simples para controlar consumo e gasto no bar. Um único `index.html` (HTML + CSS + JS puro), sem back-end. Os dados ficam no `localStorage` do navegador.

## Funcionalidades
- Ciclo de bebidas: long neck → água com gás e limão → cerveja zero → água (cigarro fora do ciclo)
- Preço editável por item, total em R$ com taxa de serviço de 10% opcional
- Encerrar noite salva no histórico; aba Histórico com gráficos e indicadores
- Exportar/Importar JSON para backup (valores em centavos)
- Exportar grava o arquivo em `historico/` e atualiza `historico/manifest.json`

## Pasta historico

Cada exportação gera `historico/rodada-historico-AAAA-MM-DD-HHMMSS.json` (preços e noites, valores em centavos) e inclui o nome em `historico/manifest.json`.

No Chrome ou no Edge, **Exportar JSON** pede a pasta `historico` do projeto na primeira vez e, nas seguintes, grava direto nela. Se o navegador não deixar escolher pasta, o arquivo é baixado: mova para `historico/` e acrescente o nome na lista `files` do manifesto. Sem isso, o site publicado não encontra o arquivo.

Ao abrir a página, o app lê o manifesto e incorpora as noites que ainda não estão neste navegador. A pasta entra no Git junto com o resto do projeto.

## Publicar
Settings → Pages → Deploy from a branch → `main` / `(root)`.
