# github
Arquivo da aula de git e github para iniciante &nbsp;
Digite, no bash, vim <nomedoarquivo.extensao> para abrir o arquivo dentro do editor vim
### No vim, digite I para entrar no modo inserção. &nbsp;
- Apertar a tecla : para sinalizar que deseja iniciar algum comando
- Apertar a tecla w após o : identifica que o comando será de write, escrita.
- Apertar a tecla q após o : identifica que deseja sair do vim. 
- Apertar :wq identifica que deseja iniciar um comando, que será um comando de escrita e para sair do vim.
- A tecla esc sai do comando atual.

### Ciclo de vida dos estados dos arquivos no GIT
- Untracked
O arquivo acabou de ser add no repositório, mas ainda não foi visto pelo GIT. Não existe nenhuma versão desse arquivo.
- Unmodified
Quando você adiciona o arquivo no GIT ele recebe esse estado. Ele é visto pelo GIT porém ainda não foi modificado
- Modified
Quando o arquivo receber alguma alteração.
- Staged
O arquivo após ser modificado, pode ser enviado para área de STAGED que é onde ele vai esperar a versão do projeto ser fechada (commit). Depois do commit, todos os meus arquivos staged serão considerados unmodified.

Esse é um repositório teste para ensinar como o git funciona

O que é um COMMIT
- Basicamente é você dizer para o GIT: "Olha, GIT, por favor cara. Pegue todos os arquivos aqui do meu repositório e crie uma imagem deles, crie um SNAPSHOT.

Comando -> git commit -m "Mensagem do commit"

## Visualização de LOGS
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

## Agora um ponto importantíssimo, como DESFAZER alguma ação usando GIT?

- git checkout <nome_do_arquivo> : Retorna as alterações anteriores antes de irem para staged area.
- git reset HEAD : Retira o arquivo da fila do staged, e o retorne para o estágio anterior, a partir dai pode-se usar o git checkout.
- git reset --soft --mixed --hard: retorna o arquivo do commit para a área de staged; retorna os arquivos para o estado modified, antes do estágio; mata tudo que foi feito no commit, destroi todas as alterações.
Ponto importante: deve ser passado a hash do commit anterior ao que se deseja resetar.

### Como eu faço para mandar um arquivo modificado no meu local para o github?

- Após comitado, é necessário realizar um push através do comando: git push origin <branch_atual>
obs: o nome do repositório origin é padrão.

### Usando o git clone:

Para clonar um repositório para o seu local basta usar o comando git clone <endereço http ou ssh do repositorio> <nome do arquivo criado local>

### Para que serve o git fork:
- Voce pode precisar 'forkar' um projeto, quando ele não é seu, mas voce quer contribuir com ele de alguma forma, alguma documentacao que esteja faltando, algum código que precise ser acrescido. O clone não permite que voce modifique arquivos e envie de volta para o repositorio que nao é seu. Ja o fork permite que voce copie um repositorio que nao lhe pertence para o seu local de trabalho, desenvolve o que voce precise e realize um pull request para enviar as contribuicoes.

## Usando branches:

As branches permitem que várias pessoas trabalhem ao mesmo tempo em um mesmo projeto, sem se 'atropelarem'. Isso permite por exemplo que um mesmo código seja atualizado por vários contribuidores, onde cada um terá em sua branch uma cópia do projeto original em sua branch, e é nessa branch que vão ser realizadas as mudanças que posteriormente serão enviadas para a branch do projeto original (geralmente chamada de master).

Para criar uma BRANCH:
- git checkout -b <nome_da_branch>

Outros comandos uteis:
- git branch
- git checkout <nome_do_branch>
- git branch -D <nome_do_branch> (deletar)

### Ok, mas e agora, como mandar as alterações realizadas na minha branch para a branch principal?

Métodos:

- Merge: a operacao de merge cria um commit específico que vai juntar duas branches diferentes. O commit em si vai ser usado somente para fazer a junção entre as duas branches. O merge não destroi nenhum commit nesse processo. 

- Rebase: processo de fastfoward. O rebase pega tudo da branch separada que está sendo 'manipulado' e o envia para frente da fila de commits. Dessa forma ele consegue manter uma linearidade do gráfico de commits.  Basicamente então: tenho um commit e quero junta-lo a uma branch principal, esse commit será recortado e enviado para a branch principal, e o commit vai para o final da fila de commits, ele nao cria um novo commit.

## Usando o git revert

- o comando git revert pode reverter as alterações que voce realizou em um commit, porém não apaga esse commit como faz o git reset.
- ele é muito util quando voce fez alguma alteracao que quebrou o codigo em algum ponto, porém nao quer apagar o commit para não perder as alteracoes pois voce quer trabalhar naquilo.
- entao o git revert retira as alteracoes feitas, porem mantem o commit, que podera depois ser retirado da area de commits e trabalhado novamente.

