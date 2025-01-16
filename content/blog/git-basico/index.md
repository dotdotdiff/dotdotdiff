+++
title = "Aprendendo o básico que você precisa de GIT"
date = 2025-01-11
updated = 2025-01-11
description = "Vamos aprender o git, uma ferramenta que é o padrão da indústria de desenvolvimento de software, mas aqui veremos que ela podemos usar ela para além do código."

[taxonomies]
tags = ["git", "tutorial"]

[extra]
+++
# O que é?

Primeiramente você deve estar se perguntando o que é git, se for da área de ti muito provavelmente já deve ter ouvido falar dessa ferramente que é padrão na indústria.

Agora para os leigos, o Git é um versionador de código (ou texto se preferir), ele é utilizado para termos controles das versões de um código que produzimos, mantendo um histórico que podemos consultar ou até mesmo voltar para algum momento no passado.

# Como instalar?

Caso utilize o windows, basta ir no site [Site oficial do git](https://git-scm.com/downloads)baixar o instalador e seguir no famoso next e next até o final.

Caso use o linux, basta instalá-lo via o gerenciador de pacotes de sua distro.

# Primeiros passos com o git

Após a instalação precisamos configurar nosso username e email em nosso git, não se preocupem agora pois podemos mudar a qualquer momento essas configurações

```bash
git config --global user.name "Meu username bonito"
git config --global user.email meuEmail@bonito.com
```
Com isso temos nosso user name e email globais já setados no git.

# Conceitos do versionamento do texto (ou código)

O git nos permite criar um fluxo de criação do nosso texto em uma árvore de mudanças, conseguindo ir empilhando mudanças horizontalmente como também verticalmente.

Em outras palavras, nós podemos dar contextos para diferentes para o nosso projeto e isso chamamos de branchs ou galhos.

# Branchs e as possibilidades
Agora para exemplificar vamos por a mão na massa, crie uma pasta (diretório) em qualquer lugar em seu sistema, após isso clique com o botão direito e abra a pasta no terminal.

com o terminal aberto digite:

```bash
git init
```
com esse comando iniciamos nosso projeto git.

Aqui nós estamos na branch inicial do nosso projeto que é a master ou main a depender do padrão do seu git.

Agora crie um arquivo txt e escreva qualquer coisa nele.

Após isso de o comando
```bash
git status
```
Ele deve exibir seu arquivo como untracked, isso significa que o git não tá "analisando" esse arquivo, para o git passar a tratar esse arquivo digite o comando

```bash
git add nome_do_seu_arquivo.txt
```
Pronto, agora seu arquivo já está adicionado ao git e ao digitar `git status` verá que agora ele mudou para stage.

Agora commitaremos nossa versão, que é basicamente fazer com que o estado atual do nosso projeto seja salvo em um commit que seria algo como um "pacote de mudanças".

```bash
git commit -a -m "meu primeiro commit"
```
A flag `-a` é para adicionar todos os arquivos para staged e a flag `-m` é para sinalizar a mensagem que queremos que vem em aspas logo em seguida.

Com isso temos nossa branch master com nosso primeiro commit salvo, mas e se quisessemos testar novas coisas sem perder o que temos?

Para isso existe a criação de branchs que vai nos ajudar com esse problema.

```bash
git branch teste
git checkout teste
```
Criamos nossa branch chamada teste e após isso nós mudamos para ela com o comando `git checkout`, onde podemos mudar a vontade sem ter o medo de que possa alterar algo na nossa branch main, que é nosso contexto principal.

Ao ir para a branch de testes, podemos alterar nosso arquivo txt e adicionar mais um novo arquivo e após isso nós commitaremos novamente.

```bash
git commit -a -m "meu commit de testes"
```
Mas ai você vai e lembra que precisa de algo que ficou no nosso contexto principal, e ai?

Agora basta darmos um `git checkout main` para que possamos voltar ao nosso contexto principal e perceba, todas as mudanças que fizemos na nossa branch teste ficaram somente lá e voltamos a ver o arquivo como estava antes de irmos para outra branch.

# Conclusão

Com isso finalizamos o básico que você precisa saber de git, eu recomendo depois dar uma pesquisada sobre o git, é algo muito útil para programadores e para pessoas que trabalham somente com texto, já que nos dá um controle enorme sobre versões e podemos voltar no histórico a vontade.

Outra coisa também, aqui fizemos tudo via terminal só que não é preciso não tá? Maioria das pessoas utiliza ferramentas com interface gráfica para mexer com o git, o que simplifica ainda mais o processo de edição e também de visualização das versões.

E por fim, fiz esse tutorialzinho básico de git somente para podermos seguir com os tutoriais que postarei mais a frente aqui e o git é pré-requisito de boa parte deles.

Caso tenha sugestões de melhorias ou queira fazer algum complemento estarei deixando o link do github com o markdown do site onde poderá fazer PRs com melhorias ou também comentar abaixo suas sugestões.
