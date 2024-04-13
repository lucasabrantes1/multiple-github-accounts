# personal-multiple-github-accounts-Edited

### Pré-requisito
- Git instalado

### Steps
### 1. Crie os arquivos Git de configuração
  ```
    $ cd ~
    $ touch .gitconfig .gitconfig-personal .gitconfig-work
  ```

### 2. Copie as seguintes informações para os arquivos Git de configuração
  ```
    $ vim .gitconfig

    [user]
	    name = Anderson Silva de Sa
    [includeIf "gitdir:~/workspace/personal/"]
	    path = ~/.gitconfig-personal
    [includeIf "gitdir:~/workspace/work/"]
	    path = ~/.gitconfig-work
  ```

    $ vim .gitconfig-personal

    [user]
	    name = Anderson Silva de Sa
	    email = asilvadesa@gmail.com

    [core]
	    sshCommand = "ssh -i ~/.ssh/personal_id_rsa"
  ```
    $ vim .gitconfig-work

    [user]
	    name = Anderson Silva de Sa
	    email = asilvagit@gmailcom

    [core]
	    sshCommand = "ssh -i ~/.ssh/work_id_rsa"
  ```

### 3. Crie os diretórios

```
    $ cd ~
    $ mkdir workspace
    $ cd worksppace
    $ mkdir personal work
```
### 5. Caso nunca tenha criado chave ssh

```
    $ mkdir -p ~/.ssh
    $ cd ~/.ssh

```

### 4. Crie as chaves SSH

```
    $ cd ~/.ssh
    $ ssh-keygen -f personal_id_rsa
    $ ssh-keygen -f work_id_rsa
```
### 5. Copie as chaves SSH

```
    $ cd ~/.ssh
    $ cat personal_id_rsa.pub
    $ cat work_id_rsa.pub
```

### 6. Colar as chaves ssh em sua respectivar contas

```
  $ cat personal_id_rsa.pub | clip
  $ cat work_id_rsa.pub | clip
  
```

### 7. Colar as chaves ssh em sua respectivar contas

```
  $ cat personal_id_rsa.pub | clip
  $ cat work_id_rsa.pub | clip
  
```

### 8. Ligar o SSH e clonar no work

```
  $ eval "$(ssh-agent -s)"
  $ cd workspace/work 
  ssh-add ~/.ssh/work_id_rsa
  ssh -T emaildacontacadastradadeWORK@gmail.com
  ssh -T git@github.com
  git clone https://github/projetodoWORK


  $ eval "$(ssh-agent -s)"
  $ cd workspace/personal 
  ssh-add ~/.ssh/personal_id_rsa
  ssh -T emaildacontacadastradadePERSONAL@gmail.com
  ssh -T git@github.com
  git clone https://github/projetodoPERSONAL	

```

### 9. Configuração do arquivo ssh (EXTRA)

```
# Configuração para a conta pessoal
Host github.com-personal
  HostName github.com
  User git
  IdentityFile ~/.ssh/personal_id_rsa

# Configuração para a conta de trabalho
Host github.com-work
  HostName github.com
  User git
  IdentityFile ~/.ssh/work_id_rsa	

```




