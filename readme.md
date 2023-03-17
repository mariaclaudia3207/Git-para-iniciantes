<h1 align="center">Git para Iniciantes</h1>


O **Git** e o **Github** são amplamente utilizados, sendo uma ferramenta primordial desde iniciantes a seniores na programação. Aqui você encontrará os primeiros passos e comandos para quem está começando agora, de forma clara e sem termos chatos que ninguém entende :)
</p>






## Sumário

:small_blue_diamond: [Primeiros passos](#primeiros-passos-fishing_pole_and_fish)

:small_blue_diamond: [Comandos básicos](#comandos-básicos-balloon)

:small_blue_diamond: [Modificando arquivos (commits)](#modificando-arquivos-commits-memo)

:small_blue_diamond: [Retornando modificações (reset)](#retornando-modificações-reset-leftwards_arrow_with_hook)

:small_blue_diamond: [Conectar seu repositório ao Github](#conectar-seu-repositório-ao-github-octocat)

:small_blue_diamond: [Como clonar repositórios remotos do Github (git clone)](#como-clonar-repositórios-remotos-do-github-git-clone)

:small_blue_diamond: [Como criar uma cópia (branch)](#como-criar-uma-cópia-branch)

:small_blue_diamond: [Como juntar a branch cópia com o arquivo principal (merge e rebase)](#como-juntar-a-branch-cópia-com-o-arquivo-principal-merge-e-rebase)

:small_blue_diamond: [Subir arquivos e modificações para o Github (push)](#subir-arquivos-e-modificações-para-o-github-push-arrow_up)

:small_blue_diamond: [Adicionando tags de versionamento ao push](#adicionando-tags-de-versionamento-ao-push)


## Primeiros passos :fishing_pole_and_fish: 

<p align="justify"> Comece instalando o Git no seu computador. Para isso acesse https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git e escolha de acordo com o seu sistema operacional (Windows, Linux, MacOS etc). Dependendo da IDE em que você for utilizar, isso pode ser feito através de extensões. </p>

Os comandos são realizados dentro de um terminal e você pode utilizar, por exemplo, o terminal do VScode, na opção "git bash":

<div align="center">
 
![image](https://user-images.githubusercontent.com/126173770/225314153-a4dc06d5-4e43-462e-9417-502f53cccd91.png)

</div>

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

<p align="justify"> Durante o desenvolvimento do seu projeto, ele sofrerá inúmeras modificações e digamos que cada modificação gere um registro para que você e outras pessoas que estejam contribuindo possam acompanhar a evolução. Cada modificação dentro do código é chamada de "commit". </p>

<p align="justify"> :arrow_right: Por exemplo, crie um arquivo README.md dentro da pasta do seu projeto e adicione algum texto dentro dele. Após isso, salve-o.
Ao adicionar um texto dentro do arquivo, você o modificou e para registrar essa modificação, digite o seguinte comando dentro da pasta do seu projeto, adicionando um comentário sobre a mudança que realizou: </p>

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

<p align="justify"> Caso você altere algum arquivo e deseje voltar a uma versão anterior a atual, utilize o comando "git reset". Existem algumas variações desse comando, sendo as mais comuns: </p>

:small_orange_diamond:"git reset soft", onde ele volta a modificação mas ainda existe um commit e vc pode voltar a modificar o arquivo principal:
```
$ git reset --soft hash_do_commit 
```
:small_orange_diamond:"git reset hard" apaga completamente o commit e a mesma modificação não poderá ser refeita. Mata todos os anteriores ao commit indicado, não contando ele:
```
$ git reset --hard hash_do_commit 
```

:bangbang: a "hash" se trata de um número de modificação e cada commit possui o seu. É possível visualizá-la através do comando "git log".









## Conectar seu repositório ao Github :octocat:

<p align="justify"> Para conectar o repositório que você criou em seu computador com a sua conta do Github utilizaremos o protocolo SSH, muito comum para acesso remoto.
Para isso, siga os seguintes passos: </p>

:arrow_right: Crie um repositório dentro do seu Github:

<div align="center">

![new repos](https://user-images.githubusercontent.com/126173770/225103286-5a10ba6b-9a4b-4e66-b5bf-e7ef586db5c9.png)</center>

</div>

:arrow_right: Liste as chaves SSH existentes em seu computador pelo comando:
```
ls -al ~/.ssh
```
<div align="center">

![image](https://user-images.githubusercontent.com/126173770/225324618-b8fcad71-9978-4812-bd58-3ecae3258787.png)

</div>
 
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

<p align="justify"> Para dúvidas relacionadas ao SSH e à conexão com o Github, acesse https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent . </p>

:arrow_right: Após copiar o conteúdo da sua chave SSH, adicione no seu github na aba "SSH and GPG keys" que fica nas configurações:

 Passo 1:
 
 <div align="center">
 
 ![image](https://user-images.githubusercontent.com/126173770/225325852-5f440292-d1f3-486f-8418-224c1acfa017.png)
 
 </div>
 
 Passo 2:
 
 <div align="center">
 
 ![image](https://user-images.githubusercontent.com/126173770/225326228-91ebd9f7-bcb5-423f-a814-5ef0d482ff92.png)

 </div>
 
:arrow_right: Prontinho, seu computador e Github estão conectados e prontos para atualizações! :rocket:









## Como clonar repositórios remotos do Github (git clone)

Para baixar um repositório em que você está trabalhando ou encontrou no github para o seu computador, existe o comando "git clone":
```
g clone chave_do_repositorio nome_que_vai_ficar_salvo
```
A chave do repositório pode ser encontrada na aba:

<div align="center">

![image](https://user-images.githubusercontent.com/126173770/225379646-73a491fb-15d9-4a51-a10b-5ef1faa0d629.png)

</div>









## Como criar uma cópia (branch)

<p align="justify"> As branchs se tratam de cópias que você faz para alteração. Alterar o arquivo principal é meio arriscado rsrs e por isso fazemos isso na programação. Para criar uma branch, utilize o seguinte comando: </p>

```
$ git checkout -b nome_da_branch
```

É bem simples mesmo. Depois que alteramos essas cópias podemos passá-las para o arquivo principal, os chamados "commits" :)


:large_orange_diamond: Outros comandos relacionados a branchs:

:small_orange_diamond: Lista todas as branchs existentes no repositório e mostra em qual você está no momento:
```
$ git branch
```
:small_orange_diamond: Para excluir uma branch:

```
$git branch -D nome_do_branch
```







## Como juntar a branch cópia com o arquivo principal (merge e rebase)

Para você passar as informações da branch de cópia para a branch main ou master, que é o arquivo principal que você está trabalhando no momento, existem dois comandos:


:arrow_right: Merge

Através do "merge" você pode unir as duas branchs, mesclando assim as modificações e diferenças entre cada uma:
```
$ git merge nome_do_branch
```

:arrow_right: Rebase

<p align="justify"> Com o "rebase" é possível unir duas branchs e as modificações no arquivo (commits) são mostrados de forma linear, poluindo menos as informações de commits do seu repositório. Ele é geralmente mais utilizado e pode ser usado através do comando: </p>
``` 
$ git rebase  nome_do_branch
```








## Subir arquivos e modificações para o Github (push) :arrow_up:

<p align="justify"> Após você conseguir conectar o repositório do seu computador ao repositório do Github, você poderá passar os arquivos para lá. Para isso, será usado o comando "push", saindo da origem (origin) para o main ou master do github: </p>

```
$ git push origin master_ou_main(nome do principal)
```






## Adicionando tags de versionamento ao push

<p align="justify"> A cada versão do seu projeto que será enviada para o github através do push, pode ser adicionada a nota de versão (ex: 1.0.0). Para isso, utilize os seguintes comandos: </p>

```
git tag -a 1.0.0 -m "comentários etc"
git push origin main --tags 
```
















