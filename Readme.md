# github
Arquivo da aula de git e github para iniciante
Digite, no bash, vim <nomedoarquivo.extensao> para abrir o arquivo dentro do editor vim
No vim, digite I para entrar no modo inserção.
Apertar a tecla : para sinalizar que deseja iniciar algum comando
Apertar a tecla w após o :, identifica que o comando será de write, escrita.
Apertar a tecla q, após o :, identifica que deseja sair do vim.
Apertar :wq identifica que deseja iniciar um comando, que será um comando de escrita e para sair do vim.
A tecla esc sai do comando atual.

Ciclo de vida dos estados dos arquivos no GIT
1 - Untracked
O arquivo acabou de ser add no repositório, mas ainda não foi visto pelo GIT. Não existe nenhuma versão desse arquivo.
2 - Unmodified
Quando você adiciona o arquivo no GIT ele recebe esse estado. Ele é visto pelo GIT porém ainda não foi modificado
3 - Modified
Quando o arquivo receber alguma alteração.
4 - Staged
O arquivo após ser modificado, pode ser enviado para área de STAGED que é onde ele vai esperar a versão do projeto ser fechada (commit). Depois do commit, todos os meus arquivos staged serão considerados unmodified.

Esse é um repositório teste para ensinar como o git funciona

O que é um COMMIT
- Basicamente é você dizer para o GIT: "Olha, GIT, por favor cara. Pegue todos os arquivos aqui do meu repositório e crie uma imagem deles, crie um SNAPSHOT.

Comando -> git commit -m "Mensagem do commit"

Visualização de LOGS
- git log 
- git log --decorate
- git log author "nome do autor"
- git log --graph
- git shortlog 
- git shortlog -sn
- git show "hash do commit"

Todos esses comandos retornam logs de commits que foram enviados por todos os autores com acesso ao repositório.


