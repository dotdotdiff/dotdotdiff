+++
title = "Scoop e Winget - Gerenciando programas no Windows"
date = 2025-01-15
updated = 2025-01-15
description = "Hoje vamos conhecer o Scoop e Winget, gerenciadores de pacote que facilitam nossa vida ao instalar programas no windows"

[taxonomies]
tags = ["scoop", "windows","winget"]

[extra]
+++
# O que são gerenciadores de pacotes?
Em resumo, gerenciadores de pacotes são centrais de programas que você pode baixar com alguns comandos.

No windows ainda é algo um tanto incomum, já que por muitas vezes quando queremos instalar algum programa nós vamos no site oficial de determinado programa, baixamos o instalador dele e depois clicamos next até o final da jornada.

Para facilitar na instalação e evitar baixar programas errados, podemos utilizar um repositório oficial que centraliza esses programas já filtrados e esse seria o papel principal do gerenciador de pacotes.

Outra coisa também é o gerenciamento de dependências e atualizações de maneira mais fácil. Basta somente um comandinho e pimba, atualizamos tudo sem esquentarmos nossa cabeça.

# Winget - O instalador de pacotes oficial da Microsoft

Esse daqui já vem pré instalado no windows então qualquer um pode utilizar a partir de já.

se por exemplo, você abrir seu terminal, prompt de comando e digitar:

```sh
winget install firefox
```
você vai instalar o navegador firefox na última versão e já vai pode utilizar normalmente depois da instalação.

para atualizar algum programa instalado basta fazer:

```sh
winget upgrade nome_do_pacote
winget upgrade firefox //no nosso caso
```

e caso não queira ir atualizando 1 por 1 basta digitar isso aqui:

```sh
winget upgrade --all
```

com isso todos os seus pacotes já vão ser atualizados bonitinho sem nenhuma dor de cabeça.

E como eu sei se o programa que quero já existe no repositório do windows?

Você pode dar um winget install e o nome do programa que você busca que ele já vai dizer se existe ou não ou também pode simplesmente acessar esse site aqui o [Winstall](https://winstall.app/)  onde você vai ver de maneira bonitinha todos os pacotes e consegue até mesmo configurar um script pra instalar todos os apps que quer ao mesmo tempo.

# Scoop - O instalador de coisas avançadas no Windows

Apesar de não ser o gerenciador oficial da microsoft, o Scoop vem pra ser uma mão na roda para quem gosta de projetos Open Source no windows, já que hoje é por lá que muitos devs publicam seus apps, por ter uma política menos rigorosa para entrar.

Sendo assim, instalaremos ele aqui para poder seguir tutoriais mais frente com coisas mais avançadas kkkk.

Você por ir no site oficial do [Scoop](https://scoop.sh/#/) ou rodar esse comando no seu powershell, aqui precisa ser o powershell mesmo e não o prompt de comando.

```sh
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```

Após a instalação vamos instalar nosso primeiro programinha para teste

```sh
scoop bucket add main
scoop install main/7zip
```
Você deve tá notando que temos que adicionar esse bucket primeiro, que seria algo como uma ¨categoria" de programas, é um repositório dentro de um repositório.

Em outras palavras, adicionando o main, podemos instalar os aplicativos do main, que é onde o 7zip está, existem buckets oficiais e alguns mantidos apenas pela comunidade.

Vou deixar aqui os principais que utilizaremos em outros tutoriais.

```sh
scoop bucket add main
scoop bucket add extras
```
Com esses dois estaremos bem servidos.

Viu como é fácil utilizar e instalar esses gerenciadores de pacote.

# E o Chocolatey Diff?
Para pessoas mais antigas devem estar pensando no Choco, que também é um gerenciador de pacote do windows, mas ele vem sendo deixado de lado a favor do Scoop, além de sempre ter sido muito bugado.

Então prefiro nem trazer ele aqui para vocês.

# Conclusão
Com gerenciadores podemos instalar todos nossos programinhas sem nem precisar ir no navegador (caso saiba o nome né), também conseguimos atualizar todos sem problemas para evitar algum tipo de vulnerabilidade de versão.

A partir daqui sempre que possível instalaremos as coisas via winget ou scoop. Nem todos os programas ainda vamos encontrar neles, mas a maioria já tá por aqui.

Se sentirem alguma dificuldade podem deixar nos comentários e se tiverem algo a acrescentar também pode abrir uma issue lá no github com sugestões e melhorias.

Espero manter esse projeto vivo o máximo de tempo que conseguir
