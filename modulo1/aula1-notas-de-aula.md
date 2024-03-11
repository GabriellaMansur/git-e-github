## Conceitos iniciais

Nesse módulo foi explicado alguns comandos básicos do git, assim como suas aplicações e exemplos de como usá-los

git commit

Branch: são separações de código, possibilita que as pessoas trabalhem de maneira independente em um mesmo projeto. A branch inicial sempre é a master. Develope: ambiente em remoi de desenvolvimento. Homolog: após altereções serem validade no ambiente de desenvolvimento, o código vai para a branch dehomologação para validações e testes de pessoas de negócio e de qualidade.

Pull: atualiza o repositório local. É realizado um merge entre o repositório online com o que temos localmente

Fork: depois de "forkar" um repositório de outra pessoas, você pode fazer um pull-requent para contribuit com o coteúdo do repositório princiapl

## Configurar o Github
1 - abrir git bash
2 - git config --global user.name "SeuUserName"
3 - git config --global user.email "exemplo@seuemail.com.br"

## Configurar chave ssh
1 - verificar chaves existentes -> ls -al ~/.ssh
2 - para gerar uma chave nova
    * Para criar uma chave ed25519, executar: ssh-keygen -t ed25519 -C "your_email@example.com"
    * Para criar uma chave rsa, executar: ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
3 - Rodar o ssh-agent: eval $(ssh-agent -s)
4 - Incluir a chave privada: ssh-add ~/.ssh/id_ed25519
5 - Copiar chave pública
    * windowns: clip < ~/.ssh/id_ed25519.pub
    * linux: cat ~/.ssh/id_ed25519.pub
6 - Após isso, adicionar a chave no github
    * configuração > SSH and GPG keys > new SSH Key