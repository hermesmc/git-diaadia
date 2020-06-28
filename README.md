# git no dia-a-dia

Algumas descrições de comandos foram colhidas no site: https://www.atlassian.com/br/git/tutorials<br>
Para maiores detalhes, acesse o site acima.<br>

- Apenas um alfarrábio para manter os principais comando do GIT que serão utilizados por mim:

<h3>git status:</h3> O comando git status exibe as condições do diretório de trabalho e da área de staging. Ele permite que você veja quais alterações foram despreparadas, quais não foram e quais arquivos não estão sendo monitorados pelo Git.
<br>
<h3>git push:</h3> 
O comando git push é usado para enviar conteúdo do repositório local para um repositório remoto. "Push" é como os commits do repositório local são enviados a um repositório remoto.

<br>
<h3>git pull:</h3> 
O comando git pull é usado para buscar e baixar conteúdo de um repositório remoto e atualizar na hora o repositório local para que tenha o mesmo conteúdo. Fazer merge de alterações remotas de upstream em seu repositório local é uma tarefa comum em fluxos de trabalho de colaboração baseados em Git. O comando git pull é, na verdade, uma combinação de dois outros comandos git fetch seguido por git merge. Na primeira etapa da operação, git pull vai executar um git fetch do escopo para o ramo local ao qual HEAD está apontado. Depois que o conteúdo for baixado, git pull vai entrar em um fluxo de trabalho de merge. Um novo commit de merge vai ser criado e HEAD vai ser atualizado para apontar para o novo commit.
<br>
<h3>git add:</h3>
O comando git add adiciona uma alteração no diretório ativo à área de staging. Ele diz ao Git que você quer incluir atualizações a um arquivo particular na próxima confirmação. No entanto, git add não afeta realmente o repositório de nenhuma forma significativa—as alterações não são realmente gravadas até você executar git commit.
<br>
Exemplo: git add .
<br>
<h3>git commit -m "comentário":</h3>
<br>

<h3>Os comandos git add e git commit compõem o fluxo de trabalho fundamental do Git. Esses são os dois comandos que cada usuário do Git precisa entender, independentemente do modelo de colaboração da equipe. Eles são os meios para gravar versões de um projeto no histórico do repositório. Além de git add e git commit, um terceiro comando git push é essencial para um fluxo de trabalho colaborativo completo do Git. </h3>
<br>
<h3>git fetch:</h3>
<br>
<h3>git checkout:</h3>
