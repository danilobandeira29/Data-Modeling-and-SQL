# 📝 Sobre
- Anotações que faço ao longo dos estudos sobre Modelagem de Dados e SQL.

# 🏆 Desafio
- Anotar de forma resumida e colocar em prática os conhecimentos que são adquiridos diariamente nos meus estudos sobre Modelagem de Dados e SQL.

# Modelagem de Dados
## O que são Dados?
- São Fatos em sua forma primitiva.
- Podem ser armazenados em algum meio.
- Sozinho não possuí significado algum.
> Exemplos:
> - CPF
> - Nome
> - 29/10/1993


## O que é Informação?
- Conjunto de Dados organizados que juntos possuem um significado.
- São Dados em um contexto.
> Exemplo:
> - Lista de nomes dos clientes com seus CPFs nascidos em 29/10/1993, ordenados.

## O que é Banco de Dados?
- Conjunto organizado de Dados.
- Os Dados são organizados de tal maneira que é possível extrair informação de acordo com a necessidade.
- Modela aspectos do mundo real para que seja possível analisar e extrair informações relevantes.

## O que são Metadados?
- São Dados sobre os Dados.
- Permite identificar e representar os Dados, gerando assim consistência e persistência.
- São mantidos em um Dicionário de Dados(ou Catálogo de Dados).

## Um Banco de dados é composto por:
- Tabelas
- Relacionamentos
- Atributos
- Triggers
- Esquemas
- Visões...
Entre outros.

## Sistema de Gerenciamento de Banco de Dados(SGBD)
- Conjunto de Softwares responsável por manipular o Banco de Dados.
- Protege e mantém o Banco de Dados ao longo do tempo.
> Exemplos de SGBD:
> - MySQL
> - PostgreSQL
> - MongoDB
> - SQLite... Entre outros.

### O banco de dados são apenas arquivos que são manipulados com a ajuda de um sistema de gerenciamento de banco de dados.

### Sistema de Banco de Dados
Usuário -> Utiliza uma interface(frontend) para -> Se comunicar com o backend/SGBD que se comunica com -> Banco de dados/Metadados

## Usuários de um Banco de Dados
- Administrador
- Projetista/Desenvolvedor
- Usuário final

## Características e Funcionalidades
- Controle de Redundância
  - evita que os dados sejam guardados de maneira repetida no banco.
- Múltiplas Visões
  - maneiras distintas de exibir informações.
- Controle de Concorrência
  - evita que um dado seja manipulado ao mesmo tempo por pessoas diferentes, evitando assim conflito.
- Backup e Restauração
- Autenticação e Autorização de Dados
  - somente pessoas autorizadas tenham acesso aos dados.
- Restrição Integridade
  - onde eu possa cadastrar um novo funcionário se ele informar todos os campos pedidos no formulário de cadastro.

## Modelos de Banco de Dados
- Hierárquico
- Em Rede
- **Modelo Relacional**
- Orientado à objetos
- Não-Relacional
### Modelo Relacional
- Os dados são separados por **Entidade/Tabelas**.
- As **Entidades/Tabelas** possuem os **Atributos** que as descrevem/qualificam.
- As **Entidades** se relacionam entre si por meio de uma associção nomeada conhecida como **Relacionamento**.
- Com o **Relacionamento** entre as **Entidades**, é possível recuperar os dados e assim gerar a informação necessária.

## Modelagem de Dados
- Modelo
  - permite o projetista a comunicar suas idéias que estão em sua mente.
  - usado para comunicar, analisar, descrever idéias.

## Para que serve a Modelagem de Dados?
- É um processo realizado para que seja possível fazer a criação de um Modelo de Dados, fazendo uso de técnicas espeficas de modelagem de dados.
- Serve para **analisar** e **definir** os processos que são suportados de acordo com as **regras de negócio**.
- **Processo importante, pois irá evitar possíveis erros na hora de implementação do Banco de Dados**.

# Modelo Relacional
- Dados são organizados e armazenados em **tabelas bidimensionais**, formadas por **linhas e colunas**.

# Banco de Dados Relacional
- Coleção de tabelas bidimensionais que armazenam dados.

## Componentes de um Banco de Dados(BD) Relacional
### Tabelas
- Estrutura básica do BD.
- Representa algo do mundo real, podendo ter existencia física ou abstrata.
- Utilizada para armazenar os dados.
### Tupla/Linha/Registro
- Representa os dados de uma determinada ocorrência do BD.
- Cada linha contém uma **Chave Primária**(Primary Key, PK) que a **identifica de forma única e exclusiva** no BD.
### Coluna
- Representa um tipo específico de dado. Ou pode não armazenar nada, sendo assim, nulo(null).
### Relacionamento
- **Associação nomeada entre as entidades/tabelas** conectadas por **Chave Primária** e **Chave Estrangeira**.

# Análise de Requisitos
- Nessa parte são realizadas reuniões com o Cliente para saber **o que será necessário armazenar no BD** e **o que não será necessário**.
- Neste processo, será possível observar as **entidades**, **atributos** e **relacionamentos**, mas estes poderão mudar ao longo do processo.

# Modelo Entidade Relacionamento(MER)
- Será gerado uma lista com as **entidades**, **atributos** e **relacionamentos** a partir da **Análise de Requisitos**.
- Traz informações sobre os **tipos de dados**, **descrições de entidades**, **restrições**, entre outros.
- A partir do MER, será possível gerar o **Diagrama Entidade Relacionamento(DER)**, que é a representação gráfica do **MER**.

## Componentes do MER
- **Entidades**
  - algo do mundo real que o banco deve guardar dados.
  - pode ser uma idéia, regra de negócio, ou seja, pode ser abstrato ou ter existência física.
  - cada ocorrência da entidade é chamado instância da entidade ou objeto(possível observar na Imagem 1 abaixo).
  > Exemplo: Cliente.

- **Atributos**
  - qualifica e descreve a **entidade**.
  > Exemplo: De Cliente, necessita-se guardar no BD Nome, CPF e Telefone. Logo, Nome, CPF e Telefone são atributos da entidade Usuário.
  <p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/DER_XjUjKj2EU.png" alt="Representação de uma Entidade, Atributos e uma instância de Entidade"/>
    
  </p>
  <p align="center">Representação de uma Entidade, Atributos e uma instância de Entidade</p>


**Relacionamentos**
  - Associação nomeada entre duas ou mais entidades, com um grau de associação(será falado mais futuramente).
  > Exemplo:
  > O BD possuí as entidades Cliente e Produto.
  > De acordo com a regra de negócio, um cliente pode comprar **apenas um** Produto.
  > O relacionamento entre Cliente e Produto é nomeado de **Compra**

# Diagrama Entidade Relacionamento(DER)
- Representação gráfica do **MER**.
- Existem várias notações para representar um **DER**, como: **Peter Chen**, **Pé de galinha(crows foot)**, **Min-Max**, **UML**, entre outros. Iremos adotar a notação de **Peter Chen**.
- A notação de **Peter Chen** é composto por:
  - Retângulos, que representam as **Entidades**.
  - Elipses, que representam os **Atributos**.
  - Losangos, que representa os **Relacionamentos**.
  - Linhas, que ligam os **atributos** as **entidades**, e as **entidades** aos **relacionamentos**.
> Exemplo:
> - O BD possuí as entidades Cliente e Produto.
> - De acordo com a regra de negócio, um cliente pode comprar **apenas um** Produto.
> - O relacionamento entre Cliente e Produto é nomeado de **Compra**
<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Diagrama_Entidade_Relacionamento_MAxsoRRXx.png" 
  alt="Diagrama Entidade Relacionamento"
  />
</p>
<p align="center">Diagrama Entidade Relacionamento</p>

## Níveis de Modelagem de Dados
- Modelo Conceitual.
- Modelo Lógico.
- Modelo Físico.

### Modelo Conceitual
- Mais próximo da abstração.
- De maneira simplificada, analisamos os dados e seus relacionamentos. Assim, poderemos determinar o que será armazanado no BD.
> Exemplo:
> - Cadastrar produtos de uma loja. Quais os dados necessários?
>   - Nome do produto
>   - Categoria do produto (higiene, alimentação)
>   - Código do fornecedor
>   - Quantidade... entre outros.

- Os detalhes de implementação ainda não aparece.
- Nessa etapa, ainda é independente do SGBD.
- Mas possuí detalhes suficientes para que seja possível identificar os dados requiridos, relacionamentos e tabelas.
### Modelo Lógico
- Nessa etapa, os dados são completamente definidos.
- A partir daqui, irá ser possível gerar o **Diagrama Entidade Relacionamento(DER)**.
### Modelo Físico
- Onde será detalhado as **entidades**, **campos**, **tipos de valores**, **restrições**, etc.
- Após esse detalhamento, podemos partir para a implentação do Banco de Dados com o SGBD mais adequado.
### Arquitetura de três níveis
Modelo Conceitual(idéias, bem abstrado) ->
Modelo Lógico(podendo ser representado em forma de diagrama) -> Modelo Físico(bem detalhado, onde será possível partir para a implementação do BD).


## Esquema de Banco de Dados
- É a definição do Banco de Dados espeficiada durante o projeto, armazenado no Dicionário de Dados.
- Mostra como o Banco de Dados é construído.
- Define **tabelas**, **campos**, **relacionamentos**, **atributos**, **visões**, **funções** e **muitos outros elementos** que compõe o BD.

## Etapas do Desenvolvimento de um BD
1. Especificação e Análise de requisitos.
2. Projeto Conceitual
    - baseado nos requisitos.

3. Projeto Lógico
    - expresso em um modelo de dados, como o relacional.

4. Projeto Físico
    - especificações para armazenar e acessar o BD

## Tarefas para Modelagem
- Identificar Entidades.
- Identificar Atributos.
- Identificar Relacionamentos.
- Criar e Associar Chaves.
- Normalizar para reduzir redundância e anomalias de atualização.
- Desnormalizar para aumentar performance.

## Tipos de Atributos
- Simples/Atômico.
- Composto.
- Multivalorado.
- Determinante.
- Identificador... entre outros.

### Atributo Simples/Atômico
- Não possuí características especiais e são indivisiveis.
> Exemplos: CPF, Nome_Empresta, CNPJ, Sexo.

### Atributos Composto
- É formado por atributos menores
- É divisivel
> Exemplo: Endereço que pode ser dividido em Rua, Número, CEP...

### Atributo Multivalorado
- Pode ter mais de um valor para o mesmo registro
> Exemplo: Telefone

### Atributo Determinante/Identificador único
- Identifica de forma **única** as instâncias da entidade.
- **Não** pode possuir duas ou mais instâncias com o mesmo valor neste atributo.
> Exemplo: CPF, CPNJ, RA...

### Atributo Identificador(Chaves)
- Identifica uma instância da entidade.
Existem dois tipos de chaves:
  - Única: Chave primária
  - Não-Única: Chave estrangeira
- As chaves podem ser compostas, consistindo em dois ou mais atributos para identificar a instância da entidade.


## Entidade/Relação
- **Entidade** é um conceito do mundo real, como Cliente ou Produto, que eu devo guardar informações sobre.
- **Relação** é um conjunto de registros(tuplas) que representam um modelo de uma entidade.
- Um registro da entidade é chamado de **instância da entidade**, e o conjunto de todas as instâncias é chamado de **Relação**.
- **A entidade da ênfase em como eu quero armazenar, ou quais dados eu quero armazenar de um determinado conceito do mundo real.**
- **Já a relação, da ênfase nas instâncias da entidade**.

## Relação
- Tabela **bidimensional** que contém linhas e colunas, criada a partir de uma **Entidade**.
### Características de uma Relação
- **Linha**: contém uma instância da entidade.
- **Coluna**: contém um atributo.
- Todos os valores em uma **Coluna** são do mesmo tipo.
- Cada **Coluna** possuí nome **único**.
- **Não há duas linhas idênticas**.
- As relações geralmente geram tabelas no Banco.
> Exemplo:

| ID_Produto       | Nome_Produto     | Preço_Produto     |
| :------------- | :----------: | -----------: |
|  1000 | Mouse   | 15,00    |
| 1001   | Teclado | 10,00 | 
| 1002   | Cadeira | 150,00 | 

## Relacionamento
- As **entidades** se conectam entre si por meio de um **Relacionamento**.
- É a associação entre duas ou mais entidades.
- Existem casos que a **entidade** se relaciona com ela mesmo.
### Por que precisamos de um Relacionamento?
- Os dados de diferentes **entidades** são guardados em tabelas distintas, **geralmente precisamos combinar duas ou mais tabelas para satisfazer as consultas do usuário no Banco de Dados**.

## Grau de Relacionamento
- Define o número de entidades que participam de um mesmo relacionamento.
> Exemplo:
> - Unário
> - Binário
> - Ternário, etc.

<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamento_Un_rio_0YDhvTGycz.png" 
  alt="Relacionamento unário"
  />
</p>
<p align="center">Relacionamento unário</p>

<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamento_Bin_rio_Ul1VR9yhW.png" 
  alt="Relacionamento binário"
  />
</p>

<p align="center">Relacionamento binário</p>
<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamento_Tern_rio_tbBuyBmt2s.png" 
  alt="Relacionamento ternário"
  />
</p>
<p align="center">Relacionamento ternário</p>

## Efetuando o Relacionamento entre Múltiplas Tabelas
- O relacionamento entre as tabelas é feita pelo uso de uma **Chave Estrangeira(Foreign Key)**.
- A **Chave Estrangeira** faz referencia a uma **Chave primária** de uma outra tabela.

# Chaves
- Consiste em uma ou mais colunas, utilizas para identificar instâncias da entidade de forma única.
## Única: Primária, Candidata, Composta, Surrogada.
## Não-única: Estrangeira.

### Chave Candidata
- **Uma ou mais colunas com potencial** para se tornarem **chave primária**.
- Caso não seja usada como chave primária, ganha o nome de **Chave Alternativa**.

### Chave Primária/Primary Key(PK)
- **Identifica de forma única as instâncias de entidade**.
- **Possuí valor único**.
- **Não pode ser null**.
- Pode ser mais de uma coluna.

### Chave Estrangeira/Foreign Key(FK)
- Coluna que estabalece uma relação com a **Chave Primária** de outra tabela.
- **É a partir da FK que sabemos com qual registro de uma outra tabela um registro está relacionado**.

### Chave Composta
- Composta de dois ou mais colunas.
- **Utilizada quando não é possível** termos apenas uma coluna servindo de **PK**.

### Chave Surrogada ou Substituta/Surrogate Key
- Valo númerico, **único**.
- Adicionado para servir de **PK** para quando não quisermos utilizar uma **Chave Primária Composta**.
- Não possuí significado para o usuário final, e geralmente é escondida na aplicação.

## Instruções para a Criação de Chaves Primárias e Estrangeiras
- **Não é possível haver valores repetidos em uma chave primária**.
- No geral, não é possível alterar o valor de uma chave primária. E também deve ser evitado, para não gerar conflito com outra chave primária existente.
- Chaves Estrangeiras são baseadas em valores de dados, classificados como **Ponteiros Lógicos**.
- **Uma Chave Estrangeira** deve fazer referencia a um valor de **Chave Primária existente** em outra tabela. **Caso contrário, deverá ter seu valor nulo**.
<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamento_entre_tabelas_XFHGNSLB8.png" 
  alt="Relacionamento entre tabelas"
  />
</p>
<p align="center">Relacionamento entre tabelas</p>


## Conceito de Domínio
Define que tipo de valor é aceito em um atributo.

## Cardinalidade
Grau de relação entre duas entidades ou tabelas.

### Cardinalidade Mínima
**Número de instâncias de entidade que obrigatoriamente devem participar do relacionamento.** **Zero é participação opcional e Um é obrigatório**.

### Cardinalidade Máxima
**Número máximo de instâncias de entidade que podem participar em um relacionamento**.

## Simbologia para Cardinalidade
Duas das simbologias mais utilizadas para expressar a cardinalidade dos Relacionamentos são:
  - **Notação de Peter Chen**: Onde o **primeiro número representa a cardinalidade mínima**, e o **segundo representa a cardinalidade máxima**.
    - Forma de ler: Funcionário trabalha em **um e apenas um** Departamento. Em Departamento trabalha no **mínimo um** funcionário, no **máximo N** funcionários.


  <p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Cardinalidade_Peter_Chen_zizAc5Bqb.png" 
  alt="Notação de Peter Chen(*crows foot*)"
  />
</p>
<p align="center">Notação de Peter Chen</p>


  - **Notação Pé de Galinha(*crows foot*)**

  <p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/crowsfoot_notation_6Ok5BWFOd.gif" 
  alt="Notação Pé de Galinha(*crows foot*)"
  />
</p>
<p align="center">Notação Pé de Galinha(crows foot).</p>

##### Fonte: https://davidneely.files.wordpress.com/2015/04/crowsfoot_notation.gif

 Onde a imagem acima está representando os relacionamentos de: 
  - um e apenas um => equivale a (1, 1) na notação de Peter Chen
  - um ou muitos => equivale a (1, N) na notação de Peter Chen
  - zero, um ou muitos => equivale a (0, N) na notação de Peter Chen
  - zero ou um => equivale a (0, 1) na notação de Peter Chen

## Integridade de Dados
- **Manutenção e garantia da consistência e  precisão dos dados**, sendo atingida por meio das **Restrições de Integridade**.
### 5 Principais tipos de Restrições de Integridade
- Referencial
- de Vazio
- de Chave
- Definida pelo usuário

#### Integridade de Domínio
  - Os valores inseridos em uma coluna devem ser do mesmo tipo dos valores aceitos por essa coluna.
  - Fatores:
    - tipo de dados do campo
    - representação interna do tipo de dado
      > Exemplo> se o valor é inteiro, númerico, data ou string.
    - presença ou não do dado
      > se o dado pode ser vazio
    - intervalo de valores do domínio
      > Exemplo: em um tabela de preço, só posso ter valores maiores que 0, pois não posso ter preço negativo.
    - conjunto de valores discretos
      > não necessariamente um intervalo, mas um exemplo de um dado que será guardado, por exemplo um preço: 55,34
#### Integridade Referencial
- Assegura que valores de uma coluna em uma tabela são valores válidos baseados nos valores em outra tabela relacionada.
> Exemplo: Na tabela de venda, foi registrado uma venda onde o id_produto vendido foi 540. Na tabela de produto, por sua vez, existe um id_produto 540.
##### Exclusão e Atualização(propagação em cascata)
- Se um registro A é excluido, todos os outros registros N que fazem referencia a A talvez sejam excluidos ou apenas setado null, irá depender da regra de negócio. 

#### Integridade de Vazio
- Informa se uma coluna é obrigatória ou não, podendo assumir valor null quando não for obrigatória.

#### Integridade de Chave
- Os valores inseridos em uma chave primária devem ser sempre únicos.
- Dessa forma, cada tupla/linha/registro será única.
- Chaves primária não pode ser nula.

#### Integridade Definada pelo Usuário
- Diz respeito a regra de negócio.
> Exemplo: Uma coluna que aceita apenas valores entre 1 e 10.

## **Dicionário de Dados**
- É um documento usado para armazenar informações sobre o **conteúdo**, **formato** e a **estrutura do banco**, assim como o **relacionamento entre os elementos**.
- Armazena informações sobre: **Entidade**, **Atributos** e **Relacionamentos**.
- Ajuda a limitar os erros ao criar a estrutura física do Banco.
- Também chamado de **Repositório de Metadados**.

| Tabela    | Relacionamento | Nome do Relacionamento  | Descrição                                          |
| :-------: | :------------: | :---------------------: | :-------------------------------------------------:|
| tbl_Livro | tbl_Autor      | Escreve                 | Tabela para cadastro de livros                     |
| tbl_Autor | tbl_Autor      | Escreve                 | Tabela para cadastro dos Autores de Livros         |

> Fazer também uma tabela para cada entidade, onde terá as colunas: **atributo**, **tipo de dado**, **comprimento**, **restrição**, **valor** e **descrição**. Colocar também o **valor máximo que cada registro poderá atingir**, fazendo um **somatório do comprimento**.
> Fazer também uma tabela para cada relacionamento, onde poderá ter as colunas: **tabela1-FK**, **tabela2-PK**... por exemplo.

## **Dependência Funcional**
- Seja **E** uma tabela, e **X** e **Y** os atributos dessa tabela. Dizemos que **Y** é funcionalmente dependente de **X** se e somense se cada valor de **X** tiver associado a ele exatamente um valor de **Y**.
- Simbolicamente:
X -> Y
  - Onde X determina funcionamente Y.
  - E Y depende funcionalmente de X.

> Exemplo: ID_Pedido -> Prazo_Entrega

> Prazo de entrega depende do ID_Pedido, pois o prazo varia de acordo com o pedido.

> Observação: Uma PK determina funcionalmente todos os outros atributos.

### Dependência Funcional Total
- Em uma relação onde existe uma **PK Composta**, **um atributo não-chave que depende de toda a chave composta**, não somente parte dela.

<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Depend_ncia_funcional_Total_aiNBGwDLq.png" 
  alt="Dependência Funcional Total"
  />
</p>
<p align="center">Dependência Funcional Total</p>

> Nessa tabela é possível observar que Quantidade_Produto depende tanto de ID_Produto como de ID_Pedido(quantidade de produto de qual pedido?).

### Dependência Funcional Parcial
- Em uma relação onde existe uma **PK Composta**, **um atributo não-chave que depende apenas de parte da PK**, não totalmente dela.


<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Depend_ncia_funcional_Parcial_kROKOI-m5.png" 
  alt="Dependência Funcional Parcial"
  />
</p>
<p align="center">Dependência Funcional Parcial</p>

> Nessa tabela, Nome_Disciplina **depende apenas** de ID_Disciplina.

### Dependência Funcional Transitiva
- Ocorre quando um atributo não-chave depende diretamente de outro atributo não-chave.

<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Depend_ncia_funcional_Transitiva_f-C2UENqT.png" 
  alt="Dependência Funcional Transitiva"
  />
</p>
<p align="center">Dependência Funcional Transitiva</p>

> Nessa tabela, Nome_Vendedor(atributo não-chave) **depende apenas** de ID_Vendedor(atributo não-chave).

### Dependência Funcional Multivalorada
- Ocorre quando para cada valor de um atributo não-chave **A** existe um conjunto de valores para outros atributos não-chave **B** e **C** que estão associados a **A**, mas não dependem entre si.
- Representação de uma dependência multivalorada:
A ->> B

| Modelo| Ano    | Cor     |
| :----:| :-----:| :------:|
| Gol   | 2018   | Vermelho|
| Uno   | 2020   |  Azul   |


> Ano e Cor **são independentes entre si** mas ambos dependem de Modelo.
> A partir do Ano, não consigo determinar a Cor.
> A partir da Cor, não consigo determinar o Ano.
> A partir do Modelo, consigo determinar Cor e Ano.

## Anomalias de Atualização
- Anomalias são problemas que ocorrem em **Banco de Dados mal planejados** e **não normalizados**.
- **Geralmente ocorre quando a excesso de dados em uma mesma tabela**.
- São causadas pelas **Dependências Parciais** e **Transitivas**.
- São classificadas em:
  - Inserção
  - Exclusão
  - Modificação
### Anomalia de Inserção
- Não deve ser possível inserir um dado, a não ser que outro dado esteja disponível.
> Exemplo: Não deve ser possível adicionar um novo livro sem que o autor desse livro já esteja cadastrado no banco de dados.

### Anomalia de Exclusão
- Ao excluir um registro, dados em uma outra tabela que fazem referência a esse registro também deve ser excluído.
> Exemplo: Se excluirmos um autor, todos os livros desse autor devem ser excluídos do banco.

### Anomalia de Modificação
- Ao atualizarmos um registro, todos os outros registros que fazem referência a ele devem ser atualizados.
> Exemplo: Caso o ID_Autor da tabela autor tenha sido atualizado, todas as tabelas que fazem referência a esse ID_Autor devem ser atualizados também. Dessa forma, os relacionamentos serão mantidos.

### Como eliminar as Anomalias de Atualização?
- Aplicando a técnica de Normalização.

## **Normalização**
- Consiste em analisar uma tabela, para verificar se a mesma está bem formada.
- **Decompor** tabelas que possuem anomalias para produzir **relações menores** e **bem-estruturadas**.
- **Ou seja, ao normalizar uma tabela, podemos inserir, excluir e modificar registros sem gerar anomalias.**
- Aplicamos uma **série de testes para verificar que a tabela satisfaça uma forma normal(FN)**.
- Originalmente, possuí três formas normais: primeira, segunda e terceira forma normal.
- Posteriormente a terceira forma normal foi revisada e deu origem a **Forma Normal de Boyce-Codd(FNBC)**.
- Existe a quarta e quinta forma normal, mas são raramente utilizadas.

## Objetivos da Normalização
- Analisar tabelas com suas **dependências funcionais e chaves primária** para:
  1. Minimizar redundâncias
  2. Minimizar anomalias de inserção, exclusão e modificação.
- **As relações serão decompostas em relações menores que atendem os testes de forma normal.**
- O ideal é que o **projeto do Banco de Dados alcance a terceira forma normal** ou a **forma normal de boyce-codd**.
- **NÃO** é ideal normalizar apenas até a primeira ou segunda forma normal.

## **Primeira Forma Normal(1FN)**
- **Em cada tabela**, eu devo analisar para que **NÃO** tenham atributos **multivalorados**, **compostos** e **suas combinações**.
- Ou seja, A primeira forma normal serve para reprovar tais atributos citados acima.
- Está na Primeira Forma Normal quando:
  - **Possuí apenas atributos atômicos**.
  - Não há grupos de atributos repetidos(há apenas um dado por coluna nas linhas).
  - Existe uma Chave Primária.
  - Relação **NÃO** possuí atributos multivalorados.
> Exemplo: Atributo Endereço é multivalorado, pois pode ser dívido em rua, cep, número, casa...

## **Normalização uma tabela até a 1FN**

- Podemos observar que a tabela cliente possuí o atributo multivalorado 'telefone'.
- Para normalizar, podemos criar uma nova tabela que servirá para armazenar os telefones dos clientes, onde terá como Chave Primária o **Cod** e o **telefone**.
### **Tabela Cliente(não normalizada)**
| Cod      | Nome_Cliente     | Telefone     |
| :------------- | :----------: | -----------: |
|  2532 | Danilo   | (86) 9 9999-9999/ (86)9 8888-8888   |

### **Tabela Cliente(normalizada)**

| Cod      | Nome_Cliente     |
| :------------- | :----------: |
|  2532 | Danilo   |

### **Tabela Telefone_Cliente**

| Cod      | Telefone     |
| :------------- | :----------: |
|  2532 | (86) 9 9999-9999   |
|  2532 | (86) 9 8888-8888  |
