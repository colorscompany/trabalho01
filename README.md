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

> O sistema proposto para “Colors Company” conterá as informações acerca dos materiais descartados, lixeiras, usuários cadastrados e dia. Dos Materiais Descartados serão armazenados o nome, tipo, peso(em g) e código. Das Lixeiras serão armazenados o número, cor, material, capacidade(em Kg) e localização. Dos usuários, serão armazenados o nome, matrícula, curso e série. Do dia, serão armazenados a data e a quantidade de lixo gerado. Todos esses atributos se relacionam na tabela Descarta_Material_Usuario_Lixeira_Dia.


### 4.RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>

![Arquivo PDF do Protótipo Balsamiq feito para Colors Company](https://github.com/euceciliabk/trabalho01/blob/master/Colors%20Company%202%20-%20PDF.pdf?raw=true "Colors Company")

#### 4.1 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
    a) O sistema proposto poderá fornecer quais tipos de relatórios e informações? 
    b) Crie uma lista com os 5 principais relatórios que poderão ser obtidos por meio do sistema proposto!
    
> A Colors Company precisa inicialmente dos seguintes relatórios:<br>
    • Relatório que informe qual é o tipo de material mais descartado (papel, plástico, vidro, metal, resíduos perigosos, hospitalar ou orgânico);<br>
    • Relatório que informe a quantidade de lixo (em Kg) descartado em um determinado período de tempo;<br>
    • Relatório que informe se um usuário descartou o lixo corretamente;<br>
    • Relatório que informe qual campi produz a maior quantidade de lixo em um determinado período de tempo;<br>
    • Relatório que informe a frequência em que cada tipo de lixo foi descartado (EX.: lixo do tipo plástico foi o mais descartado);<br>

#### 4.2 TABELA DE DADOS DO SISTEMA:
    
(https://github.com/colorscompany/trabalho01/blob/master/Tabela_ColorsCompanyMOD.ods?raw=true "Tabela - Colors Company")


### 5.MODELO CONCEITUAL<br>

![Alt text](https://github.com/colorscompany/trabalho01/blob/master/conceitual.PNG?raw=true "Modelo Conceitual")


   
#### 5.1 Validação do Modelo Conceitual
    [Grupo01]: Caio Lessa e Lucas Tejada
    [Grupo02]: Julia Suzano e Beatriz Auer
    
## Marco de Entrega 05 em: (20/05/2019)<br>

#### 5.2 DESCRIÇÃO DOS DADOS 

    USUÁRIO: Tabela que armazena as informações relativas ao Usuário
     NOME: campo que armazena o nome de cada usuário.
     MATRÍCULA: campo que armazena a matrícula de cada usuário, identificando-o.
     SÉRIE: campo que armazena a série em que os usuários que são alunos se encontram.
     
    CURSO: Tabela que armazena informações relativas ao Curso.
     CODIGO: campo que armazena um determinado codigo do curso, identificando-o.
     NOME_CURSO: campo que armazena o nome de um curso.
     
    MATERIAL: Tabela que armazena as informações relativas aos materiais descartados.
     CODIGO: campo que armazena o código de um material, identificando-o.
     PESO: campo que armazena o peso de cada material descartado em gramas.
    
    TIPO_MATERIAL: Tabela que armazena as informações relativas aos tipos de materiais descartados.
     CODIGO: campo que armazena o código de um tipo, identificando-o.
     NOME_TIPO: campo que armazena o nome de um tipo de um material(Ex: plástico).
     
    LIXEIRA:Tabela que armazena as informações relativas às Lixeiras
     COR: campo que armazena a cor de cada lixeira.
     NÚMERO: campo que armazana o número de cada lixeira, identificando-a.
     CAPACIDADE: campo que armazena a capacidade de cada lixeira em litros.
     
    LOCALIZAÇÃO: Tabela que armazena a localização.
     CAMPUS: campo que armazena em qual campus a lixeira se localiza.
     COORDENADAS: campo que armazena as coordenadas geográficas de uma lixeira. 
     BLOCO: campo que armazena o bloco em que a lixeira se localiza.
    
    DESCARTA: Tabela que armazena as informações de descarte dos materiais em uma lixeira, em uma data, por um usuário;
     DATA: campo que armazena a data de descarte.

## Marco de Entrega 06 em: (22/05/2019)<br>

### 6	MODELO LÓGICO<br>
![Alt text](https://github.com/colorscompany/trabalho01/blob/master/logicocertomsm.PNG?raw=true "Modelo Conceitual")
 

### 7	MODELO FÍSICO<br>

        
C/* logicocerto: */

CREATE TABLE Usuário (
    nome VARCHAR,
    matricula INTEGER PRIMARY KEY,
    serie VARCHAR
);

CREATE TABLE Curso (
    codigo INTEGER PRIMARY KEY,
    nome_curso VARCHAR
);

CREATE TABLE Material (
    codigo INTEGER PRIMARY KEY,
    peso FLOAT
);

CREATE TABLE Lixeira (
    numero INTEGER PRIMARY KEY,
    cor VARCHAR,
    capacidade FLOAT
);

CREATE TABLE Localização (
    campus VARCHAR,
    coordenada VARCHAR PRIMARY KEY,
    bloco INTEGER
);

CREATE TABLE Tipo_material (
    codigo INTEGER PRIMARY KEY,
    nome_tipo VARCHAR
);

CREATE TABLE Descarte (
    fk_Material_codigo INTEGER,
    fk_Lixeira_numero INTEGER,
    fk_Usuário_matricula INTEGER
);

CREATE TABLE Usuario_curso (
    fk_Usuário_matricula INTEGER,
    fk_Curso_codigo INTEGER
);

CREATE TABLE Material_tipo (
    fk_Tipo_material_codigo INTEGER,
    fk_Material_codigo INTEGER
);

CREATE TABLE Lixeira_Localização (
    fk_Lixeira_numero INTEGER,
    fk_Localização_coordenada VARCHAR
);
 
ALTER TABLE Descarte ADD CONSTRAINT FK_Descarte_1
    FOREIGN KEY (fk_Material_codigo)
    REFERENCES Material (codigo)
    ON DELETE NO ACTION;
 
ALTER TABLE Descarte ADD CONSTRAINT FK_Descarte_2
    FOREIGN KEY (fk_Lixeira_numero)
    REFERENCES Lixeira (numero)
    ON DELETE NO ACTION;
 
ALTER TABLE Descarte ADD CONSTRAINT FK_Descarte_3
    FOREIGN KEY (fk_Usuário_matricula)
    REFERENCES Usuário (matricula)
    ON DELETE NO ACTION;
 
ALTER TABLE Usuario_curso ADD CONSTRAINT FK_Usuario_curso_1
    FOREIGN KEY (fk_Usuário_matricula)
    REFERENCES Usuário (matricula)
    ON DELETE SET NULL;
 
ALTER TABLE Usuario_curso ADD CONSTRAINT FK_Usuario_curso_2
    FOREIGN KEY (fk_Curso_codigo)
    REFERENCES Curso (codigo)
    ON DELETE SET NULL;
 
ALTER TABLE Material_tipo ADD CONSTRAINT FK_Material_tipo_1
    FOREIGN KEY (fk_Tipo_material_codigo)
    REFERENCES Tipo_material (codigo)
    ON DELETE RESTRICT;
 
ALTER TABLE Material_tipo ADD CONSTRAINT FK_Material_tipo_2
    FOREIGN KEY (fk_Material_codigo)
    REFERENCES Material (codigo)
    ON DELETE SET NULL;
 
ALTER TABLE Lixeira_Localização ADD CONSTRAINT FK_Lixeira_Localização_1
    FOREIGN KEY (fk_Lixeira_numero)
    REFERENCES Lixeira (numero)
    ON DELETE SET NULL;
 
ALTER TABLE Lixeira_Localização ADD CONSTRAINT FK_Lixeira_Localização_2
    FOREIGN KEY (fk_Localização_coordenada)
    REFERENCES Localização (coordenada)
    ON DELETE SET NULL;

## Marco de Entrega 07 em: (27/05/2019)<br>

### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
insert into usurio (nome, matricula, serie) values <br>
('Atlas', 201810304, '2'),<br>
('Min', 201610307, '4'),<br>
('Pedro', 201818687, '2'),<br>
('Yoongi', 201713312, '3'),<br>
('Momo', 201817477, '2'),<br>
('Mina', 201915252, '1'),<br>
('Sana', 201910308, '1'),<br>
('Eden', 201816700, '2'),<br>
('Dagny', 201710090, '3'),<br>
('Tessa', 201611123, '4');<br>

insert into curso (codigo, nome_curso) values<br> 
(1, 'Informatica'),<br>
(2, 'Mecatronica'),<br>
(3, 'Automacao Industrial');<br>

INSERT INTO LIXEIRA (COR, NUMERO, MATERIAL, CAPACIDADE, LOCALIZACAO) VALUES<br> 
('Vermelho', 4, 'Plástico', 50, 'Campus Serra'),<br>
('Azul', 23, 'Papel', 40, 'Campus Vitória'),<br>
('Amarelo', 289, 'Metal', 100, 'Campus Cariacica'),<br>
('Marrom', 33, 'Orgânico', 50, 'Campus Nova Venécia'),<br>
('Azul', 44, 'Papel', 200, 'Campus Aracruz'),<br>
('Vermelho', 122, 'Plástico', 150, 'Campus Montanha'),<br>
('Verde', 28, 'Vidro', 100, 'Campus Santa Teresa'),<br>
('Vermelho', 3, 'Plástico', 40, 'Campus Vila Velha'),<br>
('Amarelo', 90, 'Metal', 150, 'Campus Itapina'),<br>
('Marrom', 30, 'Orgânico', 50, 'Campus Guarapari');<br>

INSERT INTO DIA (QTD_LIXO, DATA) VALUES<br> 
(3, '2019/10/20'),<br>
(7, '2019/06/25'),<br>
(1, '2019/09/01'),<br>
(3, '2019/02/03'),<br>
(10, '2019/07/24'),<br>
(7, '2019/07/25'),<br>
(8, '2019/09/10'),<br>
(10, '2019/06/24'),<br>
(4, '2019/05/30'),<br>
(1, '2019/07/03');<br>

#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELA E INSERÇÃO DOS DADOS
        
CREATE TABLE Usuario ( nome VARCHAR(23), matricula VARCHAR(14) PRIMARY KEY, serie VARCHAR(5), curso VARCHAR(50));<br>

CREATE TABLE Material ( nome VARCHAR(23), tipo VARCHAR(10), peso FLOAT, codigo INTEGER PRIMARY KEY );<br>

CREATE TABLE Lixeira ( cor VARCHAR(15), numero INTEGER PRIMARY KEY, material VARCHAR(23), capacidade FLOAT, localizacao VARCHAR(20) );<br>

CREATE TABLE Dia ( qtd_lixo FLOAT, data DATE PRIMARY KEY );<br>

CREATE TABLE Descarta_Material_Usuario_Lixeira_Dia ( fk_Material_codigo INTEGER, fk_Usuario_matricula VARCHAR, fk_Lixeira_numero INTEGER, fk_Dia_data DATE );<br>

INSERT INTO USUARIO (NOME, MATRICULA, SERIE, CURSO) VALUES<br>
('Ariana Grande', '20181tiimi8373', '2', 'Informática'),<br>
('Im Na Yeon', '20161tiimi8788', '4', 'Informática'),<br>
('Kim Taehyung', '2019prof8888', NULL, NULL),<br>
('Park Jimin', '2014bsi6666', '3', 'Sistema de Informações'),<br>
('Min Yoongi', '2017tiimi1212', '1', 'Informática'),<br>
('Jung Hoseok', '20191tiimi7787', '3', 'Informática'),<br>
('Jeon Jungkook', '20161prof5657', NULL, NULL),<br>
('Kim Seokjin', '20181bsi3526', '2', 'Sistema de Informações'),<br>
('Kim Namjoon', '20191tiimi3677', '1', 'Informática'),<br>
('Hirai Momo', '20181bsi4646', '1', 'Sistema de Informações');<br>

INSERT INTO MATERIAL (NOME, TIPO, PESO, CODIGO) VALUES<br>
('Garrafa Pet', 'Plástico', 50, 123),<br>
('Guardanapo', 'Papel', 5, 222),<br>
('Lata de Refri', 'Metal', 14.5, 628),<br>
('Casca de Banana', 'Orgânico', 80, 782),<br>
('Folha de Prova', 'Papel', 5, 235),<br>
('Canudo', 'Plástico', 9, 234),<br>
('Garrafa de Vidro', 'Vidro', 400, 682),<br>
('Papel de Bala', 'Plástico', 9, 908),<br>
('Lata de Refri', 'Metal', 50, 627),<br>
('Casca de Tangerina', 'Orgânico', 80, 187);<br>

INSERT INTO LIXEIRA (COR, NUMERO, MATERIAL, CAPACIDADE, LOCALIZACAO) VALUES<br> 
('Vermelho', 4, 'Plástico', 50, 'Campus Serra'),<br>
('Azul', 23, 'Papel', 40, 'Campus Vitória'),<br>
('Amarelo', 289, 'Metal', 100, 'Campus Cariacica'),<br>
('Marrom', 33, 'Orgânico', 50, 'Campus Nova Venécia'),<br>
('Azul', 44, 'Papel', 200, 'Campus Aracruz'),<br>
('Vermelho', 122, 'Plástico', 150, 'Campus Montanha'),<br>
('Verde', 28, 'Vidro', 100, 'Campus Santa Teresa'),<br>
('Vermelho', 3, 'Plástico', 40, 'Campus Vila Velha'),<br>
('Amarelo', 90, 'Metal', 150, 'Campus Itapina'),<br>
('Marrom', 30, 'Orgânico', 50, 'Campus Guarapari');<br>

INSERT INTO DIA (QTD_LIXO, DATA) VALUES
(3, '2019/10/20'),<br>
(7, '2019/06/25'),<br>
(1, '2019/09/01'),<br>
(3, '2019/02/03'),<br>
(10, '2019/07/24'),<br>
(7, '2019/07/25'),<br>
(8, '2019/09/10'),<br>
(10, '2019/06/24'),<br>
(4, '2019/05/30'),<br>
(1, '2019/07/03');<br>

       postgres://wzvtfjcc:dmyeQX...@raja.db.elephantsql.com:5432/wzvtfjcc
       
#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
       
DROP TABLE Usuario;<br>
DROP TABLE Material;<br>
DROP TABLE Lixeira;<br>
DROP TABLE Dia;<br>
DROP TABLE Descarta_Material_Usuario_Lixeira_Dia;<br>

CREATE TABLE Usuario ( nome VARCHAR(23), matricula VARCHAR(14) PRIMARY KEY, serie VARCHAR(5), curso VARCHAR(50));<br>

CREATE TABLE Material ( nome VARCHAR(23), tipo VARCHAR(10), peso FLOAT, codigo INTEGER PRIMARY KEY );<br>

CREATE TABLE Lixeira ( cor VARCHAR(15), numero INTEGER PRIMARY KEY, material VARCHAR(23), capacidade FLOAT, localizacao VARCHAR(20) );<br>

CREATE TABLE Dia ( qtd_lixo FLOAT, data DATE PRIMARY KEY );<br>

CREATE TABLE Descarta_Material_Usuario_Lixeira_Dia ( fk_Material_codigo INTEGER, fk_Usuario_matricula VARCHAR, fk_Lixeira_numero INTEGER, fk_Dia_data DATE );<br>

INSERT INTO USUARIO (NOME, MATRICULA, SERIE, CURSO) VALUES<br>
('Ariana Grande', '20181tiimi8373', '2', 'Informática'),<br>
('Im Na Yeon', '20161tiimi8788', '4', 'Informática'),<br>
('Kim Taehyung', '2019prof8888', NULL, NULL),<br>
('Park Jimin', '2014bsi6666', '3', 'Sistema de Informações'),<br>
('Min Yoongi', '2017tiimi1212', '1', 'Informática'),<br>
('Jung Hoseok', '20191tiimi7787', '3', 'Informática'),<br>
('Jeon Jungkook', '20161prof5657', NULL, NULL),<br>
('Kim Seokjin', '20181bsi3526', '2', 'Sistema de Informações'),<br>
('Kim Namjoon', '20191tiimi3677', '1', 'Informática'),<br>
('Hirai Momo', '20181bsi4646', '1', 'Sistema de Informações');<br>

INSERT INTO MATERIAL (NOME, TIPO, PESO, CODIGO) VALUES<br>
('Garrafa Pet', 'Plástico', 50, 123),<br>
('Guardanapo', 'Papel', 5, 222),<br>
('Lata de Refri', 'Metal', 14.5, 628),<br>
('Casca de Banana', 'Orgânico', 80, 782),<br>
('Folha de Prova', 'Papel', 5, 235),<br>
('Canudo', 'Plástico', 9, 234),<br>
('Garrafa de Vidro', 'Vidro', 400, 682),<br>
('Papel de Bala', 'Plástico', 9, 908),<br>
('Lata de Refri', 'Metal', 50, 627),<br>
('Casca de Tangerina', 'Orgânico', 80, 187);<br>

INSERT INTO LIXEIRA (COR, NUMERO, MATERIAL, CAPACIDADE, LOCALIZACAO) VALUES<br> 
('Vermelho', 4, 'Plástico', 50, 'Campus Serra'),<br>
('Azul', 23, 'Papel', 40, 'Campus Vitória'),<br>
('Amarelo', 289, 'Metal', 100, 'Campus Cariacica'),<br>
('Marrom', 33, 'Orgânico', 50, 'Campus Nova Venécia'),<br>
('Azul', 44, 'Papel', 200, 'Campus Aracruz'),<br>
('Vermelho', 122, 'Plástico', 150, 'Campus Montanha'),<br>
('Verde', 28, 'Vidro', 100, 'Campus Santa Teresa'),<br>
('Vermelho', 3, 'Plástico', 40, 'Campus Vila Velha'),<br>
('Amarelo', 90, 'Metal', 150, 'Campus Itapina'),<br>
('Marrom', 30, 'Orgânico', 50, 'Campus Guarapari');<br>

INSERT INTO DIA (QTD_LIXO, DATA) VALUES<br>
(3, '2019/10/20'),<br>
(7, '2019/06/25'),<br>
(1, '2019/09/01'),<br>
(3, '2019/02/03'),<br>
(10, '2019/07/24'),<br>
(7, '2019/07/25'),<br>
(8, '2019/09/10'),<br>
(10, '2019/06/24'),<br>
(4, '2019/05/30'),<br>
(1, '2019/07/03');<br>

https://api.elephantsql.com/console/b0576abf-5bf5-4d35-a6b0-071283f4356f/browser?

## Marco de Entrega 08 em: (29/05/2019)<br>

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>

![Alt text](https://github.com/colorscompany/trabalho01/blob/master/1.PNG?raw=true "Tabela1")<br>

![Alt text](https://github.com/colorscompany/trabalho01/blob/master/2.PNG?raw=true "Tabela2")<br>

![Alt text](https://github.com/colorscompany/trabalho01/blob/master/3.PNG?raw=true "Tabela3")<br>

![Alt text](https://github.com/colorscompany/trabalho01/blob/master/4.PNG?raw=true "Tabela4")<br>

![Alt text](https://github.com/colorscompany/trabalho01/blob/master/6.PNG?raw=true "Tabela5")<br>



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


        
        


    





