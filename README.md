# 🚀 Guia Prático de Git (Principais Comandos)

## 💡 Se você utiliza GIT no seu dia a dia, esse material foi feito para você! 

Nos próximos tópicos, procuramos explicar alguns conceitos básicos e bastante utilizados no nosso dia a dia. Não deixe de aproveitar e se possível, contribuir para a melhoria e otimização deste Guia Prático.

*   🤔 **O que é Git?** Imagine uma máquina do tempo para o seu código. Git é essa ferramenta que rastreia todas as mudanças e permite voltar atrás se algo der errado (e vai acontecer! 😂).
*   🎯 **Por que usar?** Organize projetos, colabore em equipe, e nunca mais perca seu progresso! É como ter um superpoder de controle de código! 🦸
*   📜 **O que você vai aprender?** Os principais comandos e técnicas essenciais para o sucesso do desenvolvedor. 
*   💻 **Para quem?** Todos que se utilizam da ferramenta para o versionamento do seu código!

## 📌 Configuração Inicial  
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@email.com"
git config --list  # Ver configurações
```
## 📂 Criando e Clonando Repositórios  
```bash
git init  # Iniciar repositório (analisar o uso, pois em algumas situações o GIT já está instalado, não sendo necessário o uso deste comando)
git clone <URL.git>  # Clonar repositório remoto
```

## 💻 Status e Histórico  
```bash
git status  # Ver mudanças
git log  # Histórico de commits
git log --oneline --graph --decorate --all  # Visualização simplificada
git log --oneline -4  # Visualização dos últimos 4 commits
```

## 📖 Controle de Versões  
```bash
git add nome_do_arquivo.extensao  # Adicionar arquivo ao staging
git add .  # Adicionar tudo
git commit -m "Mensagem do commit"  # Criar commit
git commit -am "Nova mensagem"  # um comando mais ágil que realiza o add e o commit ao mesmo tempo (lembrando que para arquivos Untracked ainda deve ser usado `git add`, isso serve para arquivos Modified)
git checkout -- <arquivo>  # Descartar mudanças locais
git reset HEAD <arquivo>  # Remover do staging
```

## 🕹️ Git em Ação: O Fluxo de Trabalho do dia-a-dia 

*   🖼️ **Os Bastidores: Os Estados do Git:**
    *   *Imagina um fluxo como um pipeline, e o seu código é a matéria prima, vamos te guiar por todas as fases do pipeline!* 
    *   ⚪ **Untracked:** Arquivos que ainda não estão no radar do Git.
    *   🟢 **Staged:** Os arquivos que serão "congelados" na próxima atualização! 
    *   🟠 **Modified:** Se você mudou algo em um arquivo que o Git já rastreia, ele fica aqui.
    *   🔵 **Committed:** Seu código "congelado" no tempo, pronto para ser resgatado sempre que precisar.

## 🔄 Sincronização com Repositório Remoto  
```bash
git remote -v  # Ver repositórios remotos
git remote add origin <URL>  # Adicionar repositório remoto
git push origin master  # Enviar commits para o repositório remoto
git pull origin master  # Atualizar código local
git fetch origin  # Buscar atualizações sem mesclar
```

## 🌿 Trabalhando com Branches  
```bash
git branch  # Listar branches
git branch <nome>  # Criar nova branch
git checkout <nome>  # Trocar de branch
git checkout -b <nome>  # Criar e mudar para nova branch
git merge <branch>  # Mesclar branch na atual
git branch -d <nome>  # Deletar branch local
git push origin --delete <nome>  # Deletar branch remota
git log --oneline --all # Lista todos os commits de todas as branches
git branch -d <nome> # Apaga a branch
```

## ♻️ Revertendo Mudanças  
```bash
git revert <hash>  # Criar um commit que desfaz uma alteração
git reset --hard <hash>  # Resetar para um commit específico (perde alterações locais)
git reset --soft <hash>  # Resetar mantendo alterações no staging
```

## 🛠️ Resolvendo Conflitos  
```bash
git merge <branch>  # Pode gerar conflitos
# Editar arquivos manualmente, depois:
git add <arquivo>
git commit -m "Resolvendo conflito"
```

## 🔀️️ Ignorando arquivos com o.gitignore
```bash
touch .gitignore # comando para criação do arquivo git ignore

vim .gitignore # abrindo o editor de textos padrão (vim)
```
**No editor de texto, você deve incluir todos os arquivos únicos, 
repositórios e/ou extensões que não deverão ser commitados 
ao repositório remoto (ex.: senhas, arquivos grandes que não 
devem ser enviados, banco de dados, credenciais, etc)**

**Exemplos:**
```bash
*.env # exemplo para todos os arquivos nessa extensão
venv/ # exemplo para repositório completo
meu_arquivo.txt # exemplo para arquivo único
```

## 🔍 Extras  
```bash
git reflog  # Histórico de todas as ações no repositório

git rebase nome_da_branch 

*REBASE*: Em um Rebase você retira as suas mudanças e depois 
          repõe os seus commits um por um por cima dessas mudanças, 
          fazendo o seu histórico mais limpo. 
*MERGE*:  Em um merge o Git junta seus commits com mais um de mesclagem. 

```
**Afinal, quando usar MERGE ou REBASE?**
*   `MERGE` > Use para manter o histórico, preservando como a colaboração aconteceu.
*   `REBASE`> Por não criar um commit de merge, use para manter uma história de projeto linear, organizada e compreensível, voltado a colaboração em equipe.

---  

### 🚀 Dicas Finais De Boas Práticas
*  ✅ Use `git add .` somente se você quiser colocar tudo no stage, cuidado pra não commit algo que não devia.
*   ✨ Use as mensagens de commit para ajudar você e seus colegas de time! Não hesite em dar detalhes dos commits.
*    🤔 Analise os commits antes de comitar, o que eu quero salvar dessa etapa do meu projeto? 
*  🔥 Sempre que precisar ver os commits e descobrir quando uma funcionalidade ou problema foi adicionado, consulte o git log.
* 💫 Se precisar refazer seus commits, utilize o reset, se quiser desfazer apenas um, revert, e lembre-se que você precisa de commits salvos no git log para estas funções serem eficazes. 

Esperamos que este guia possa ser um auxiliador na sua jornada 😃 . E caso tenha alguma sugestão de melhoria, não hesite em nos comunicar via [e-mail](link) 🚀
