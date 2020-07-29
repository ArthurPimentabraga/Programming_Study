---
title: Git
author: Arthur P. Braga
---

### Git Commands

```shell
--amend -> quando se deseja modificar a mens do commit. (Escrever outro commit com a mens certa colocando esse comando no final);

git reset --soft HEAD~(nº de commits p/ trás)-> reseta os commits feitos sem perder o conteúdo; 

git reset --hard HEAD~(nº de commits p/ trás)-> reseta os commits feitos deletando o conteúdo;

git status -> mostra o status de alteração, ou seja, oq vc modificou e ainda não fez commit...

git add -i -> opção interativa para add arquivos modificados no commit.
    (É bom quando modificou mais de um tipo de arquivo e quer dividi-los em mais de um commit);

git reset -- -> reseta o repositório para o estado do último commit;
```

- Caso esqueça de fazer pull: 

```shell
git stash save
git stash apply
```
