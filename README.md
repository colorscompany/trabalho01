# TRABALHO 01:  Colors Company

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo<br>
Cecília Bastazini Kröebel:cecilia.bastazini.k@gmail.com<br>
Pedro Henrique de Carvalho:ordepesnyc@gmail.com<br>
...

### 2.INTRODUÇÃO E MOTIVAÇAO<br>
Este documento contém a especificação do projeto do banco de dados Colors Company
<br>e motivação da escolha realizada. <br>

> A "Colors Company" visa colaborar com desenvolvimento de projetos para uma sociedade mais consciente e cuidadosa com o meio-ambiente. Sabendo-se da necessidade da separação do lixo corretamente, para que assim, os processos que envolvem reciclagem possam ser realizados da melhor forma possível, e visando reunir as informações relativas a tipo, nome e material do produto, e nome, tipo, localização e capacidade das lixeiras em um mesmo local, ficamos motivados com o desenvolvimento deste sistema. O Sistema "Colors Company" tem como objetivo gerenciar todas as informações para que um conjunto de lixeiras da coleta seletiva localizadas nos campi do Ifes, seja capaz de informar ao usuário em qual lixeira deve depositar o material que deseja descartar. Para realizar suas operações adequadamente a empresa necessita que o sistema armazene informações relativas aos materiais que serão descartados, lixeiras e usuários.
 

### 3.MINI-MUNDO Novo<br>

> O sistema proposto para “Colors Company” conterá as informações acerca dos materiais descartados, lixeiras, usuários cadastrados e dia. Dos Materiais Descartados serão armazenados o nome, tipo, peso(em g) e código. Das Lixeiras serão armazenados o número, cor, material, capacidade(em Kg) e localização. Dos usuários, serão armazenados o nome, matrícula, curso e série. Do dia, serão armazenados a data e a quantidade de lixo gerado. 


### 4.RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>

![Arquivo PDF do Protótipo Balsamiq feito para Colors Company](https://github.com/euceciliabk/trabalho01/blob/master/Colors%20Company%202%20-%20PDF.pdf?raw=true "Colors Company")

#### 4.1 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
    a) O sistema proposto poderá fornecer quais tipos de relatórios e informaçes? 
    b) Crie uma lista com os 5 principais relatórios que poderão ser obtidos por meio do sistema proposto!
    
> A Colors Company precisa inicialmente dos seguintes relatórios:<br>
    • Relatório que informe quais são os usuários de cada campus incluindo as seguintes informações: nome do usuário, matrícula, período/série e curso;<br>
    • Relatório de materiais para descarte incluindo as seguintes informações: Nome do material, Código do material, Tipo do material, Peso do material;<br>
    • Relatório de lixeiras, incluindo as seguintes informações: Cor, Número, Material, Capacidade(em Litros) e localização;<br>
    • Relatório do dia em cada campus, incluindo as seguintes informações:  Data e quantidade de lixo gerado em quilos;<br>

#### 4.2 TABELA DE DADOS DO SISTEMA:
    
(https://github.com/colorscompany/trabalho01/blob/master/Tabela_ColorsCompanyATUALIZADA.ods?raw=true "Tabela - Colors Company")

### 5.MODELO CONCEITUAL<br>
        
![Alt text](https://github.com/colorscompany/trabalho01/blob/master/ConceitualATT.PNG?raw=true "Modelo Conceitual")
   
#### 5.1 Validação do Modelo Conceitual
    [Grupo01]: Cecília Bastazini e Pedro Henrique
    
## Marco de Entrega 05 em: (20/05/2019)<br>

#### 5.2 DESCRIÇÃO DOS DADOS 

    USUÁRIO: Tabela que armazena as informações relativas ao Usuário<br>
     NOME: campo que armazena o nome de cada usuário.<br>
     MATRÍCULA: campo que armazena a matrícula de cada usuário, tanto professores, como alunos.<br>
     SÉRIE: campo que armazena a série em que os usuários que são alunos se encontram.<br>
     CURSO: campo que armazena o curso que os usuários que são alunos estão matriculados.<br>
     
    MATERIAL: Tabela que armazena as informações relativas aos materiais descartados.<br>
     NOME: campo que armazena o nome de cada material descartado.<br>
     TIPO: campo que armazena o tipo do material descartado, este pode ser: papel, plástico, vidro, metal ou orgânico.<br>
     PESO: campo que armazena o peso de cada material descartado em gramas.<br>
    
    LIXEIRA:Tabela que armazena as informações relativas às Lixeiras<br>
     COR: campo que armazena a cor de cada lixeira.<br>
     NÚMERO: campo que armazana o número de cada lixeira.<br>
     MATERIAL: campo que armazena o tipo de material que pode ser descartado em cada lixeira.<br>
     CAPACIDADE: campo que armazena a capacidade de cada lixeira em litros.<br>
     LOCALIZAÇÃO: campo que armazena a localização, ou seja, em qual campus do Ifes cada lixeira se encontra.<br>
     
    DIA: Tabela que armazena a data atual e a quantidade de lixo que foi gerado nesse dia.<br>
     DATA: campo que armazena o dia, o mês e o ano atuais.<br>
     QUANTIDADE DE LIXO: campo que armazena a quantidade de lixo gerado em um dia em gramas.<br>

## Marco de Entrega 06 em: (22/05/2019)<br>

### 6	MODELO LÓGICO<br>
        a) inclusão do modelo lógico do banco de dados
        b) verificação de correspondencia com o modelo conceitual 
        (não serão aceitos modelos que não estejam em conformidade)

### 7	MODELO FÍSICO<br>
        a) inclusão das instruções de criacão das estruturas DDL 
        (criação de tabelas, alterações, etc..)          

## Marco de Entrega 07 em: (27/05/2019)<br>

### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
        a) inclusão das instruções de inserção dos dados nas tabelas criadas pelo script de modelo físic
        b) formato .SQL

#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELA E INSERÇÃO DOS DADOS
        a) Junção dos scripts anteriores em um único script 
        (create para tabelas e estruturas de dados + dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        c) formato .SQL
#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
        a) Junção dos scripts anteriores em um único script 
        (Drop table + Create de tabelas e estruturas de dados + dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        c) formato .SQL

## Marco de Entrega 08 em: (29/05/2019)<br>

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas
#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.


    
#### 9.5	ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>


#### 9.6	CONSULTAS COM JUNÇÃO E ORDENAÇÃO (Mínimo 6)<br>
        a) Uma junção que envolva todas as tabelas possuindo no mínimo 3 registros no resultado
        b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho
        

### ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO SEMESTRAL (Mínimo 6 e Máximo 10)<br>


#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>

#### 9.8	CONSULTAS COM LEFT E RIGHT JOIN (Mínimo 4)<br>
#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho
#### 9.10	SUBCONSULTAS (Mínimo 3)<br>

#### 9.11	LISTA DE CODIGOS DAS FUNÇÕES E TRIGGERS<br>
        Detalhamento sobre funcionalidade de cada código.
        a) Objetivo
        b) Código do objeto (função/trigger)
        c) exemplo de dados para aplicação
        d) resultados em forma de tabela/imagem
<br>


#### 9.12	GERACAO DE DADOS (MÍNIMO DE 100 MIL REGISTROS PARA PRINCIPAL RELAÇAO)<br>
        a) principal tabela do sistema deve ter no mínimo 100 mil registros
        b) tabelas diretamente relacionadas a tabela principal 10 mil registros
        c) tabelas auxiliares de relacao multivalorada mínimo de 10 registros
        d) registrar o tempo de inserção em cada uma das tabelas do banco de dados
        e) especificar a quantidade de registros inseridos em cada tabela
        Para melhor compreensão verifiquem o exemplo na base de testes:<br>
        https://github.com/discipbd2/base-de-testes-locadora
        

#### 9.13	Backup do Banco de Dados<br>
        Detalhamento do backup.
        a) Tempo
        b) Tamanho
        c) Teste de restauração (backup)
        d) Tempo para restauração
        e) Teste de restauração (script sql)
        f) Tempo para restauração (script sql)
<br>

Data de Entrega: (Data a ser definida)
<br>

#### 9.14	APLICAÇAO DE ÍNDICES E TESTES DE PERFORMANCE<br>
    a) Lista de índices, tipos de índices com explicação de porque foram implementados nas consultas 
    b) Performance esperada VS Resultados obtidos
    c) Tabela de resultados comparando velocidades antes e depois da aplicação dos índices (constando velocidade esperada com planejamento, sem indice e com índice Vs velocidade de execucao real com índice e sem índice).
    d) Escolher as consultas mais complexas para serem analisadas (consultas com menos de 2 joins não serão aceitas)
    e) As imagens do Explain devem ser inclusas no trabalho, bem como explicações sobre os resultados obtidos.
    f) Inclusão de tabela mostrando as 10 execuções, excluindo-se o maior e menor tempos para cada consulta e 
    obtendo-se a media dos outros valores como resultado médio final.
<br>
    Data de Entrega: (Data a ser definida)
<br>   

### 10	ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO FINAL (Mínimo 6 e Máximo 10)<br>
<br>
    Data de Entrega: (Data a ser definida)
<br>

### 11 Backup completo do banco de dados postgres 
    a) deve ser realizado no formato "backup" 
        (Em Dump Options #1 Habilitar opções Don't Save Owner e Privilege)
    b) antes de postar o arquivo no git o mesmo deve ser testado/restaurado por outro grupo de alunos/dupla
    c) informar aqui o grupo de alunos/dupla que realizou o teste.

    
### 12	TUTORIAL COMPLETO DE PASSOS PARA RESTAURACAO DO BANCO E EXECUCAO DE PROCEDIMENTOS ENVOLVIDOS NO TRABALHO PARA OBTENÇÃO DOS RESULTADOS<br>
        a) Outros grupos deverão ser capazes de restaurar o banco 
        b) executar todas as consultas presentes no trabalho
        c) executar códigos que tenham sido construídos para o trabalho 
        d) realizar qualquer procedimento executado pelo grupo que desenvolveu o trabalho

### 13	DIFICULDADES ENCONTRADAS PELO GRUPO<br>  

    
Data de Entrega final: (Data a ser definida)
<br>

       
### 14  FORMATACAO NO GIT: https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
   
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/

#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. Caso existam arquivos com conteúdos sigilosos, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário deste GIT, para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://sis4.com/brModelo/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


        
        


    





