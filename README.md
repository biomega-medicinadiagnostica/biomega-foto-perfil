# Gerador de Foto de Perfil Corporativa — Biomega

Este repositório publica uma página estática pelo GitHub Pages para montar uma foto de perfil corporativa. A interface mantém a prévia, os controles de zoom e posição, o diálogo “Como usar?”, a composição com a identidade visual Biomega e o download em PNG.

## Estrutura

- `index.html` — página principal. Inclui a última tentativa de correção da remoção de fundo (biblioteca e arquivos de modelo alinhados à versão 1.7.0, execução em CPU e indicação de progresso).
- `assets/fundo-branco-logo.png` — camada branca com marca d’água/logotipo.
- `assets/moldura-azul-bordo.png` — sobreposição azul e aro bordô usada pelo `index.html`.
- `assets/moldura-original.png` — arquivo original da moldura, mantido para referência.
- `assets/moldura-base.png` e `assets/moldura-frente.png` — arquivos de camadas de moldura das versões anteriores, mantidos no pacote por referência; a página atual não os utiliza.

## Publicar em um repositório novo

1. Crie um repositório público no GitHub, por exemplo `gerador-fotos-biomega`.
2. Extraia este ZIP no computador.
3. Envie o conteúdo desta pasta para a raiz do repositório. A estrutura deve ficar exatamente assim:

   ```
   index.html
   README.md
   assets/
     fundo-branco-logo.png
     moldura-azul-bordo.png
     moldura-original.png
     moldura-base.png
     moldura-frente.png
   ```

4. Faça o commit dos arquivos na branch `main`.
5. No GitHub, abra **Settings → Pages**.
6. Em **Build and deployment**, escolha **Deploy from a branch**, branch `main` e pasta `/(root)`, e salve.
7. Aguarde o deploy indicado pelo GitHub Pages e abra o endereço publicado.

## Como usar

1. Selecione uma foto individual, nítida, de frente e bem iluminada.
2. Ajuste zoom e posição.
3. Clique em **Remover fundo** e aguarde.
4. Quando a remoção concluir, clique em **Baixar PNG**.

Na primeira utilização, o navegador baixa a biblioteca e os modelos necessários, o que pode levar alguns minutos. As fotografias são processadas no navegador pela página e não são enviadas intencionalmente a um servidor por este código; os recursos da biblioteca/modelo são baixados de terceiros.

## Diagnóstico da remoção de fundo

A versão incluída é a última tentativa preparada após o erro `can't access property Symbol.iterator, g.shape is undefined`. Ela alinha a importação da biblioteca e o `publicPath` para a versão `1.7.0`, usa o arquivo fotográfico original como entrada e mostra progresso no status/console.

**Limitação importante:** o processamento não pôde ser executado no navegador/rede do usuário a partir deste ambiente. Portanto, esta estrutura não deve ser considerada como confirmação de que o erro foi definitivamente resolvido. Se o erro persistir, verifique no navegador (F12 → Console e Network) se há falhas ao baixar scripts, WASM ou arquivos do modelo; não altere os elementos visuais da página durante esse diagnóstico.

## Licença e uso corporativo

A página usa `@imgly/background-removal`, uma dependência de terceiros. Antes de disponibilizar o serviço publicamente ou utilizá-lo em ambiente corporativo, revise a licença e os termos atuais da biblioteca e de seus arquivos de modelo. A publicação pública do repositório também torna o código e os arquivos gráficos públicos.

## Ajuda

Contato do setor de Marketing: **marketing@biomega.com.br**.
