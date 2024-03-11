# Apostila Git

## Configurar o Github
**1** - abrir git bash
**2** - `git config --global user.name "SeuUserName"`
**3** - `git config --global user.email "exemplo@seuemail.com.br"`

## Configurar chave ssh
**1** - verificar chaves existentes -> ls -al ~/.ssh
**2** - para gerar uma chave nova
    * Para criar uma chave ed25519, executar: ssh-keygen -t ed25519 -C "your_email@example.com"
    * Para criar uma chave rsa, executar: ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
**3** - Rodar o ssh-agent: eval $(ssh-agent -s)
**4** - Incluir a chave privada: ssh-add ~/.ssh/id_ed25519
**5** - Copiar chave pública
    * windowns: clip < ~/.ssh/id_ed25519.pub
    * linux: cat ~/.ssh/id_ed25519.pub
**6** - Após isso, adicionar a chave no github
    * configuração > SSH and GPG keys > new SSH Key

## Conceitos iniciais

Nesse módulo foi explicado alguns comandos básicos do git, assim como suas aplicações e exemplos de como usá-los

* **Branch**: são separações de código, possibilita que as pessoas trabalhem de maneira independente em um mesmo projeto. A branch inicial sempre é a master. Develope: ambiente em remoi de desenvolvimento. Homolog: após altereções serem validade no ambiente de desenvolvimento, o código vai para a branch dehomologação para validações e testes de pessoas de negócio e de qualidade.

* **Pull**: atualiza o repositório local. É realizado um merge entre o repositório online com o que temos localmente

* **Fork**: depois de "forkar" um repositório de outra pessoas, você pode fazer um pull-requent para contribuit com o coteúdo do repositório princiapal

## Fluxo de trabalho criando um repositório e iniciando o git

**1** - inicie o git dentro do projeto na sua máquina
```git
git init
```

**2** - adicione todas as alterações
```git
git add .
```

**3** - dê o primeiro commit
```git
git commit -m "first commit"
```

**4** - nomeie a branch como main
```git
git branch -M branch
```

**5** - adicione o projeto no repositório remoto (github)
```git
git remote add origin [link]
```

****6** - mande as alterações para o github
```git
git push -u origin main
```

## Trabalhando com branchs

* Para criar uma nova branch e já alterar para ela =>
git checkout -b [nome da branch]

* Verificar quantas branchs temos => `git branch`

* Para mudar de branch => `git checkout [nome da branch]`

* Enviando sua branch local para o repositório remoto => `git push --set-upstream origin [nome]`. Temos que fazer isso para que a branch que foi criada apenas localmente seja enviada/criada no repositório remoto

* Fazendo um merge local => `git merge`

### Colaborando com projetos de outras pessoas

* Para atualizar o **fork** via linha de comando
```git
git remote add upstream [link do repositório ]
git fetch upstream
git rebase upstream/master
Obs: é possível fazer isso pelo github
```

### Revisão: Clonando um repositório, Criando uma nova branch, adicionando suas alterações, fazendo um pull request. 

```git
git clone [link do repositório]
git checkout -b [nome da branch]
git status
git add .
git commit -m "mensagem do commit"
git push
git push --set-upstream origin 
```

## Colaborando com um repositório

### Situação: fui adicionada em um repositório do github como colaboradora. O que devo fazer?

**1** - clone o repositório para sua máquina
`git clone [url do repositório]`

**2** - Nesse caso, os colaboradores estão trabalhando com branchs, então muda para a branch que deseja trabalhar
``
![git checkout node_da_branch](https://)

**3** - Para verificar quais são as branchs remotas
``
git branch -r

**4** - Para criar uma nova branch
``
git checkou -b none_da_branch

**5** - Caso tenha criado errado a branch e queira apagá-la
``
git branch -d nome_da_branch

**6** - Para saber em qual branch você está
``
git branch

**7** - Faça as suas aterações e depois adicione ao git
``
git add .

**8** - Faça um commit das suas alterações
``
git commit -m "Sua mensagem descritiva aqui"

**9** - Envie suas alterações para o GitHub
``
git push origin nome_da_branch

**10**- Abra uma Pull Request (PR)
``
Vá para a página do repositório no GitHub, clique em “Pull requests” e depois em “New pull request”. Selecione a branch principal como a branch base e sua branch como a branch de comparação. Clique em “Create pull request”, dê um título à sua PR e descreva suas alterações. Quando terminar, clique em “Create pull request” novamente.

**11** - Merge da PR
``
Depois que suas alterações forem revisadas e aprovadas, alguém com permissões de gravação no repositório pode mesclar sua PR na branch principal. Isso é feito clicando no botão “Merge pull request” na página da PR.

**12** - Atualize sua branch principal local
``
git checkout main
git pull origin main
