# git no dia-a-dia

As descrições de comandos foram colhidas no site: https://www.atlassian.com/br/git/tutorials<br>
Para maiores detalhes, recomendo muito que acesse o site acima.<br>

<ul>
    <li>
        Apenas um alfarrábio para manter os principais comandos do GIT que serão utilizados por mim:
   </li>        
</ul>

<h1>Índice</h1>
<a href="#C1">1 - Primeiros passos</a><br>
<a href="#C2">2 - Visualizando Branches</a> <br>
<a href="#C3">3 - Comandos do GIT</a> <br>


<h2><a name="C1">1 - Primeiros passos</a></h2>

<h3>Instalando o git:</h3>

- Acesse: https://git-scm.com/
- Efetue o download que melhor lhe atender;
- Faça a instalação "next - next";
- Se o prompt estiver aberto feche e abra novamente. Digite o comando "git". Deverão aparecer uma série de opções de comando demonstrando que o git foi instalado com sucesso.

<h3>Iniciando no GIT</h3>

- Entre na pasta que deseja que o git faça o monitoramento;
- Dê o comando: <b>git init</b>
- Para verificar se o git já está "enxergando" a pasta que você inicializou, dê o comando: <b>git status</b>;
- Para incluir todos os arquivos no monitoramento do git dê o comando: <b>git add .</b>;
- Se quiser apenas alguns arquivos do repositório dê o comando: <b>git add <nome do arquivo></b>;
- Para efetivar a versão do arquivo que está sendo salvo dê o comando: <b>git commit -m "<descrição da alteração feita>"</b> 
- Caso não esteja logado uma mensagem de erro aparacerá e será sugerido os comandos abaixo:
    <b>git config --global user.email "seu-email"</b>
    <b>git config --global user.name "seu-nome"</b>
 - Para verificar o histórico de modificações: <b>git log</b>;
 - Para ver o log de maneira simplificada: <b>git log --oneline</b>;    
 - Para ver um log mais completo <b>git log -p</b>
 - Para mais opções de log: https://devhints.io/git-log
 - Para o git ignorar o monitoramento de um ou mais arquivos:
    - na pasta do projeto, crie um arquivo chamado .gitignore;
    - inclua neste arquivo o nome dos arquivos que não queira que o git monitore.
    - inclua este arquivo, .gitignore, na monitoração do git: <b>git add -gitignore</b> - <b>git commit -m "Incluindo gitignore"</b>
    
 <h3>Criando servidor remoto</h3> 
 
 <b>A vantagem de se criar um servidor remoto ou servidor remoto é que todos da equipe podem acessá-lo para compartilhar suas atualizações.</b>
 
 - Crie uma pasta e execute o comando:<b>git init --bare</b>
 - Esse repositório não vai conter uma cópia fisica dos arquivos, só das suas alterações;
 - Para adicionar um repositório remoto na pasta onde o git está monitorando, execute:<b>git remote add <nome do servidor> <endereço do local do servidor></b>;  
 - Para verificar se o repositório remoto foi criado dê o comando:<b>git remote --v</b>; 
 
 <h4>Trazendo dados de repositório remoto</h4>
 
 - Na pasta onde deseja baixar os dados do repositório remoto dê o comando:<b>git clone <endereço do repositorio remoto> <nome da psata que será criada></b> 
 
 <h4>Enviando dados para o repositório remoto</h4>
 
 - Para enviar os dados para o repositório remoto, comando: git push <nome do repositorio> <nome da branch>
    
 <h3>Desfazendo alterações</a></h3>

- Quando você faz uma alteração em uma pasta monitorada pelo git, esta pode ser desfeita com o comando: git checkout -- <nome do arquivo>
- Quando essa alteração é feita e você preparou para o commit com o git add, o comando é: git reset HEAD <nome do arquivo>
- Quando essa alteração é feita e você já deu um commit, a sequencia é: 
    git log (aqui vc deve pegar o hash do commit que foi dado;
    git revert <hash do commit>
    
 - Recuperando um commit
    - Efetue o comando git log para localizar o hash do commit que quer recuperar;
    - Execute git checkout <6 primeiros digitos do hash>;
    - Crie uma nova branch para salvar a recuperação feita antes;
    

 <h3>Fazendo alterações temporárias</h3>

- Comando git stash (salva alteração temporária)
- Comando git stash list (lista as alterações temporárias)
- Comando git stash drop 0 (retira da lista do stash na posição 0)
- Comando git stash pop (faz um merge da alteração temporária com a atual e retira da lista do stash)   

<h3>Boa prática</h3>

- Sempre que tiver um código pronto, envie-o para o repositório principal(master):
    - <b>git push local master</b>

<h2><a name="C2">2 - Visualizando Branches</a></h2>

- Ferramenta para visualização do comportamento de branches: https://git-school.github.io/visualizing-git/


<h2><a name="C3">3 - Comandos do GIT</a></h2>

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
<h3>git commit:</h3>
O comando git commit captura um instantâneo das mudanças preparadas do projeto no momento. Os instantâneos com commit podem ser considerados versões "seguras" de um projeto, o Git nunca os altera, a menos que você peça a ele. Antes da execução de git commit, o comando git add é usado para promover ou "preparar" mudanças no projeto que são armazenadas em um commit. Estes dois comandos git commit e git add estão entre os mais usados.
<br>
Exemplo: git commit -m "comentário"

<ul>
    <li>Explicando o exemplo: -m é um comando de atalho que cria de imediato um commit com uma mensagem de commit transmitida. Por padrão, git commit abre o editor de texto configurado no local e solicita que uma mensagem de commit seja escrita. Transmitir a opção -m vai pular a solicitação do editor de texto em favor de uma mensagem integrada.
    </li>
</ul>
<br>
<h2>ATENÇÃO</h2>
<table>
    <td>
        <h3>1 - Só dê o comando de commit em códigos FUNCIONAIS. Se ainda não estiver OK, não use este comando.</h3>        
    </td> 
</table>
<table>
    <td><h3>2 - Os comandos git add e git commit compõem o fluxo de trabalho fundamental do Git. Esses são os dois comandos que cada usuário do Git precisa entender, independentemente do     modelo de colaboração da equipe. Eles são os meios para gravar versões de um projeto no histórico do repositório. Além de git add e git commit, um terceiro comando git push é essencial para um fluxo de trabalho colaborativo completo do Git. </h3>
    </td>
</table>  
<br>
<h3>git fetch:</h3>
O comando git fetch baixa commits, arquivos e referências de um repositório remoto para seu repositório local. Busca (fetching) é o que você faz quando quer ver em que todos estão trabalhando. É semelhante ao svn update, que permite que você veja como a história central tem progredido, mas não obriga a de fato fazer o merge das mudanças em seu repositório. O Git isola o conteúdo buscado de um conteúdo local existente e não tem efeito algum no trabalho local de desenvolvimento. O conteúdo buscado tem de ser explicitamente verificado, usando o comando git checkout . Isso faz com que a busca seja uma forma segura de analisar commits antes de serem integrados ao repositório local.
<br>
<h3>git checkout:</h3>
Em termos Git, um “checkout” é o ato de alternar entre versões diferentes de uma entidade de destino. O comando git checkout opera em três entidades distintas: arquivos, commits e branches. Além da definição de “checkout”, o termo “verificação” costuma ser usado para implicar o ato de executar o comando git checkout.
<br>
Exemplo1: git checkout -b &ltnew-branch&gt
<br>
<ul>
    <li> O exemplo acima cria e verifica o &ltnew branch&gt ao mesmo tempo. A opção -b é uma sinalização de conveniência que diz ao Git para rodar o git branch &ltnew-branch&gt antes de rodar o git checkout &ltnew-branch&gt.
    </li>    
</ul>    
<br>
Exemplo2: git checkout -b &ltnew-branch&gt &ltexisting-branch&gt
</br>
<ul>
    <li>
Por padrão, o git checkout -b vai usar como base para o new-branch o HEAD atual. Outro parâmetro de branch opcional pode ser transmitido para o git checkout. No exemplo acima, &ltexisting-branch&gt é transmitido e, então, o new-branch toma o existing-branch como base em vez do HEAD atual.
    </li>
</ul>    
<br>
<h3>git branch:</h3>
O comando git branch permite criar, listar, renomear e excluir ramificações. Ele não permite que você alterne entre as ramificações ou reúna uma história bifurcada novamente. Por esse motivo, o comando git branch é firmemente integrado com os comandos git checkout e git merge.
Exemplo1:git branch
<ul>
    <li>
Listar todas as ramificações no seu repositório. Isso é sinônimo de git branch --list.
    </li>
</ul>    
<br>
Exemplo2: git branch &ltbranch&gt
<ul>
    <li>
Criar uma nova ramificação chamada &ltbranch&gt. Isso não verifica a nova ramificação.
    </li>
</ul>    
<br>
Exemplo3: git branch -d &ltbranch&gt
<ul>
    <li>
Excluir a ramificação especificada. Esta é uma operação “segura” em que o Git impede que você exclua a ramificação se tiver mudanças não mescladas.
   </li>
</ul>    
<br>
<h3>git rebase:</h3>
Rebase é um dos dois utilitários do Git que se especializam em integrar alterações da ramificação para outra. O outro utilitário de integração de alterações é o git merge. o rebase tem recursos poderosos para reescrever o histórico. Rebasing é o processo de mover ou combinar uma sequência de confirmações para uma nova confirmação base. 
<br>
