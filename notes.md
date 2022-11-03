# Manual nativo de utilização do VIM:

`man vim`

# Modos do Vim

> `esc` - volta ao modo de comando
> `:` - prescreve o comando

- `i` - Modo de inserção
- `v` - Modo visual
- `/` - Modo busca
- `R` - Modo reposição (sobrescrever)

# Comandos de terminal

- 1 - `vim --help`: exibe compandos úteis para o vim
- 2 - `vim <namefile.ext>`: cria ou abre um arquivo - `vim <namefile.ext> +`: abre o arquivo na última linha - `vim <namefile.ext> +n`: abre o arquivo na linha n - `vim <namefile.ext> +/ABC`: abre o arquivo na primeira ocorrência da palavra ABC
- 3 - `vim -o <namefile1.ext> <namefile2.ext>`: abre os arquivos em uma tela em colunas diferentes [para trocar de arquivo usa-se Ctrl+w+w]
- 4 - `vimtutor` - pequeno tutorial do vim
- 5 - `vimdiff` - mostra a diferença entre dois ou mais arquivos

# Salvar e sair

- `:w` - salva o arquivo
- `:q` - sai do arquivo
- `:wa` - salva todos os arquivos
- `:qa` - sai de todos os arquivos
- `:wq`, `:x`, `ZZ` - salva e sai do arquivo
- `:wqa` - salva e sai de todos os arquivos
- `:q!` - sai do arquivo mesmo sem salvar
- [*deprecado, usa-se apenas no VI*]`:set autowrite`, `:set aw` - salva a cada alteração efetuada
- `:split <dir>/<filename.txt>` - abre o arquivo filename no vim no modo linha
  - `vsplit <dir>/filename.txt` - abre o arquivo no modo coluna

# Modo de inserção

- `i` - insere ao digitar a partir de onde o cursor está
- `a` - começa a digitar após a posição do cursor
- `o` - começa a digitar na linha abaixo do cursor

## Manipulação de texto

- `v` - marca o cursor e possibilita selecionar usando as setas ou hjlk
- `[shift]+v` - seleciona todo o parágrafo
- `y` - copia o texto selecionado, ou linha até o cursor atual. se posicionar o cursor após a palavra, pegará o espaço também.
- `p` - cola a palavra ou linha copiada
- `d` - recorta o texto selecionado, ou linha.
- `x` - deleta o texto selecionado, ou a linha

- `yy` - copia toda a linha
- `8yy` - copia 8 linhas abaixo contando com a atual do cursor

- `dd` - deleta a linha atual
- `u` - desfaz a última ação

- `ggVG` - seleciona tudo

- `u` - troca a parte selecionada por minúsculas
- `U` - troca a parte selecionada por MAIÚSCULAS

### Comentar múltiplas linhas

- 1 - Vá para o início da linha a partir de qual será comentada
- 2 - Entre no modo de seleção vertical, usando `Ctrl + V`
- 3 - Selecione as linhas com o cursor ou use uma movimentação no modo normal (7j para andar para 7 linhas acima)
- 4 - Pressione `[SHIFT] + i` para entrar no modo de inserção múltipla
- 5 - Insira o caractere necessário para comentar (em `JS`, seria o `//`)

### Auto indentação

Selecione todo o texto necessário e aperte `==` ou `gg=G` para auto indentar o texto

## Movimentando no texto

[*NO MODO DE COMANDO = ESC*]

- `l` - vai para a direita
- `k` - vai para a cima
- `j` - vai para a baixo
- `h` - vai para a esquerda

- `w` - vai para a próxima palavra
- `b` - vai para a palavra anterior
- `)` - pula para a próxima frase
- `(` - volta para a última frase
- `}` - vai para o próximo parágrafo
- `{` - volta o último parágrafo

- `$` - vai para o fim da linha
- `ˆ` - vai para o início da linha

- `:$`, `G` - vai para o fim do arquivo
- `gg` - vai para o início do arquivo

# Modo busca

- `/word` - busca a palavra "word" no texto e deixa todas em destaque
- `n` - vai para a próxima incidência da palavra "word"
- `:% s/nada/NINGUEM` - troca a primeira palavra nada por NINGUEM
  - `:% s/nada/NINGUEM/g` - troca todas as palavras nada por NINGUEM
  - `:% s/nada/NINGUEM/gc` - pergunta em cada palavra nada se o usuário deseja trocar por ninguém.

# Personalizando

- `:set nu!` - mostra o número das linhas
- `:map <key> <action>` - mapeia um compando para uma tecla personalizada
  - exemplo: `:map <F12> ggVG`=> agora a tecla F12 seleciona todo o texto.
- `:set textwidth=80` - limita a digitação a 80 colunas

# VimScript (VimL)

Para criar VimScripts, editamos o arquivo de config do vim (ou criamos um, caso não exista no sistema):
- No mac e linux: `~/.vimrc`
- No windows: `~/_vimrc`

Toda vez que um arquivo for aberto com o vim, o VimScript aplicará as configurações salvas no vimrc.

Para identificar o `vimrc` no OS, basta usar o comando: `:echo $MYVIMRC` no VI, Vim ou NVim 

No NeoVim o caminho é: `~/.config/nvim`
