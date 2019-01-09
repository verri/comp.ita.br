# Divisão de Computação - ITA
Por questão de segurança, utilizamos um site estático para a divisão de computação. [Jekyll](https://jekyllrb.com) é utilizado para compilar o conteúdo do site de forma estática e dentre seus templates, [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) foi escolhido por ser o mais utilizado e com vários recursos já prontos.

Para informações sobre, veja:
- Jekyll - https://jekyllrb.com/docs/
- Minimal Mistakes - https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/

Este repositório contêm o conteúdo do site em Jekyll, conforme especificado na [documentação](https://jekyllrb.com/docs/structure/), onde as principais pastas são:
 - `_site` - Resultado da compilação do site
 - `_data` - Dados a serem utilizados nas páginas
 - `_posts` - Posts de blogs, notícias da divisão
 - `_drafts` - Posts ignorados durante compilação, não estará em `_site`
 - `third_party/minimal-mistakes` - Submódulo com template do site baseado no Minimal Mistakes em Jekyll

**Observação**: Como o template é incluído como submódulo na pasta `third_party/minimal-mistakes`, alterações no template devem ser realizados diretamente em seu repositório particular em [https://github.com/verri/minimal-mistakes](https://github.com/verri/minimal-mistakes). Veja como trabalhar com submódulos na seção [Comandos GIT](#comandos-git).



## Instalação
Veja [INSTALACAO.md](INSTALACAO.md) para instalação do Jekyll e repositório.



## Workflow
Alterações devem ser feitas em seu branch específico. Para alterar para seu branch, utilize o comando checkout.
Exemplo: as linhas abaixo alteram os branches do repositório de conteúdo do site e do submódulo.

```bash
git checkout vitor
cd third_party/minimal-mistakes && git checkout vitor
```

Após os testes e commit de suas alterações em seu branch, informe para que possamos fazer o merge no *master*.
*Nota*: Para os leigos em GIT (como eu :smile:), tenha em mãos um bom [tutorial curto](http://rogerdudler.github.io/git-guide/index.pt_BR.html).

Para servir a página localmente ([http://localhost:4000](http://localhost:4000)) execute `jekyll serve` via bundle: `bundle exec jekyll serve -wil` (veja [Quickstart](https://jekyllrb.com/docs/)). Para outros comandos, veja [Command Line Usage](https://jekyllrb.com/docs/usage/).



## Páginas e Posts
As páginas em Jekyll podem ser escritas em HTML ou Markdown, com exceção das páginas que utilizarem paginação, onde a extensão *html* é obrigatória. Veja a nota [Pagination only works within HTML files](https://jekyllrb.com/docs/pagination/).

**Encoding**: Ao editar as páginas, verifique se a formatação é UFT8 sem BOM. Não salve com BOM, caso contrário poderá corromper a compilação. Veja [Encoding no Windows](https://jekyllrb.com/docs/installation/windows/#encoding) e a nota [UTF-8 Character Encoding Warning](https://jekyllrb.com/docs/front-matter/).

Os conteúdos do site são preferencialmente escritos em Markdown por simplicidade, e vale ressaltar que tags HTML também são aceitas em Markdown. Veja os links: [Páginas](https://jekyllrb.com/docs/pages/), [Posts](https://jekyllrb.com/docs/posts/) e [Markdown](https://daringfireball.net/projects/markdown/) para entender melhor como escrever as páginas. A versão [kramdown](https://kramdown.gettalong.org/syntax.html), um superset de Markdown, é suportada por Minimal Mistakes.

Ferramentas online auxiliam na formatação em Markdown, mas podem sofrer variações de suporte a recursos. Abaixo segue uma lista de ferramentas interessantes:
- https://stackedit.io
- https://dillinger.io
- https://pandao.github.io/editor.md/en.html

Geralmente, todas as páginas possuem um *Front Matter*, um header logo no início do arquivo iniciando com  três '-'. Este header é utilizado para escolher o template de página, incluir arquivos e definir variáveis. Veja [Front Matter](https://jekyllrb.com/docs/front-matter/).
