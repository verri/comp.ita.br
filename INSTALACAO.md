# Instalação
Duas etapas são necessárias:
- Clonar o repositório
- Instalar o Jekyll para compilar e servir a página para desenvolvimento local



## Download do Repositório
Clonar o repositório:
```bash
mkdir workspace && cd workspace
git clone git@bitbucket.org:fverri/comp.ita.br.git
cd comp.ita.br.git
```

Carregue os submódulos do repositórios:
```bash
# inicializa os submódulos e baixa seus arquivos
git submodule update --init
```

Para atualizar o submódulo via comandos GIT, acesse sua pasta; no caso: `third_party/minimal-mistakes`. Para os leigos em GIT (como eu :smile:), tenha em mãos um bom [tutorial curto](http://rogerdudler.github.io/git-guide/index.pt_BR.html).



## Instalação do Jekyll
Utilize uma distribuição linux para instalação do Jekyll: [Jekyll on Linux](https://jekyllrb.com/docs/installation/other-linux/) ou [Jekyll on Ubuntu](https://jekyllrb.com/docs/installation/ubuntu/). Em Windows, utilize o [WSL](https://docs.microsoft.com/en-us/windows/wsl/about) disponível para Windows 10 Pro. Uma alternativa à instalação é o uso da imagem Docker [jekyll/build](https://hub.docker.com/r/jekyll/builder/).

Após a instalação, execute o comando `bundle update` dentro da pasta de repositório para atualizar os Ruby Gems.
Para servir as páginas, execute `jekyll serve` via bundle: `bundle exec jekyll serve`.

### Sabor Windows
Instale a versão [Ubuntu do WSL](https://www.microsoft.com/store/p/ubuntu/9nblggh4msv6) e siga as [instruções de instalação para Ubuntu](#ubuntu).

**Nota**: Não utilize as instruções de instalação do Jekyll em [Jekyll on Windows](https://jekyllrb.com/docs/installation/windows/#installation-via-bash-on-windows-10).

### Sabor Ubuntu
Basta seguir as instruções em [Jekyll on Ubuntu](https://jekyllrb.com/docs/installation/ubuntu/) com seu usuário. Em algumas instalações, ocorerrá um erro (*não me lembro agora o nome*) indicando a falta de um pacote. Basta pegar o nome do pacote e instalar via `apt-get install`.

### Sabor Alpine
Utilize os comandos:
```bash
sudo apk update
sudo apk add build-base ruby-dev ruby-full

echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME=$HOME/gems' >> ~/.bashrc
echo 'export PATH=$HOME/gems/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
gem install jekyll bundler
```

### Sabor Docker
Exemplo de execução, a partir de uma pasta de trabalho: `docker run -it --rm -v %cd%:/srv/jekyll --name jekyll -p 4000:4000 jekyll/builder bash`