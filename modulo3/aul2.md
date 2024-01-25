## Trabalhando com branchs

### Para criar uma nova branch e já alterar para ela
git checkout -b [nome da branch]

### Verificar quantas branchs temos
git branch

### Para mudar de branch
git checkout [nome da branch]

### Enciando sua branch local para o repositório remoto
git push --set-upstream origin [nome]
Temos que faezr isso para que a branch que foi criada apenas localmente seja enviada/criada no repositório remoto

### Fazendo um merge locoal
git merge