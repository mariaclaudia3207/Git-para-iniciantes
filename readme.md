<h1 align="center">Git para Iniciantes</h1> 



<p align="justify">
O Git e o Github são amplamente utilizados, sendo uma ferramenta primordial desde iniciantes a seniores na programação. Aqui você encontrará os primeiros passos e comandos para quem está começando agora, de forma clara e sem termos chatos que ninguém entende :)
</p>






## Sumário

:small_blue_diamond: [Primeiros passos](#primeiros-passos-fishing_pole_and_fish)

:small_blue_diamond: [Comandos básicos](#Comandos-básicos-balloon)

:small_blue_diamond: [Modificando arquivos (commits)](#Modificando-arquivos-(commits)-memo)

:small_blue_diamond: [Como rodar a aplicação](#como-rodar-a-aplicação-arrow_forward)

... 

Insira os tópicos do README em links para facilitar a navegação do leitor






## Primeiros passos :fishing_pole_and_fish: 

Comece instalando o Git no seu computador. Para isso acesse https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git e escolha de acordo com o seu sistema operacional (Windows, Linux, MacOS etc).

Os comandos são realizados dentro de um terminal e você pode utilizar, por exemplo, o terminal do VScode, na opção "git bash":

![image](https://user-images.githubusercontent.com/126173770/225314153-a4dc06d5-4e43-462e-9417-502f53cccd91.png)


:arrow_right: Digite o comando "mkdir" no terminal para criar uma pasta. Esta será o seu repositório, um lugar onde estarão os códigos que farão parte do seu projeto. Por exemplo:

```
$ mkdir pasta_do_projeto
```
:arrow_right: Com o comando "cd", entre na pasta e inicie o repositorio com o comando "git init":

```
$ cd pasta_do_projeto
$ git init
```
Após isso, será possível criar os arquivos e desenvolver seu projeto.







## Comandos básicos :balloon:

:small_orange_diamond:O comando "diff" serve para mostrar as últimas modificações que um arquivo sofreu:

```
$ git diff
```
:small_orange_diamond:"git status" mostra o estado atual do projeto, se há alguma alteração esperando ser aceita etc:

```
$ git status
```
:small_orange_diamond:"git show" mostra as mudanças que cada commit fez:

```
$ git show
```
:small_orange_diamond:"git log" mostra os commits feitos e informações sobre eles, enquanto o "git log --graph" mostra as informações em formato de grafo:

```
$ git log
$ git log --graph
```







## Modificando arquivos (commits) :memo:

Durante o desenvolvimento do seu projeto, ele sofrerá inúmeras modificações e digamos que cada modificação gere um registro para que você e outras pessoas que estejam contribuindo possam acompanhar a evolução. Cada modificação dentro do código é chamada de "commit". 

:arrow_right: Por exemplo, crie um arquivo README.md dentro da pasta do seu projeto e adicione algum texto dentro dele. Após isso, salve-o.
Ao adicionar um texto dentro do arquivo, você o modificou e para registrar essa modificação, digite o seguinte comando dentro da pasta do seu projeto, adicionando um comentário sobre a mudança que realizou:
```
$ git commit -am "comentário sobre a modificação"
```
:arrow_right: Utilize "git show" para visualizar as modificações:
```
$ git show
```
:arrow_right: "git log" para listar todas as commits (modificações realizadas) no projeto:
```
$ git log
$ git log --graph
```





## Retornando modificações (reset) :leftwards_arrow_with_hook:

Caso você altere algum arquivo e deseje voltar a uma versão anterior a atual, utilize o comando "git reset". Existem algumas variações desse comando, sendo as mais comuns:

:small_orange_diamond:"git reset soft", onde ele volta a modificação mas ainda existe um commit e vc pode voltar a modificar o arquivo principal:
```
$ git reset --soft hash_do_commit 
```
:small_orange_diamond:"git reset hard" apaga completamente o commit e a mesma modificação não poderá ser refeita. Mata todos os anteriores ao commit indicado, não contando ele:
```
$ git reset --hard hash_do_commit 
```

:bangbang: a "hash" se trata de um número de modificação e cada commit possui o seu. É possível visualizá-la através do comando "git log".









## Conectar seu repositório ao Github :computer: :arrow_right: :octocat:

Para conectar o repositório que você criou em seu computador com a sua conta do Github utilizaremos o protocolo SSH, muito comum para acesso remoto.
Para isso, siga os seguintes passos:

:arrow_right: Crie um repositório dentro do seu Github:

![new repos](https://user-images.githubusercontent.com/126173770/225103286-5a10ba6b-9a4b-4e66-b5bf-e7ef586db5c9.png)</center>

:arrow_right: Liste as chaves SSH existentes em seu computador pelo comando:
```
ls -al ~/.ssh
```
![image](https://user-images.githubusercontent.com/126173770/225324618-b8fcad71-9978-4812-bd58-3ecae3258787.png)

:arrow_right: A chave com a extensão .pub será a utilizada. Para mostrar seu conteúdo, digite:
```
$ cat ~/.ssh/id_ed25519.pub
```

:bangbang: Se não houver chaves SSH, crie através do terminal uma com o email utilizado no seu Github, através do seu seguinte comando:
```
$ ssh-keygen -t ed25519 -C "email_utilizado_no_github.com"
```
Ele pedirá uma senha e sua confirmação.
Se não funcionar, tente este:
```
$ ssh-keygen -t rsa -b 4096 -C "email_utilizado_no_github.com"
```

Para dúvidas relacionadas ao SSH e à conexão com o Github, acesse https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

:arrow_right: Após copiar o conteúdo da sua chave SSH, adicione no seu github na aba "SSH and GPG keys" que fica nas configurações:

 Passo 1:
 
 ![image](https://user-images.githubusercontent.com/126173770/225325852-5f440292-d1f3-486f-8418-224c1acfa017.png)
 
 Passo 2:
 
 ![image](https://user-images.githubusercontent.com/126173770/225326228-91ebd9f7-bcb5-423f-a814-5ef0d482ff92.png)

:arrow_right: Prontinho, seu computador e Github estão conectados e prontos para atualizações! :rocket:







## Como rodar os testes

Coloque um passo a passo para executar os testes

```
$ npm test, rspec, etc 
```

## Casos de Uso

Explique com mais detalhes como a sua aplicação poderia ser utilizada. O uso de **gifs** aqui seria bem interessante. 

Exemplo: Caso a sua aplicação tenha alguma funcionalidade de login apresente neste tópico os dados necessários para acessá-la.

## JSON :floppy_disk:

### Usuários: 

|name|email|password|token|avatar|
| -------- |-------- |-------- |-------- |-------- |
|Lais Lima|laislima98@hotmail.com|lais123|true|https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcS9-U_HbQAipum9lWln3APcBIwng7T46hdBA42EJv8Hf6Z4fDT3&usqp=CAU|

... 

Se quiser, coloque uma amostra do banco de dados 

## Iniciando/Configurando banco de dados

Se for necessário configurar algo antes de iniciar o banco de dados insira os comandos a serem executados 

## Linguagens, dependencias e libs utilizadas :books:

- [React](https://pt-br.reactjs.org/docs/create-a-new-react-app.html)
- [React PDF](https://react-pdf.org/)

...

Liste as tecnologias utilizadas no projeto que **não** forem reconhecidas pelo Github 

## Resolvendo Problemas :exclamation:

Em [issues]() foram abertos alguns problemas gerados durante o desenvolvimento desse projeto e como foram resolvidos. 

## Tarefas em aberto

Se for o caso, liste tarefas/funcionalidades que ainda precisam ser implementadas na sua aplicação

:memo: Tarefa 1 

:memo: Tarefa 2 

:memo: Tarefa 3 

## Desenvolvedores/Contribuintes :octocat:

Liste o time responsável pelo desenvolvimento do projeto

| [<img src="https://avatars2.githubusercontent.com/u/46378210?s=400&u=071f7791bb03f8e102d835bdb9c2f0d3d24e8a34&v=4" width=115><br><sub>Diana Regina</sub>](https://github.com/Diana-ops) |  [<img src="https://avatars2.githubusercontent.com/u/46378210?s=400&u=071f7791bb03f8e102d835bdb9c2f0d3d24e8a34&v=4" width=115><br><sub>Diana Regina</sub>](https://github.com/Diana-ops) |  [<img src="https://avatars2.githubusercontent.com/u/46378210?s=400&u=071f7791bb03f8e102d835bdb9c2f0d3d24e8a34&v=4" width=115><br><sub>Diana Regina</sub>](https://github.com/Diana-ops) |
| :---: | :---: | :---: 

## Licença 

The [MIT License]() (MIT)

Copyright :copyright: Ano - Titulo do Projeto
