# github
Arquivo da aula de git e github para iniciante &nbsp;
Digite, no bash, vim <nomedoarquivo.extensao> para abrir o arquivo dentro do editor vim
No vim, digite I para entrar no modo inserção. &nbsp;
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

Vamos aprender agora sobre DIFF. Como visualizar as diferenças num arquivo antes de realizar um commit.

- git diff 
- git diff --name-only

Dessa forma, utilizando o git diff, você consegue visualizar alterações no seu arquivo antes de realizar um commit. 

Agora um ponto importantíssimo, como DESFAZER alguma ação usando GIT?

- git checkout <nome_do_arquivo> : Retorna as alterações anteriores antes de irem para staged area.
- git reset HEAD : Retira o arquivo da fila do staged, e o retorne para o estágio anterior, a partir dai pode-se usar o git checkout.
- git reset --soft --mixed --hard: retorna o arquivo do commit para a área de staged; retorna os arquivos para o estado modified, antes do estágio; mata tudo que foi feito no commit, destroi todas as alterações.
Ponto importante: deve ser passado a hash do commit anterior ao que se deseja resetar.

Como eu faço para mandar um arquivo modificado no meu local para o github?

- Após comitado, é necessário realizar um push através do comando: git push origin <branch_atual>
obs: o nome do repositório origin é padrão.

- Para clonar um repositório para o seu local basta usar o comando git clone <endereço http ou ssh do repositorio> <nome do arquivo criado local>

