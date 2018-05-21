# Git, Git Flow e GitHub

### Links Úteis
1. [Tudo que você queria saber sobre Git e GitHub, mas tinha vergonha de perguntar](https://tableless.com.br/tudo-que-voce-queria-saber-sobre-git-e-github-mas-tinha-vergonha-de-perguntar/)

2. [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)

#### Gerar **SSH Key**
```
$ ssh-keygen
```

#### Verificar se a instalação do git está ok. Se estiver, retornará comandos e informações do git
```
$ git
```

#### Verificar a **versão** do git instalada
```
$ git version
```

#### **Configurar** o git
```
$ git config --global user.name "username"
$ git config --global user.email "your@email.com"
$ git config --global color.ui true
$ git config --global core.editor nano
```

#### **Iniciar o repositório** git (rodar na pasta que vc deseja versionar)
```
$ git init
```

#### **Iniciar o repositório bare** git
[Qual é a diferença entre `git init` e `git init --bare`?](https://pt.stackoverflow.com/questions/80182/qual-%C3%A9-a-diferen%C3%A7a-entre-git-init-e-git-init-bare)
```
$ git init --bare
```

## **1° Git Stage** untracked files ou changes not staged *(unstaged)*
> Novo arquivo que não está versionado pelo git ainda ou arquivo que foi modificado.

## **2° Git Stage** changes to be committed *(staged)*
> Arquivo adicionado para o stage e agora está pronto para ser comitado.

## **3° Git Stage** committed files *(committed)*
> O arquivo foi comitado e está versionado.

#### Verificar o **status** do repositório e o **branch atual**.
```
$ git status
```

#### Verificar o histórico do branch atual
```
$ git log
```

#### Verificar o histórico dos ultimos 90 dias (padrão) do repositório
```
$ git reflog
```

#### **Interface gráfica** para verificar o histórico do repositório.
```
$ gitk
```

#### **Adiciona** arquivos específicos do *unstaged* para o *staged*.
```
$ git add <file>
```

#### **Adiciona** todos os arquivos do *unstaged* para o *staged*.
```
$ git add .
```

#### Abre o editor padrão para escrever o comentário e *comita* todos os arquivos do *staged*.
```
$ git commit
```

#### Abre o editor padrão para escrever o comentário e *comita* todos os arquivos estando ou não no *staged*, ou seja, até os arquivos do *unstaged*
```
$ git commit -a
```

#### *Comita* todos os arquivos do *staged* junto com o comentário
```
$ git commit -m 'Descrição do que foi feito da melhor forma possível, brevemente'
```

#### **Renomear** e/ou **Mover** um arquivo
```
$ git mv <old_file> <new_file>
```

#### **Remove** arquivos específicos do *staged* para o *unstaged*
```
$ git reset <file>
```

#### **Remove** todos os arquivos do *staged* para o *unstaged*
```
$ git reset --
```

#### **Voltar commits** e **manter** as alterações no *staged*. Troque `xx` por quantos commits você quer voltar
```
$ git reset --soft HEAD~xx
```

#### **Voltar commits** e **apagar** as alterações. Troque `xx` por quantos commits você quer voltar
```
$ git reset --hard HEAD~xx
```

#### **Voltar para um commit específicado com o id** (pode usar os mesmos parâmetros *--soft* | *--hard*)
```
$ git reset <id_commit>
```

#### **Listar** *branchs*
```
$ git branch
```

#### **Criar** *branch*
```
$ git checkout -b <branch>
```

#### **Trocar** *branch*
```
$ git checkout <branch>
```

#### **Adicionar** repositório remoto. O padrão quase sempre é `origin`
```
$ git remote add <name> <url>
```

#### **Apagar** repositório remoto
```
$ git remote rm <name> <url>
```

#### **Renomar** repositório remoto
```
$ git remote rename <old_name> <new_name>
```

#### **Listar** repositórios remotos
```
$ git remote -v
```

#### **Verificar** repositórios remoto
```
$ git remote show <name>
```

#### **Enviar** branch atual para um branch no repositório remoto
```
$ git push <remote> <branch>
```

#### **Sincronizar** git com um repositório remoto
```
$ git pull
```

#### **Sincronizar** branch atual com um branch no repositório remoto
```
$ git pull <remote> <branch>
```

#### **Clonar (baixar)** um branch de um repositório remoto
```
$ git checkout -b <branch> <remote>/<branch>
```

#### **Clonar (baixar)** um repositório
```
$ git clone <url>
```

#### **Sincronizar** o repositório
[Qual a diferença entre os comandos 'git pull' e 'git fetch'?
](https://pt.stackoverflow.com/questions/3231/qual-a-diferen%C3%A7a-entre-os-comandos-git-pull-e-git-fetch)
```
$ git fetch <remote>
```

#### **Criar** um release (tag)
```
$ git tag <version>
```

#### **Apagar** um release (tag) LOCALMENTE
```
$ git tag -d <version>
```

#### **Apagar** um release (tag) REMOTO
```
$ git push origin :refs/tags/<version>
```

#### **Listar** releases (tags)
```
$ git tag -l
```

#### **Sincronizar** releases (tags)
```
$ git push <remote> <branch> --tags
```

#### **Configurar** alias.
```
$ git config --global alias.v version
$ git config --global alias.cl clone
$ git config --global alias.s status
$ git config --global alias.b branch
$ git config --global alias.ck checkout
$ git config --global alias.l 'log --pretty=oneline --graph'
$ git config --global alias.lf 'log --pretty=fuller --stat -p --graph -1'
```

#### **Visualizar** todos os alias
```
$ nano ~/.gitconfig
```

#### **Apagar** um alias. Troque `xx` pelo alias que você quer apagar
```
$ git config --global --unset alias.xx
```

#### **Fast Config**
```
$ git config --global user.name "username";git config --global user.email "your@email.com";git config --global color.ui true;git config --global core.editor nano;git config --global alias.v version;git config --global alias.cl clone;git config --global alias.s status;git config --global alias.b branch;git config --global alias.ck checkout;git config --global alias.l 'log --pretty=oneline --graph';git config --global alias.lf 'log --pretty=fuller --stat -p --graph -1'
```

## Git Flow
#### Iniciar repositório Git com Git Flow
```
$ git flow init
```

## **Git Flow** Feature
#### Listar features
```
$ git flow feature list
```

#### Criar uma feature. **Irá criar um branch a partir do develop**
```
$ git flow feature start <feature>
```

#### Finalizar uma feature (merge "no fast-forward" com develop). **Irá excluir o branch da feature** (--keepremote mantem no remoto)
```
$ git flow feature finish <feature>
```

#### Finalizar uma feature (merge "no fast-forward" com develop). **Irá manter o branch da feature**
```
$ git checkout develop
$ git merge --no-ff <feature/feature>
```

#### Enviar uma feature para o repositório remoto. **Irá fazer um push desse branch**
```
$ git flow feature publish <feature>
```

#### Pegar uma feature do repositório remoto. **Irá fazer um pull desse branch**
```
$ git flow feature track <feature>
```

## **Git Flow** Release
[Versionamento Semântico 0.0.0](https://semver.org/lang/pt-BR/)

#### Criar release
```
$ git flow release start <version>
```

#### Publicar release
```
$ git flow release finish <version>
```

## Hotfix (Git Flow)
#### Criar hotfix (usar sempre uma version maior que a atual que será corrigida)
```
$ git flow hotfix start <version>
```

#### Publicar release
```
$ git flow hotfix finish <version>
```

## **Git Flow** Bugfix
#### Criar bugfix
```
$ git flow bugfix start <bugfix>
```

#### Publicar bugfix
```
$ git flow bugfix finish <bugfix>
```

# License
[WTFPL](http://www.wtfpl.net/)
