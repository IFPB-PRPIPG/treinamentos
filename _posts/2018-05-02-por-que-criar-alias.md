---
layout: post
comments: true
title: "Por que criar alias?"
date: 2018-05-02 17:59:22
image: '/assets/img/'
gif: '/assets/gif/'
description: 'Você já parou para pensar na sua rotina ao chegar no ambiente de trabalho após ligar a máquina? Quais comandos sempre usa? Quais sistemas sempre abre?'
main-class: 'misc'
tags:
- linux
- dicas
categories:
twitter_text:
introduction: 'Crie os seus próprios atalhos para preparar o seu ambiente de trabalho e tenha a perfeita desculpa para encher o seu café enquanto a máquina os executa.'
author_email: 'pedro.vinicius@academico.ifpb.edu.br'
author: 'Pedro Paiva'
author_img: 'pedro.png'
github_username: 'VSPPedro'
---

# Mapeando a rotina

Caso ainda não tenha feito isso antes, eu sugiro que você analize a sua rotina no trabalho. O motivo? Perceber o que pode ser automatizado.
Talvez o seu "mapa" fique parecido como:
- Abre o terminal ou IDE
  - Levanta o ambiente
  - Executa o projeto
- Abre o slack
- Abre um browser para email/stack overflow/Trello
  - Vê as atividades/lembra onde parou
- Abre o Spotify ou Youtube
- Pega café/água
- Mãos à obra!

![imagem_coding_time][coding_time_meme]

Essa era a minha. Eu sei! Devia pegar o café/água antes de ir para a máquina, mas nem sempre lembro disso. E em minha defesa dizem que caminhar ajuda a pensar melhor.

**Próximo passo:**

![programador_na_bicicleta_gif](https://media1.tenor.com/images/7582f8bd7e7af8a03308a0f1492145bf/tenor.gif?itemid=7990692)

~~Mentira, cansei só de olhar.~~

# E a resposta do título?

Boa pergunta! ~~Tinha esquecido...~~

Uma das formas de aumentar a produtividade é evitando o uso do mouse e é aí que entra o *alias*, pois com ele podemos simplificar comandos, poupando tempo na digitação, e até fazer com que um mero comando dispare muitos outros.

**Exemplo de comando:**

``` bash
$ startdev <django_project>
```

**Resultado:**

- Abre um browser
- Abre Spotify
- Abre Slack
- Abre Editor de Texto ou IDE do projeto que estamos trabalhando
  - Prepara o ambiente
  - Executa um git pull atualizando o código do projeto

**DICA1**: É melhor deixar o git pull por último, pois em caso de conflito ele não vai quebrar a cadeia de comandos.

**Mas além de alias existe outras formas de evitar o uso do mouse?**

Claro! Exemplos:

- Aprendendo os atalhos existentes da ferramenta que usamos durante o desenvolvimento.
- Aprimorando a ferramenta para a framework que usamos. (Adicionando plugins de Django/Python no Atom, por exemplo.)


# Mãos à obra

![jim_carrey_digitando_gif](https://media1.tenor.com/images/505ddb5e0b0e8c3e96b66e1469ef47c1/tenor.gif?itemid=4903969)

## Preparando ambiente

Por motivos de organização vamos criar uma pasta na home chamada de **aliases**(plural de alias). Local onde ela vai ficar:

``` bash
$ pwd
/home/$USER/aliases
```

Dentro dessa pasta vamos criar um arquivo executável chamado de **aliasesmanager.sh**.

**OBS1:** Toda vez que criarmos um arquivo executável precisamos inserir na primeira linha: **#!/bin/bash**. Esse comando serve para identificar o interpretador que será utilizado na execução dos comandos.

**OBS2:** Outro detalhe importante é dar ao arquivo a permissão de execução:
``` bash
$ chmod +x aliasesmanager.sh
```

**O que esse aliasmanager.sh vai fazer?**

Ele vai ter a lista de todos os alias que vamos criar. Fique vendo!

### Criando alias

No arquivo **aliasesmanager.sh** vamos adicionar alguns atalhos para comandos um pouco longos que usamos em um projeto Django e Jekyll(caso queira você pode fazer sobre outra framework/linguagem):

``` bash
#!/bin/bash
alias cddjango='/home/$USER/<django_project_dir>'
alias startenv='source <ambiente>/bin/activate'
alias startdjango='python manage.py runserver 0.0.0.0:8000'
alias startjekyll='jekyll server --watch'
```

**Opcional:** Tente lembrar de comandos um pouco extenso que você costuma usar durante o desenvolvimento e adicione no arquivo.

Agora precisamos executar o arquivo para que esses aliases fiquem acessíveis no terminal:
``` bash
$ source aliasesmanager.sh
```  

## Executou sem erro? Hora de testar!

O que achou?

- **Não dava para juntar esses três comandos do Django em um só não?**
- **E como que eu faço para que o arquivo aliasesmanager.sh seja executado quando minha máquina iniciar?**
- **Meu alias está tomando controle do terminal, não quero isso!**
- **E a desculpa para o café, cadê? Cadê? Cadê?**

![jim_carrey_frustrado_gif](https://media.tenor.com/images/09c075a32556feeb23c5943c3b5bd496/tenor.gif)

Ei, calma lá! Eu vou responder! O problema é que esse post ficou um pouco longo ~~e eu não vou abrir mão dos memes/gifs~~. Solução? Dividir em dois!

<Inserir Link Parte 2 Aqui Em Um Futuro Próximo>


<!-- links -->
[coding_time_meme]:/assets/img/posts/hour_of_code.jpg
[bike]:https://media1.tenor.com/images/7582f8bd7e7af8a03308a0f1492145bf/tenor.gif?itemid=7990692
