## Estilizando seu terminal para uma melhor visualização (Somente para sistemas em unix).

Muitas pessoas tem me perguntando como fazer para estilizar o seu terminal. Pensando nisso, fiz especialmente para vocês, um artigo com o passo-a-passo para deixar o terminal com uma visualização bem melhor.

Mas antes de começar de fato, um aviso importante: Este tutorial não irá funcionar para você que utiliza windows. Caso você queira utilizar o windows, eu aconselho experimentar o terminal hyper (hyper.is). Ele é feito com tecnologias web e irá funcionar nesse sistema.

Com isso esclarecido, vamos ao que interessa!

1 - Vamos começar baixando a fonte que iremos utilizar:

Acessando o link abaixo você irá baixar a fonte Fira Code. Essa é uma fonte muito utilizada por desenvolvedores. Ela deixa uma visualização de código muito mais agradável.

```https://github.com/tonsky/FiraCode```

Após baixar a fonte é só extraí-la, acessar o diretório do formato (eot, ttf, etc) que deseja instalar e clicar duas vezes que ela irá instalar.

ATENÇÃO: Ao acessar o link do github você precisa descer o scroll até o parte de "Solution" e lá você encontra o botão de download.

Tudo certo com a fonte? Então vamos ao segundo passo!

2 - Baixando o tema para seu terminal:

Em uma pasta a sua escolha, dê um clone no projeto.</br>
É necessário ter o git instalado. Para saber mais, clique aqui. 

```$ git clone https://github.com/dracula/terminal-app.git```

Feito isso, você precisa ir no seu terminal e acessar o Menu Terminal -> Preferências (Estou utilizando um mac, mas as “Preferências” do linux são as mesmas).</br>
Clique na engrenagem abaixo dos temas e clique em Importar.

![captura de tela 2019-03-08 as 08 52 50](https://user-images.githubusercontent.com/34281331/54033326-c35a0c80-4192-11e9-9c1c-35c4822c357f.png)

Agora, você deve ir até o diretório onde salvou o terminal e selecionar o arquivo "Dracula.terminal" e clicar em Abrir.

Depois de importar o tema, selecione-o e clique na opção "Trocar..." para mudar a fonte.

![captura de tela 2019-03-08 as 08 56 06](https://user-images.githubusercontent.com/34281331/54033498-38c5dd00-4193-11e9-97c2-d4b29c9dd1b7.png)

Na janela de fontes, procure pela fonte que você baixou (Fira Code).</br>
Nesse ponto, você poderá escolher a tipografia, tamanho da fonte entre outras definições que ficam a seu critério.</br>
Você ainda poderá configurar algumas outras opções como o modo que o curso, janela, entre outros irão se comportar. Tudo fica de acordo com o seu gosto, mas a definição padrão já é uma escolha muito boa. 

Com o tema Dracula selecionado clique em "Padrão" ao lado da engrenagem:

![captura de tela 2019-03-08 as 09 02 08](https://user-images.githubusercontent.com/34281331/54033614-89d5d100-4193-11e9-9c4a-6e5ac6c86107.png)

Depois de seguir esse passo, reinicie seu terminal.

3 - Agora iremos instalar o terminal "Oh my zsh" para deixar seu terminal bem bonitinho!
No seu terminal cole o comando abaixo:

```sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"```

Após finalizar a instalação reinicie seu terminal e você já verá a diferença.</br>
Mas ainda tem mais. Agora é hora de instalar um tema para o Oh my zsh.</br>
Vamos lá!</br>
Mais uma vez, iremos usar o git clone para fazer o download. Para isso, digite o comando abaixo na pasta onde deseja salvar:

```git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"```

Ao finalizar o comando vamos fazer um symlink. </br>
Execute o comando abaixo:

```ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"```

Agora vamos abrir o arquivo de configuração com seu editor que preferir (Vou usar o nano):

```sudo nano ~/.zshrc```

Onde está escrito ZSH_THEME mude para:

![captura de tela 2019-03-08 as 09 16 43](https://user-images.githubusercontent.com/34281331/54033637-a540dc00-4193-11e9-81d6-c0a4677d7cf7.png)

Tudo feito? Reinicie seu terminal! </br>
Agora quando você entrar em algum projeto git você verá que ele mostra qual branch você está entre outras coisas.

Voltando ao arquivo zshrc no final do arquivo cole os comandos abaixo:
```
SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg
  exec_time
  line_sep
  vi_mode
  jobs
  exit_code
  char
)

SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_CHAR_SUFFIX=" "
```
4 - Para finalizar, vamos instalar um plugin que nos dá sugestões de código, informa se você está digitando algum comando errado, entre outras coisas.

Execute o comando abaixo em seu terminal:

```sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zplugin/master/doc/install.sh)"```

Serão adicionadas as seguintes linhas no seu arquivo zshrc:

![captura de tela 2019-03-08 as 10 04 26](https://user-images.githubusercontent.com/34281331/54033623-9823ed00-4193-11e9-9757-d176a71c5256.png)

Logo abaixo dessas linhas cole os comandos abaixo (sudo nano ~/.zshrc):

```
zplugin light zsh-users/zsh-autosuggestions
zplugin light zsh-users/zsh-completions
zplugin light zdharma/fast-syntax-highlighting
```

Conseguiu fazer tudo? Então agora é só reiniciar seu terminal.</br>
Assim que ele abrir, serão instalados os plugins necessários.</br>
Feito isso, é só aproveitar! Garanto que será muito útil!
