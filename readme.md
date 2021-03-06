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
- **Me ajuda a enxergar o que é necessário guardar no banco.**

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
  <p align="center"><i>Representação de uma Entidade, Atributos e uma instância de Entidade</i></p>


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
<p align="center"><i>Diagrama Entidade Relacionamento</i></p>

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
<p align="center"><i>Relacionamento unário</i></p>

<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamento_Bin_rio_Ul1VR9yhW.png" 
  alt="Relacionamento binário"
  />
</p>

<p align="center"><i>Relacionamento binário</i></p>

<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamento_Tern_rio_tbBuyBmt2s.png" 
  alt="Relacionamento ternário"
  />
</p>
<p align="center"><i>Relacionamento ternário</i></p>

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
<p align="center"><i>Relacionamento entre tabelas</i></p>


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
<p align="center"><i>Notação de Peter Chen</i></p>


  - **Notação Pé de Galinha(*crows foot*)**

  <p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/crowsfoot_notation_6Ok5BWFOd.gif" 
  alt="Notação Pé de Galinha(*crows foot*)"
  />
</p>
<p align="center"><i>Notação Pé de Galinha(crows foot)</i></p>

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
<p align="center"><i>Dependência Funcional Total</i></p>

> Nessa tabela é possível observar que Quantidade_Produto depende tanto de ID_Produto como de ID_Pedido(quantidade de produto de qual pedido?).

### Dependência Funcional Parcial
- Em uma relação onde existe uma **PK Composta**, **um atributo não-chave que depende apenas de parte da PK**, não totalmente dela.


<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Depend_ncia_funcional_Parcial_kROKOI-m5.png" 
  alt="Dependência Funcional Parcial"
  />
</p>
<p align="center"><i>Dependência Funcional Parcial</i></p>

> Nessa tabela, Nome_Disciplina **depende apenas** de ID_Disciplina.

### Dependência Funcional Transitiva
- Ocorre quando um atributo não-chave depende diretamente de outro atributo não-chave.

<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/Depend_ncia_funcional_Transitiva_f-C2UENqT.png" 
  alt="Dependência Funcional Transitiva"
  />
</p>
<p align="center"><i>Dependência Funcional Transitiva</i></p>

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
- Não sou obrigado a normalizar, mas provavelmente eu teria um problema na hora de gravar, alterar ou deletar dados em um tabela complexa.

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
| Cod(PK)      | Nome_Cliente     | Telefone     |
| :------------- | :----------: | -----------: |
|  2532 | Danilo   | (86) 9 9999-9999/ (86)9 8888-8888   |

### **Tabela Cliente(normalizada)**

| Cod(PK)     | Nome_Cliente     |
| :------------- | :----------: |
|  2532 | Danilo   |

### **Tabela Telefone_Cliente**

| Cod(FK)(PK)      | Telefone(PK)     |
| :------------- | :----------: |
|  2532 | (86) 9 9999-9999   |
|  2532 | (86) 9 8888-8888  |

## **Segunda Forma Normal(2FN)**
- Baseada no conceito de **Dependência Funcional Total**.
- Uma tabela está na 2FN **se cada atributo não-chave for dependênte funcionalmente total da chave primária composta**.
- **Caso a PK não seja composta, esse teste não será aplicado.**
- Está na 2FN se:
  - Está na 1FN.
  - Todos os atributos não-chave possuem dependêncial funcional total, ou seja, de TODAS as partes da PK.
  - Não existem dependências funcionais parciais
  - Caso contrário, deve-se gerar uma tabela nova com dados.
## **Normalizando uma tabela até a 2FN**
- Deve-se criar uma **nova tabela com os atributos não-chave que dependem de parte da PK composta**.
- **A parte da PK composta que determina funcionalmente esses atributos não-chave, será também a PK da nova tabela criada.**

### **Tabela Peça(não 2FN)**
| Cod_Peça(PK)    | Cod_Fornecedor(PK)    | Local_Fornecedor    | Qtde_Estoque | Tel_Fornecedor
| :------------- | :----------: | :-----------: |:-----------: | -----------: |
|  2532 | 02   | Piauí   | 25   | (86) 9 9999-9999  |
|  2532 | 03   | São Paulo   | 20   | (11) 9 8888-8888  |
|  2533 | 03   | São Paulo   | 10   | (11) 9 8888-8888  |
|  2533 | 02   | Piauí   | 4   | (86) 9 9999-9999  |

### **Tabela Peça(na 2FN)**
| Cod_Peça(PK)    | Cod_Fornecedor(PK, FK)    | Qtde_Estoque | 
| :------------- | :----------: | -----------: |
|  2532 | 02   | 25   |
|  2532 | 03   | 20   | 
|  2533 | 03   | 10   | 
|  2533 | 02   | 4   |

### **Tabela Fornecedor(na 2FN)**
| Cod_Fornecedor(PK)   | Local_Fornecedor    | Tel_Fornecedor
| :------------- | :----------: | -----------: |
|  02 | Piauí | (86) 9 9999-9999  |
|  03 | São Paulo| (11) 9 8888-8888  |

## **Terceira Forma Normal(3FN)**
- Baseada no conceito de **dependência funcional transitiva**.
- **Não devem existir atributos não-chave que determinam funcionamento outro atributo não-chave(ou conjunto deles).**

Está na 3FN se:
- Está na 2FN.
- Não existir dependência funcional transitiva.

## **Normalizando uma tabela até a 3FN**
- Para cada atributo(ou conjunto) não-chave que determina funcionalmente outro atributo não-chave, crie uma nova relação. Esse atributo determinante será a PK na nova tabela.
- Mova todos os atributos que dependem funcionalmente desse atributo para a nova tabela.
- O atributo PK da nova tabela será agora FK na tabela antiga, para associar as duas tabelas.

### **Tabela Venda(não 3FN)**
| Nota_fiscal(PK)     | Cod_Vendedor (FK)  | Nome_Vendedor | Cod_Produto | Qtde_vendida |
| :------------- | :----------: | :----------: | :----------: | ----------: |
|  0001 | 04  | Danilo  | 002  | 01  |
> Nome_Vendedor(atributo não-chave) depende funcionalmente de Cod_Vendedor(atributo não-chave).

### **Tabela Venda(na 3FN)**
| Nota_fiscal(PK)     | Cod_Vendedor (FK)  | Cod_Produto | Qtde_vendida |
| :------------- | :----------: | :----------: | ----------: 
|  0001 | 04 | 002  | 01  |

### **Tabela Vendedor(na 3FN)**
| Cod_Vendedor(PK)    | Nome_Vendedor  |
| :------------- | ----------: |
|  04 | Danilo |

### **Passos da Normalização**
1. Tabela não-normalizada
2. Remover atributos multivalorados e compostos
3. 1FN
4. Remover as dependências funcionais parciais
5. 2FN
6. Remover as dependências funcionais transitivas
7. 3FN

## **Forma Normal de Boyce-Codd(FNBC)**
- **Quando uma Relação possuí mais do que uma chave candidata, podem ocorrer anomalias.**
- A 3FN não lida com:
  - Duas ou mais chaves candidatas compostas em uma relação.
  - Essas chaves candidatas tivessem atributo em comum(superposição).
- Caso a combinação dessas condições não ocorra, basta normalizar a tabela até a 3FN.
- **Uma relação só está na FNBC SE E SOMENTE SE os únicos determinantes forem a chave canditada composta.**
- Na FNBC as chaves candidatas não possuem dependências parciais por outros atributos.
- Uma relação R está na FNBC sempre que uma dependência funcional não-trivial X -> a se mantiver em R, assim X é uma superchave de R.

### **Dependência Funcional Trivial**
- Dependência que não pode deixar de ser satisfeita
- **Dependência funcional é trivial se o lado direito da expressão é subconjunto do lado esquerdo.**
> Exemplo: A -> B é um dependência funcional trivial se B for um subconjunto de A.
> Exemplo: { ID_Func, Nome_Func }(chave primária composta) -> ID_Func

### **Tabela Fornecedor**

| ID_Forn  | Nome          | ID_Prod | Quantidade  | 
| :------- | :-----------: | :-----: | ----------: |
|  01 | Fátima Salgados  | 10      | 30          |
|  01 | Fátima Salgados  | 12      | 55          |
|  02 | Danilo Salgados  | 10      | 30          |

- ID_Forn não pode ser chave primária, pois se repete.
- ID_Prod não pode ser chave primária, pois se repete.

**Chaves Candidatas Composta:**

{ ID_Forn, **ID_Prod** }

{ Nome, **ID_Prod** }

**ID_Prod acaba sendo o atributo em comum nas duas chaves candidatas composta, ou seja, superposição.**

## **Normalizando até a FNBC**
- Devemos decompor a tabela com os seguintes passos:
  1. Encontrar uma dependência funcional não-trivial X -> Y que viole a condição da FNBC. X não deve ser superchave.

  2. Dividir a tabela em duas: Uma com os atributos XY, ou seja, todos os atributos da dependência.

### **Tabela Fornecedor**
| ID_Forn(PK) | Nome          | 
| :------- | -----------: |
|  01 | Fátima Salgados  |
|  02 | Danilo Salgados  |

**posso ter a tabela com ID_Forn e ID_Prod como sendo a chave primária composta.**
### **Tabela Forn_Produto**
| ID_Forn(PK)(FK)  | ID_Prod(PK) | Quantidade  | 
| :------- | :-----------: | -----: |
|  01 |  10      | 30          |
|  01 |  12      | 55          |
|  02 |  10      | 30          |

**OU posso ter a tabela com Nome e ID_Produto como sendo a chave primária composta.**

### **Tabela Forn_Produto**
| Nome_Forn(PK)(FK)  | ID_Prod(PK) | Quantidade  | 
| :------- | :-----------: | -----: |
|  Fátima Salgados |  10      | 30          |
|  Fátima Salgados |  12      | 55          |
|  Danilo Salgados|  10      | 30          |

**Sempre há mais que uma decomposição válida na FNBC.**

#### Resumo
- Pegar uma tabela na 3FN e analisar se existem duas ou mais chaves candidatas composta.
- Caso haja, verificar se existem um atributo em comum entre essas chave candidatas composta.
- Caso possua, decompor a tabela, tal que:
    1. Remover o atributo(X) em comum para outra tabela juntamente com os atributos dependentes funcionais de X.
    2. Utilizar um dos atributos Y ou Z que seriam par do atributo X na tabela da qual ele foi removido.
    3. Na nova tabela, os atributos que eram chave candidata composta na tabela antiga, serão chave primária, por exemplo X e Y.

# Projeto Prático
- Banco de dados para o gerenciamento de uma faculdade.

**Objetivos do Banco de dados**
- Realizar controle centralizado de Alunos, Professores, Cursos, Disciplina, Histórico escolar e Turmas.

## Fases do Projeto
- Levantamento de Requisitos
- Identificação de Entidades, Relacionamentos e Atributos
- MER
- DER (criar, cardinalidade, eliminar n:m)
- Dicionário de Dados
- Normalização
- Implementação
- Testes básicos

## Regras de Negócio // Levantamento de Requisitos
- Um **Aluno** só pode estar matriculado em um curso por vez.
- Alunos possum um **código identificador(RA)**.
- **Cursos** são *compostos* por **Disciplina**.
- Cada disciplina terá no máximo 30 alunos por **Turma**.
- As disciplinas devem ser obrigatórias ou optativas, depende do curso.
- As disciplinas pertencem a departamentos específicos.
- Cada disciplina possuí um código de identificação.
- Alunos podem trancar matrícula, não estando então matriculados em nenhuma disciplina no semestre.
- Em cada semestre, cada aluno poderá se matricular em no máximo 9 disciplinas.
- O aluno poderá ser reprovado no máximo 3 vezes na mesma disciplina.
- A faculdade terá no máximo 3000 alunos matriculados simultaneamente, em 10 cursos distintos.
- Entram 300 alunos novos por ano.
- Existem 30 disciplinas no total disponíveis.
- O **Histórico escolar** traz todas as disciplinas cursadas por um aluno, incluindo nota final, frequência e período do curso realizado.
- **Professores** podem ser cadastrados sem mesmo lecionar.
- Existem 40 professores trabalhando na faculdade.
- Cada professor irá lacionar no máximo 4 disciplinas diferentes.
- Cada professor é vinculado a um departamento.
- Professores são identificados por código do professor.

> **Podem ter mais regras!!** Temos o processo de Análise para descobrir ou criar novas regras.

## Identificação de Entidades, Relacionamentos e Atributos

- Tentar reprensetar um elemento como Entidade, para que seja possível observar se pode ou não ocorrer instância daquele elemento.

### Entidades
- Aluno
- Professor
- Disciplina
- Curso
- Departamento
- Histórico Escolar
- Turma

 > Consegui identificar essas Entidades. Talvez existam mais, pois modelagem é um processo que pode mudar ao longo do tempo, mas ficará mais definada também com o tempo.

### Relacionamentos
- Aluno está matriculado em curso
- Aluno cursa disciplina
- Aluno realizou disciplina
- Disciplina pertence a curso
- Professor ministra disciplina
- Professor pertence a departamento
- Departamento é responsável por disciplina
- Departamento controla curso
- Disciplina depende de disciplina(pois existem disciplinas que possuem pré-requisitos)

### Atributos - Aluno
- RA
- Nome
- Sobrenome
- Endereço (rua, número, bairro, cep, cidade, estado)
- Código do curso

### Atributos - Professor
- Código do professor
- Nome
- Sobrenome
- Departamento

### Atributos - Professor
- Código da disciplina
- Nome disciplina
- Descrição curricular
- Código do departamento
- Número de alunos

### Atributos - Curso
- Código do curso
- Nome do curso
- Código do departamento

### Atributos - Departamento
- Código do departamento
- Nome departamento

> São todos os atributos? Talvez, pois o cliente às vezes não identifica exatamente tudo o que ele quer guardar.

## Diagrama Entidade Relacionamento
- Os relacionamentos serão feitos separadamente por entidade, e no final irei unir todos eles.
- Tanto a cardinalidade, atributos e relacionamentos devem ser feitos de forma individual, pois escolhi ir avançando aos poucos, para não ficar confuso.
- Como falado no tópico anterior, os atributos podem sofrer alteração de acordo com o tempo, pois às vezes não é possível identificar todos os atributos de maneira clara e fácil.

**Relacionamentos da Entidade Professor**
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamentos_Professor_HIymuADeq.png" alt="Relacionamentos da Entidade Professor"/>
    
  </p>
  <p align="center"><i>Relacionamentos da Entidade Professor</i></p>

**Relacionamentos da Entidade Departamento**

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamentos_Departamento_Wd6okNYcQ.png" alt="Relacionamentos da Entidade Departamento"/>
    
  </p>
  <p align="center"><i>Relacionamentos da Entidade Departamento</i></p>

**Relacionamentos da Entidade Disciplina**

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamentos_Disciplina_Rb-F619QO.png" alt="Relacionamentos da Entidade Disciplina"/>
    
  </p>
  <p align="center"><i>Relacionamentos da Entidade Disciplina</i></p>

**Relacionamentos da Entidade Curso**

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamentos_Curso_QGhf7Fefy.png" alt="Relacionamentos da Entidade Curso"/>
    
  </p>
  <p align="center"><i>Relacionamentos da Entidade Curso</i></p>

  **Relacionamentos da Entidade Aluno**

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamentos_Aluno_D1qPwtEx9J.png" alt="Relacionamentos da Entidade Aluno"/>
    
  </p>
  <p align="center"><i>Relacionamentos da Entidade Aluno</i></p>


**Todos Relacionamentos das Entidade e seus Atributos**

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamentos_com_atributos_43f1em76Z.png" alt="Todos Relacionamentos das Entidade e seus Atributos"/>
    
  </p>
  <p align="center"><i>Todos Relacionamentos das Entidade e seus Atributos</i></p>

## Calculando cardinalidades no DER
**Quem manda na cardinalidade é a regra de negócio!!**

1. Ler a entidade e seu relacionamento da seguinte forma.
  - Um professor pertence a quantos departamentos?
  Um e apenas um departamento.
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/cardinalidade_professor_7zJvb2_3OP6.png" alt="Cardinalidade professor"/>
    
  </p>
  <p align="center"><i>Cardinalidade professor</i></p>

  > Uma instância de entidade se relaciona com quantas instâncias de outra entidade?

  2. Ler também no sentido oposto.

  - A um departamento pertencem quantos professores?
  No mínimo um professor, no máximo N.

  <p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/cardinalidade_de_professor_e_departamento_UHGmmRJko.png" alt="Cardinalidade professor e departamento"/>
    
  </p>
  <p align="center"><i>Cardinalidade professor e departamento</i></p>

  **A cardinalidade da entidade fica do lado oposto do relacionamento.**
  
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/cardinalidade_lado_1zl7gXpd0h.png" alt="Cardinalidade de uma entidade"/>
    
  </p>
  <p align="center"><i>Cardinalidade de uma entidade</i></p>

### Em relacionamentos onde os dois lados são (1,N), o relacionamento se tornará uma **entidade associativa(ou tabela associativa/pivô)**, pois ao **somarmos as cardinalidades** teremos um relacionamento **muitos-para-muitos(N,M)**
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/cardinalidade_nm_UK6BYWQuFK.png" alt="Cardinalidade muitos-para-muitos"/>
    
  </p>
  <p align="center"><i>Cardinalidade muitos-para-muitos</i></p>

### Cardinalidade completa do DER(intermediário)

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Cardinalidade_de_todas_as_entidades_4iDywXqsVH.jpg" alt="Cardinalidade de todas as entidades"/>
    
  </p>
  <p align="center"><i>Cardinalidade de todas as entidades</i></p>

## Eliminando relacionamentos muitos-para-muitos
Relacionamentos desse tipo devem ser eliminados, pois irão gerar problemas na implementação do banco, como: **redundância**, **integridade de dados**.

### Entidade associativa
- Gerada para resolver relacionamentos N:M.
- Possuí as **chaves primárias** das tabelas da relação como **chaves estrangeiras**.
- Irá gerar relacionamento 1:N.

Exemplo:

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Relacionamento_muitos_para_muitos_GaiSgQLq5.png" alt="Relacionamento muitos-para-muitos"/>
    
  </p>
  <p align="center"><i>Relacionamento muitos-para-muitos</i></p>

Resolvendo relacionamento muitos-para-muitos com entidade/tabela associativa
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Tabela_associativa_Xv-BpYQNe.png" alt="Entidade/Tabela associativa"/>
    
  </p>
  <p align="center"><i>Entidade/Tabela associativa</i></p>

No projeto prático, temos os seguintes relacionamentos N:M, logo, será necessário criar uma entidade associativa para cada um deles:
- Curso pertence Disciplina
- Disciplina compõe Histórico
- Professor ministra Disciplina

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/tabela_associativa_historico_disciplina_6PGNg4u-8E.png" alt="Entidade/Tabela associativa histórico_disciplina"/>
    
  </p>
  <p align="center"><i>Entidade/Tabela associativa histórico_disciplina</i></p>

### DER - Intermediário com tabelas associativas
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/DER_faculdade_Fz13fuvqa.jpg" alt="DER intermediário com tabelas associativas"/>
    
  </p>
  <p align="center"><i>DER intermediário com tabelas associativas</i></p>

## Criando dicionário de dados(intermediário)
**Dicionário de dados: Entidades**

| Entidade      | Relacionamento | Nome do Relacionamento | Descrição | 
| :-------      | :-----------: | :-----: | :-----:|
|  Departamento |  Professor / Curso / Disciplina | Pertence / Controla / Gerencia | Tabela para cadastro dos departamentos da faculdade| 
|  Professor    |  Departamento / Prof_disciplina  | Pertence / Leciona | Tabela para cadastro dos professor da faculdade |
|  Turma        |  Curso / Aluno    | Gerencia / Pertence  |  Tabela para registro de turmas em andamento e encerradas|

</br>

**Dicionário de dados: Relacionamentos**

| Relacionamento      | Tabela1_ | Tabela2 | Descrição | 
| :-------      | :-----------: | :-----: | :-----:|
|  Pertence |  Departamento | Professor | Qual departamento cada professor pertence | 
|  Leciona |  Prof_disciplina  | Professor | Quais disciplinas o professor leciona |

</br>

**Dicionário de dados: Atributos**

Entidade departamento:
| Atributo| Tipo de dados | Comprimento | Restrição |Descrição | 
| :-------      | :-----------: | :-----: | :-----:| :-----:|
|  Cod_Departamento |  Inteiro | 4 bytes | PK, NOT NULL | Código de identificação do departamento | 
|  Nome_Departamento |  Caractere | 40 bytes | NOT NULL | Nome do departamento | 

</br>

Entidade professor:
| Atributo| Tipo de dados | Comprimento | Restrição |Descrição | 
| :-------      | :-----------: | :-----: | :-----:| :-----:|
|  Cod_professor |  Inteiro | 4 bytes | PK, NOT NULL | Código de identificação do professor | 
|  Nome_professor |  Caractere | 40 bytes | NOT NULL | Nome do professor | 
|  Sobrenome_professor |  Caractere | 40 bytes | NOT NULL | Nome do Sobrenome do professor | 
|  Status |  Booleano | 1 bit | NOT  NULL | Status do professor (lecionando / não lecionando) | 

</br>

Entidade Disc_Hist:
| Atributo| Tipo de dados | Comprimento | Restrição |Descrição | 
| :-------      | :-----------: | :-----: | :-----:| :-----:|
|  Cod_Histórico |  Inteiro | 4 bytes | PK, FK, NOT NULL | Código de identificação do histórico | 
|  Cod_Disciplina |  Inteiro | 4 bytes | PK, FK, NOT NULL | Código de identificação do disciplina | 
|  Nota |  Decimal | 8 bytes | NOT NULL | Nota da disciplina | 
|  Frequência |  Inteiro | 4 byter | NOT  NULL | Número de faltas na disciplina |

</br> 

## Modelo lógico
Antes, a representação foi feita utilizando retangulos, losangos e afins. No modelo lógico serão tabelas que se relacionam por meio da chave estrangeira.
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Modelo_l_gico_0o11edW7B.png" alt="Modelo lógico das entidades/tabelas Turma e Curso à partir do DER da faculdade"/>
    
  </p>
  <p align="center"><i>Modelo lógico das entidades/tabelas Turma e Curso à partir do DER da faculdade</i></p>

Fazer isso para todas as tabelas do banco.

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Modelo_l_gico_Faculdade__FgX8cQhE.jpg" alt="Modelo lógico das entidades/tabelas à partir do DER da faculdade"/>
    
  </p>
  <p align="center"><i>Modelo lógico das entidades/tabelas à partir do DER da faculdade</i></p>

## Normalização
### Primeira Forma-Normal
- Observar as tabelas que possuem nome e sobrenome, pois: Sobrenome pode ter vários valores ali dentro, exemplo "Bastos Bandeira". Mas a idéia de atributo multivalorado é **ter vários valores diferentes para um campo(telefone, por exemplo)**, ou seja, um sobrenome com várias palavras continua sendo **APENAS UM sobrenome(atributo simples/atômico)**.
>Continua sendo apenas uma instância *Bastos Bandeira* para o instância *Danilo*.

- Tabela de aluno possuí campos multivalorados: Filiação, Contato, Telefone.
> Pode ser apenas um telefone ou muitos, vai depender do requisito do cliente.

- Tabela Histórico possuí campo multivalorado: Período de realização. Dividir em Data início e Data fim.

> Tabela Histórico_Disciplina tem o campo nota. Essa é a nota final do aluno e não suas notas.

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Modelo_l_gico_1fn_IdW2QyL_B.jpg" alt="Modelo lógico das entidades/tabelas na Primeira Forma Normal"/>
    
  </p>
  <p align="center"><i>Modelo lógico das entidades/tabelas na Primeira Forma Normal</i></p>

### Segunda Forma-Normal
- Tabela aluno possui campos que não depende da chave primária: Nome_Rua, Num_Rua, CEP, Tel_Residencia, Tel_Cel. Ao mudar o aluno, não significa que esses atributos irão mudar, pois podem existir vários alunos que moram na mesma rua.
Criar novas tabelas para **telefone**, **tipo do telefone**, **endereço** e **tipo de logradouro**.

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Modelo_L_gico_2fn_8TEhD0Oob.jpg" alt="Modelo lógico das entidades/tabelas na Segunda Forma Normal"/>
    
  </p>
  <p align="center"><i>Modelo lógico das entidades/tabelas na Segunda Forma Normal</i></p>

> Tabela Histórico_Disciplina os campos nota e frequência possuem dependência funcional total.

> Não sou obrigado a normalizar, mas provavelmente eu teria um problema na hora de gravar, alterar ou deletar dados em um tabela complexa como a de aluno.


### Terceira Forma-Normal
**Devo olhar os atributos não-chaves e verificar se um afeta o outro, se ao excluir um o outro sofrerá alterações.**

**Exemplo**: Se eu remover CPF de uma ocorrência de Aluno, algum outro atributo deixa de fazer sentido? NÃO!

**Exemplo 2**: Na tabela Professor, se eu eliminar o nome do professor, o status do professor deixa de existir? Não, pois Status do professor não depende do Nome do Professor.

**Exemplo 3**: Na tabela Turma, data_fim depende da data_inicio? Não, pois existem cursos com duração diferente, não consigo determinar a data de fim só em saber a data de início.

**Exemplo 4**: Na tabela Aluno se for alterado o nome do aluno, não quer dizer que será alterado o nome do mãe/pai. Posso ter 40 alunos com nome Ana, mas o CPF ser diferente. Quando altero o Cod_Aluno, tudo será alterado. Se eu alterar nome, nenhum outro campo sofrerá alteração.

**Exemplo 5**: Na tabela Endereço_Aluno se eu tirar o CEP, a rua deixa de fazer sentido? Não.

**Na primeira forma normal** encontramos mais problemas. **Na segunda forma normal**, menos problemas. **Na terceira forma normal**, menos ainda.

O banco já está na terceira forma normal. E como não foi encontrado nenhum problema, não é necessário ir para a Forma Normal de Boyce-Codd.

## Dicioniário de Dados(Final)
Refatorar o dicionário de dados e simplificar. Serão descritos apenas as **entidades** e os **atributos**, pois irei utilizar o próprio modelo lógico para descrever os relacionamentos na hora da implementação do banco de dados.

Entidades

| Entidade | Relacionamentos | Nome do Relacionamento | Descrição |
| :-----: | :----- | :----- | :----- |
| Aluno | Aluno_disciplina/Curso/Turma... | Cursa/Está Matriculado/Faz parte... | Tabela que guarda informações de Aluno |

</br>

Atributos: Entidade Aluno

| Atributo | Tipo/Domínio | Comprimento | Restrição | Descrição |
| :----- | :----- | :----- | :---- | :----- |
| Cod_Aluno | Inteiro | 6 Bytes | PK, NOT NULL |  Código do aluno |
| Nome_Aluno | Caractere | 20 Bytes | NOT NULL |  Nome do aluno |
| Sobrenome_Aluno | Caractere | 50 Bytes | NOT NULL |  Sobrenome do aluno |
| Email | Caractere | 60 Bytes | NOT NULL |  Email do aluno |
| CPF | Caractere | 11 Bytes | UNIQUE, NOT NULL |  CPF do aluno |
| Sexo | Caractere | 1 Byte | NOT NULL |  Sexo do aluno |
| Status | Boolean | 1 Bit | NOT NULL |  Status de matrícula do aluno |
| Nome_Mãe | Caractere | 60 Bytes | NOT NULL |  Nome da mãe do aluno |
| Nome_Pai | Caractere | 60 Bytes | NULL |  Nome da pai do aluno |
| Cod_Turma | Inteiro | 6 Bytes | FK, NOT NULL |  Código da turma que o aluno faz parte |
| Cod_Curso | Inteiro | 6 Bytes | FK, NOT NULL |  Código do curso que o aluno está matriculado |

> 1 caractere = 1 byte

## Implementação do Banco de dados
1. Para criar uma tabela que possuí chave estrangeira(depende de outra tabela), eu preciso primeiro criar a tabela dessa chave estrangeira. **Caso contrário, haverá erro**.

2. Ir criando as tabelas em sequência.

3. Ao inserir dados, segue a mesma lógica de criação de tabelas.
> Irei postar logo mais os códigos e explicar sobre sql

## SQL - Structured Query Language
Linguagem de consulta estruturado

### Funções
- Permite acesso aos dados em SGBDR.
- Permite **inserir** e **manipular** dados em Banco de Dados.
- Permite **criar** e **excluir tabelas** e banco de dados.
- Permite criar **triggers**, **visões**, **Stored Procedures**.
- Permite configurar permissões de acesso.

### Grupo de Comandos SQL
1. DDL - Data Definition Language.
2. DML - Data Manipulation Language.
3. DCL - Data Control Language.
4. DQL - Data Query Language.

### 1. DDL - Data Definition Language
| COMANDO | DESCRIÇÃO |
| :---- | :---- |
|CREATE|Cria uma nova tabela, visão ou objeto|
|ALTER|Modifica uma tabela ou objeto existente no banco|
|DROP|Exclui uma tabela ou objeto|

</br>

### 2. DML - Data Manipulation Language
| COMANDO | DESCRIÇÃO |
| :---- | :---- |
|INSERT|Inserir um novo registro|
|UPDATE|Modifica registro|
|DELETE|Exclui registro|

</br>

### 3. DCL - Data Control Language
| COMANDO | DESCRIÇÃO |
| :---- | :---- |
|GRANT|Dá acesso a um usuário|
|REVOKE|Retira acesso/privilegios do usuário|

</br>

### 4. DDL - Data Query Language
| COMANDO | DESCRIÇÃO |
| :---- | :---- |
|SELECT|Seleciona, obtém os registro de uma tabela|


</br>

## Criando, visualizando e excluindo um Banco de dados
Para criar, basta ir no MySQL Workbench ou o SGBDR que você está utilizando e executar o comando:

```sql
CREATE DATABASE IF NOT EXISTS db_Biblioteca;
```

Para verificar os bancos de dados que existem, executar o comando:
```sql
SHOW DATABASES;
```

Para utilizar um BD, você precisa selecioná-lo utilizando o comando:
```sql
USE db_Biblioteca;
```

Para visualizar o BD selecionado, execute o comando:
```sql
SELECT DATABASE();
```

Para excluir um BD
```sql
DROP DATABASE IF EXISTS db_Biblioteca;
```

Para visualizar as tabelas do BD
```sql
SHOW TABLES;
```

## SQL Constrains(restrições)
- São regras aplicadas as colunas da tabela.
- Usada para limitar os tipos de dados que serão inseridos na coluna.
- Pode ser especificado no momento de criação da tabela(CREATE) ou depois dela ter sido criada(ALTER).

### Principais Constrains
- NOT NULL
- UNIQUE
- PRIMARY KEY
- FOREIGN KEY
- DEFAULT

### NOT NULL
- Define que aquela coluna não pode exister valores nulos.
- Desse modo, não é possível inserir um registro(ou atualizar) sem entrar com um valor nesse campo.

### UNIQUE
- Identifica de forma única cada registro do banco de dados.
- UNIQUE e PRIMARY KEY garantem que aquele registro será exclusivo na tabela.
- PRIMARY KEY já é automaticamente UNIQUE.
- Podem existir vários UNIQUE, mas apenas uma PRIMARY KEY na tabela.

### PRIMARY KEY
- Identifica de forma única cada registro.
- Único.
- Não pode ser nulo.
- Apenas uma Chave primário por tabela.

### FOREIGN KEY
- Define a relação entre duas ou mais tabelas.
- Aponta para a Chave primária de outra tabela.
- Não é única.

```sql
CONSTRAINT fk_ID_Autor FOREIGN KEY(ID_Autor) REFERENCES tbl_Autor(ID_Autor)
```

> *CONSTRAINT fk_ID_Autor* - nome da registração.

> FOREIGN KEY(ID_Autor) nome da coluna que fará referência da PK da outra tabela.

> REFERENCES tbl_Autor(ID_Autor) nome da tabela que possuí a PK seguido do nome da coluna.

### DEFAULT
- Valor que será padrão caso nenhum valor seja inserido naquela coluna.

### Criando tabelas
```sql
CREATE TABLE [IF NOT EXISTS] nome_tabela(
  nome_coluna dominio_dado constraints,
  ...
);
```

> [comando opcional] retirar os cochetes

```sql
CREATE TABLE IF NOT EXISTS tbl_Livro(
  ID_Livro SMALLINT AUTO_INCREMENT PRIMARY KEY,
  Nome_Livro VARCHAR(50) NOT NULL,
  ISBN VARCHAR(30) NOT NULL,
  ID_Autor SMALLINT NOT NULL,
  Data_Pub DATE NOT NULL,
  Preco_Livro DECIMAL NOT NULL
);

CREATE TABLE IF NOT EXISTS tbl_Autor(
  ID_Autor SMALLINT AUTO_INCREMENT PRIMARY KEY,
  Nome_Autor VARCHAR(50),
  Sobrenome_Autor VARCHAR(60),
);

CREATE TABLE IF NOT EXISTS tbl_Editora(
  ID_Editora SMALLINT AUTO_INCREMENT PRIMARY KEY,
  Nome_Editora VARCHAR(50)
);

SHOW TABLES;
```

## Auto_increment
- Permite que um número único seja gerado quando um novo registro for inserido.
- Em mySQL é o comando AUTO_INCREMENT.
- Possuí valor inicial padrão 1 e incrementa 1 quando um novo registro é inserido.
- Posso alterar o valor inicial padrão AUTO_INCREMENT = 100 para iniciar do 100, por exemplo.
- Só pode existir **um AUTO_INCREMENT por tabela**.
- **NÃO** preciso inserir valor naquela coluna, pois o valor é inserido de forma automática, como o nome sugere.
- **NÃO** necessita utilizar a constraint NOT NULL, pois ele já possuí de forma automática.

Exemplo:
```sql
CREATE TABLE IF NOT EXISTS tbl_teste_incremento(
  ID_Test SMALLINT AUTO_INCREMENT PRIMARY KEY,
  Nome VARCHAR(50) NOT NULL
) AUTO_INCREMENT = 40;

INSERT INTO tbl_teste_incremento(Nome) VALUES('Danilo');
INSERT INTO tbl_teste_incremento(Nome) VALUES('Ana');

SELECT * FROM tbl_teste_incremento;

SELECT MAX(ID_Test) FROM tbl_test_incremento;
```

> SELECT MAX(nome_coluna) FROM nome_tabela retorna o valor máximo/registro mais atual.

> SELECT * FROM tbl_test_incremento WHERE ID_Test=LAST_INSERT_ID(); faz com que eu selecione o último registro inserido no banco

### Alterar os próximos valores do AUTO_INCREMENT
Para alterar o comando dos próximos valores de um auto_increment

```SQL
ALTER TABLE tbl_test_incremento
AUTO_INCREMENT = 50;
```
## Tipos de dados(mySQL)
- Existem vários tipos de dados quem podem ser inseridos com valores de intervalos diferentes. Alguns exemplos:

| Tipo | Descrição |
|:---- | :-------  |
|INT   | Inteiro regular, pode variar entre -2147483648 e 2147483647|
|SMALLINT   | Inteiro, pode variar entre -32768 e 32768|
|DECIMAL(P,D)  | Ponto flutuante, decimal(P,D) onde valor máximo de P é 1 à 65 e D é 0 à 30|
|FLOAT(P,D)   | Ponto flutuante, decimal(P,D) onde valor máximo de P é 1 à 65 e D é 0 à 24|
|VARCHAR| Ocupa tamanho variado até 65, 533(onde será somado a 2, valor do prefixo) por **registro**|
|CHAR| Ocupa tamanho fixo entre 0 e 255|
|BOOLEAN| Valor entre 0 e 1|
|BLOB|Utilizado para armazenar grandes quantidades de dados, como imagem|
|MEDIUMTEXT|Permite strings grandes, como descrição|

</br>

> DECIMAL(P,D), P se refere a precisão do valor, ou seja, qual o valor de digitos totais e o D se refere a escala que são o número de casas após a vírgula. **Padrão DECIMAL(10,0)**.

> FLOAT(P,D), Padrão FLOAT(10, 2).

> VARCHAR, Caso eu tenha dois varchar no mesmo registro, posso coloca-los com valor máximo de 32765+2+32766+2=65535

```sql
CREATE TABLE IF NOT EXISTS varchar_test (
    s1 VARCHAR(32765) NOT NULL,
    s2 VARCHAR(32766) NOT NULL
)  CHARACTER SET 'latin1' COLLATE LATIN1_DANISH_CI;

```

Mais informais sobre os tipos de dados aceitos no mySQL, acessar: https://www.mysqltutorial.org/mysql-data-types.aspx

## Alterando tabelas(ALTER TABLE)
- Depois da tabela ter sido criado, posso atualizada-la utilizando o seguinte comando:
```sql
ALTER TABLE nome_table ADD COLUMN nome_coluna;
```

- Posso atualizar o tipo de dado daquela coluna
- Posso inserir uma chave primária

```sql
ALTER TABLE tbl_test MODIFY COLUMN Nome_Pessoa VARCHAR(60) NOT NULL;

ALTER TABLE tbl_test ADD PRIMARY KEY (ID_Test);
-- para isso, a ID_Test já deve exister na tbl_test
```

Adicionar na tabela de livros as colunas ID_Autor, ID_Editora.

```sql
ALTER TABLE tbl_livro ADD ID_Autor SMALLINT NOT NULL;
ALTER TABLE tbl_livro ADD ID_Editora SMALLINT NOT NULL;

ALTER TABLE tbl_livro ADD 
CONSTRAINT fk_ID_Autor 
FOREIGN KEY (ID_Autor) REFERENCES tbl_autor(ID_Autor);

ALTER TABLE tbl_livro ADD 
CONSTRAINT fk_ID_Editora 
FOREIGN KEY (ID_Editora) REFERENCES tbl_editora(ID_Editora);
```

## Plotando o DER à partir do SQL
1. Ir em databases, reverser engineer.
2. Seleciona a conexão.
3. Next, next, seleciona o database, next...

Resultado:
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/DER_a_partir_do_sql_WaEwROaUh.png" alt="DER à partir do SQL"/>
    
  </p>
  <p align="center"><i>DER à partir do SQL</i></p>

## Inserir dados no banco mysql
Utilizando o comando

```sql
INSERT INTO nome_table(coluna1, coluna2) VALUES (valor1, valor2);
```
**Começar inserindo os dados por tabelas que não depende de outras tabelas, ou seja, que não possuem chave estrangeira.**

```sql
INSERT INTO tbl_autor(ID_Autor, Nome_Autor) VALUES (1, 'Danilo Bandeira');
INSERT INTO tbl_autor(ID_Autor, Nome_Autor) VALUES (2, 'Ana Banana');
INSERT INTO tbl_autor(ID_Autor, Nome_Autor) VALUES (3, 'Larica');
INSERT INTO tbl_autor(ID_Autor, Nome_Autor) VALUES (4, 'Thayann');
```

```sql
INSERT INTO tbl_editora(Nome_Editora) VALUE ('Editora1');
INSERT INTO tbl_editora(Nome_Editora) VALUE ('Editora2');
INSERT INTO tbl_editora(Nome_Editora) VALUE ('Editora3');
INSERT INTO tbl_editora(Nome_Editora) VALUE ('Editora4');
```

Agora consigo inserir dados na tabela de livro, pois ela depende de chaves estrangeiras(ID_Autor e ID_Editora). Lembrando que os valores das chaves estrangeiras devem fazer referencias as chaves primárias existentes em ambas as tabelas.

```sql
INSERT INTO tbl_livro(Nome_Livro, ISBN, ID_Autor, Data_Pub, Preco_Livro, ID_Editora) VALUES('Dexter is delicious', 4444, 1, '2020-09-26', 50, 4);
```
## Datatype of column(tipos de dados de uma tabela)
Para saber o tipo de dados da coluna de uma tabela basta executar o comando;

```sql
SELECT data_type, column_type 
FROM information_schema.columns 
WHERE table_schema = 'db_Biblioteca'
AND table_name = 'tbl_livro'; 
```
## SELECT - Realizar consultas simples

```SQL
SELECT coluna FROM tabela;
```

Dessa forma ainda não é possível pegar os dados de mais de uma tabela, mesmo que elas estejam relacionadas.

Exemplos:
```SQL
SELECT nome_editora FROM tbl_editora;

SELECT * FROM tbl_editora;

SELECT * FROM tbl_editora WHERE nome_editora = 'Salgados';

```

## ORDER BY - Consultas ordenadas;
Caso queira em ordem crescente, posso utilizar a palavra ASC ou não, já que por padrão é ordenado de forma crescente.

```sql
SELECT Nome_Livro, ID_livro, Preco_Livro
FROM tbl_livro
ORDER BY Preco_Livro ASC;
```

Caso queira em ordem descrecente, basta utilizar a palavra DESC.
```sql
SELECT Nome_Livro, ID_livro, Preco_Livro
FROM tbl_livro
ORDER BY Preco_Livro DESC;
```
## Indexar tabelas
- Para realizar consultas de maneira performatica.
- Vai direto ao indíce ao invés de percorrer toda a tabela.

**Em mySQL, algumas colunas já possuí indíces:**
- PRIMARY KEY
- FOREIGN KEY
- CONSTRAINT UNIQUE

Existem 2 tipos de Indíces:
**Clusterizado**
- Só existe um por tabela.
- Altera a forma que os dados são armazenados na tabela.
- Caso não possua chave primária a constraint UNIQUE irá servir como indíce.
- Caso não possua PK e UNIQUE, os dados serão armazenados em uma estrutura não-organizada chamada *heap*.

**Não-Clusterizado**
- Podem existir vários por tabela.
- Não altera a forma que os dados são armazenados.
- Cria um objeto que irá apontar para o indíce,**ou seja, serve como ponteiro**.

## Criar index
Criar tabela e o index ao mesmo tempo(significa que o banco foi bem planejado).
```sql
CREATE TABLE IF NOT EXISTS tbl_test(
  id_test int AUTO_INCREMENT PRIMARY KEY,
  nome_test varchar(50) NOT NULL,
  INDEX (id_test, nome_test) 
);

```

Posso criar um indíce em uma tabela que já existe
```sql
CREATE [UNIQUE] INDEX nome_index
ON nome_tabela(
  coluna1 [ASC | DESC],
  coluna2 [ASC | DESC],
  coluna3 [ASC | DESC]...
);
```
Posso utilizar o comando ALTER // ADD INDEX
```sql
ALTER TABLE nome_tabela ADD INDEX nome_index(colunas);
```

### Mostrar index de uma tabela
```sql
SHOW INDEX FROM tbl_test;
```

Comando para explicar outro comando, como será de fato executado:
```SQL
EXPLAIN SELECT * FROM tbl_livro WHERE nome_livro = 'Dexter';
```
### Resultado da consulta na tabela em uma coluna não-indexada com o extra WHERE
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/comando_explain_se_t7Qiq6.png" alt="Resultado da consulta na tabela em uma coluna não-indexada"/>
    
  </p>
  <p align="center"><i>Resultado da consulta na tabela em uma coluna não-indexada</i></p>

É possível observar na imagem acima que para realizar tal consulta, foi necessário percorrer 20% do banco para retornar o resultado.

**NÃO criar indíces em qualquer coluna. Evitar utilizar em colunas que alteram muito seu valor, pois ao ter o valor alterado o index também deve ser atualizado... logo, irá gerar uma lentidão.**

**Criar indíces em colunas que são mais acessadas, mas que não sofrem alterações constantes.**

### Resultado da consulta na tabela em uma coluna indexada com extra WHERE

```sql
EXPLAIN SELECT * FROM tbl_livro
WHERE nome_livro = 'Dexter';
```

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/comando_explain_com_where_jQkuLvjYm.png" alt="Resultado da consulta na tabela em uma coluna indexada com extra WHERE"/>
    
  </p>
  <p align="center"><i>Resultado da consulta na tabela em uma coluna indexada com extra WHERE</i></p>

Observação: Caso eu faça um consulta passando a chave primária no where, é possível observar que o filtro é o mesmo acima... ou seja, uma consulta direta ao dado desejado.

### Remover index
```SQL
DROP INDEX nome_index ON nome_tabela;
```

## WHERE
Permite filtrar registros em uma consulta. Consigo utilizar com operadores mais complexos para filtragens mais complexas.

```sql
SELECT colunas FROM tabela WHERE coluna = valor;
```
## AND, OR e NOT
- Operadores lógicos usados para filtrar registros em mais de uma condição.

Exemplos:

```SQL
SELECT ID_Livro, Nome_Livro
FROM tbl_livro
WHERE ID_Livro >= 2 OR Nome_livro = 'Dexter2';
```

```SQL
SELECT ID_Livro, Nome_Livro
FROM tbl_livro
WHERE ID_Livro < 2 AND NOT Nome_livro = 'Dexter2';
```

```SQL
SELECT ID_Livro, Nome_Livro
FROM tbl_livro
WHERE NOT(ID_Livro >= 4 OR Nome_livro = 'Dexter')
```
## Excluir Registros
Caso queira excluir poucos registros, utilizar o DELETE

```SQL
DELETE FROM tbl_livro
WHERE ID_Livro = 4;
```
**Observações:**
1. Utilizar o WHERE, pois sem isso, irá deletar todos os registros da tabela.
2. No safemode, posso deletar apenas utilizando o ID como filtro ou se a coluna for indexada.
3. Caso a tabela esteja relacionada, será necessário utilizar o join(irei aprender sobre em outras aulas).

</br>

Caso queira excluir **TODOS** os registros de uma tabela, utilizar o *TRUNCATE TABLE*, pois ele é mais rápido e consome menos recursos do sistema e log de transações.

```SQL
TRUNCATE TABLE tbl_livro;
```
**Observação:** Caso a tabela esteja relacionada, talvez seja necessário excluir os registros da outra tabela primeiro(irei aprender sobre em outras aulas).

## ALIAS
Dar um apelido a coluna/tabela.

```sql
SELECT ID_Livro AS CÓDIGO, Nome_livro AS Livro
FROM tbl_livro AS TABELA_DE_LIVROS;
```
**Observação:**
1. Facilita quando tenho que criar códigos grandes, complexos.
2. Alteração no nome da tabela é mais utilizada quando hover junção de tabelas, utilizando o *JOIN*.

## Funções de agregação(MAX, MIN, AVG, COUNT, SUM)
- Permite executar operações aritméticas nos valores de uma coluna em todos os registros de uma tabela.
- Retorna um valor único baseado em um conjunto de valores.
### **CUIDADO!!**
**Sempre interessante agrupar os dados(*GROUP BY*) para evitar erros.**

```sql
nome_função(ALL | DISTINCT expressão)
```
**Observações:**
1. ALL pega todos os valores, já é padrão.
2. DISTINCT pega os valores que não se repetem.

Funções mais comuns:
- MIN = Valor mínimo
- MAX = Valor máximo
- AVG = Média aritmética
- SUM = Total
- COUNT = Contador de 1 em 1

Retorna a quantidade de livros registrados.
```SQL
SELECT COUNT(*) FROM tbl_livro;
```
</br>

Retorna a quantidade de livros registrados que possuem Id_Autor diferentes, pois podem existem vários livros de apenas um autor.

```SQL
SELECT COUNT(DISTINCT Id_Autor) FROM tbl_livro;
```
</br>

Retorna o valor máximo na coluna Preco_livro.
```SQL
SELECT MAX(Preco_livro) FROM tbl_livro;
```
</br>

Retorna o valor mínimo na coluna de Preco_livro.
```SQL
SELECT MIN(Preco_livro) FROM tbl_livro;
```
</br>

Retorna a somatório dos valores na coluna Preco_livro.
```SQL
SELECT SUM(Preco_livro) FROM tbl_livro;
```
</br>

Retorna a média aritmética de Preco_livro.
```SQL
SELECT AVG(Preco_livro) FROM tbl_livro;
```
</br>

## Renomear tabelas
Não mexe nos dados, mas é sempre bom fazer um backup.

```sql
RENAME TABLE nome_antigo TO novo_nome;
```
## Atualizar registros
- Bastante utilizado no dia a dia.
- Pode atualizar um ou vários registros, tudo depende do filtro aplicado no WHERE(ou não utilização do mesmo).

```sql
UPDATE tbl_livro 
SET nome_livro = 'Dexter gods left hand' 
WHERE nome_livro = 'Dexter2';
```

**Observação:** Se eu não utilizar o *WHERE*, **TODOS** os registros serão atualizados.

## BETWEEN Seleção entre intervalos

```sql
SELECT Nome_Livro AS Livro, Preco_Livro AS Preço
FROM tbl_livro
WHERE Preco_Livro BETWEEN 50.00 AND 99.99;
```
```sql
SELECT Nome_livro AS Livro, Preco_livro AS Preço, Data_pub AS Lançamento
FROM tbl_livro
WHERE Data_pub BETWEEN '2020-10-29' AND '2021-10-29';
```

## LIKE e NOT LIKE
- Filtragem de padrão de caracteres.
- Similar a REGEX.

**%** = qual cadeia de 0 ou mais caracteres.

**_** = um caractere único.

Livros que o nome começam com D, não importando o que vem depois.
```SQL
SELECT * FROM tbl_livro
WHERE Nome_Livro LIKE 'D%';
```
Livros que o nome NÃO começam com D, não importando o que vem depois.
```SQL
SELECT * FROM tbl_livro
WHERE Nome_livro NOT LIKE 'D%';
```

Livro que terminam com S, não importando o que vem antes.

```sql
SELECT * FROM tbl_livro
WHERE Nome_livro LIKE '%S';
```

Livros que possuem a segunda letra m, não importando o que vem depois.

```SQL
SELECT * FROM tbl_livro
WHERE Nome_livro LIKE '_m%';
```

## REGEXP
Busca padrões baseados em expressão regular(padrão de caracteres).

[...] - Qualquer caracter único no intervalo ou conjunto especifícado.

Exemplos:
1. [a-d] (entre a e d)
2. [aeiou] (vogais);

[^...] - Qualquer caracterer único que **NÃO ESTEJA** no intervalo ou conjunto especifícado.

Exemplos:
1. [^a-d] (não esteja entre a e d)

2. [^aeiou] (qualquer string que comece com consoante)

^ - Início da string

$ - Fim da string

a|b|c - Alternação (a ou b ou c)

Todos os livros que não começam com vogais

```SQL
SELECT * FROM tbl_livro
WHERE Nome_livro
REGEXP '^[^aeiou]';
```

Que terminam com *us* ou *hand*
```SQL
SELECT * FROM tbl_livro
WHERE Nome_livro
REGEXP '[us]$|[hand]$'
```

Livros que começam com E ou D
```sql
SELECT * FROM tbl_livro
WHERE Nome_livro
REGEXP '^[ED]';
```

Livros que começam com 'dex'
```sql
SELECT * FROM tbl_livro
WHERE Nome_livro
REGEXP '^dex';
```

## DEFAULT (valor padrão)
Se nenhum valor for inseridornaquele campo, ele irá setar um valor padrão.

Criar uma coluna em uma tabela existente.

```sql
ALTER TABLE tbl_livro
ADD COLUMN data_inscricao DATE
DEFAULT '2020-10-01';
```

Modificar uma coluna que já existe
```SQL
ALTER TABLE tbl_livro
MODIFY COLUMN data_inscricao DATE
DEFAULT '1999-01-01';
```

Criar uma tabela já com o valor default
```sql
CREATE TABLE IF NOT EXISTS tbl_livro(
  id INT AUTO_INCREMENT PRIMARY KEY,
  nome VARCHAR(50) DEFAULT 'John Doe',
  INDEX(nome)
) AUTO_INCREMENTO = 10;
```

Caso queira remover, basta utilizar o ALTER TABLE com MODIFY mas não inserir o DEFAULT;
```sql
ALTER TABLE tbl_livro MODIFY COLUMN data_inscricao
```

## Backup do BD
Utilizar o mysqldump no terminal:

Fazer backup:
system mysqldump -u(user) root -p(para pedir o password) nome_banco > C:\Users\Danilo\Documents\db_biblioteca_backup.sql

Para restaurar backup:

Criar novo banco vazio
system mysql -u root -p banco_vazio_criado < C:\Users\Danilo\Documents\db_biblioteca_backup.sql

> No Windows: abrir a CLI do MySQL, utilizar o comando system mysqldump...

## GROUP BY
Usada pra agrupar registros em subgrupos baseados em colunas ou valores retornados por uma expressão.
```sql
SELECT colunas, função_agregação() FROM tabela
WHERE filtro
GROUP BY colunas
```
**Importante que tenha a função de agregação**

Exemplos:
Irá retonar o total de produtos vendidos por cidade.
```sql
SELECT Cidade, SUM(quantidade) FROM Vendas
GROUP BY Cidade;
```
</br>
Irá retornar o total de registros, mas retornando apenas uma cidade.(errado)

```sql
SELECT Colunas, COUNT(*) FROM Vendas;
```

</br>
Irá retornar o total de registros de cada cidade.(certo)

```sql
SELECT Colunas, COUNT(*) FROM Vendas
GROUP BY Cidade;
```
> Possuí o filtro *HAVING*, que funciona como o WHERE, mas para *GROUP BY*.

## HAVING
- Filtro de agrupamento.
- Usada para especificar condições de filtragem em grupos de registros ou agregações.
- Frequentemente usado em clásula GROUP BY para filtrar as colunas agrupadas.
- Similar ao *WHERE*, **mas aplicado ao GROUP BY AO INVÉS DO SELECT**.
- **Aceita função de agregação**.

```SQL
SELECT Coluna, Função_Agregação() FROM Tabela WHERE Filtro
GROUP BY Coluna HAVING Filtro_Agrupamento;
```

Exemplos:
1. Preciso fazer o agrupamento por cidade *GROUP BY*, já que possuem várias cidades.
2. Depois aplico o filtro no *GROUP BY* que é o *HAVING*.

Consulta agrupando os registros por cidade, onde a quantidade de itens vendidos são menores que 2500.

```SQL
SELECT Cidade, SUM(Quantidade) AS Total_Quantidade
FROM Vendas GROUP BY Cidade HAVING SUM(Quantidade) < 2500;
```

</br>

Irá me retornar apenas a primeira cidade que encontrar no registro, somando a quantidade de TODOS os registros(de todas as cidades). OU SEJA, ESTÁ ERRADO!!

```sql
-- Ao utilizar uma função de agregação, devo utilizar o agrupamento(GROUP BY) para evitar erros.

SELECT Cidade, Produto, SUM(Quantidade) AS Total_Vendido
FROM Vendas;
```

</br>

Consulta para agrupar por cidade os registros onde foram vendidos menos de 1500 teclados.

```sql
SELECT Cidade, Produto, SUM(Quantidade) AS Total_Vendido
FROM Vendas WHERE Produto = 'Teclado'
GROUP BY Cidade HAVING SUM(Quantidade) < 1500;
```

## VIEWS
- Tabela virtual gerada à partir de um conjunto/resultado de consultas.
- Possuí linhas e colunas, e aceita comandos SQL como qualquer outra tabela.
- Posso realizar consultas em cima das VIEWS, para facilitar em consultas complexas.
- Mostra os resultados atualizados, já que o BD recria os dados a cada consulta na view.

```sql
CREATE VIEW [Nome_view] AS SELECT Colunas
FROM Tabela WHERE Filtro;
```

```sql
CREATE VIEW vw_LivroAutores
AS SELECT tbl_Livro.Nome_livro AS Livro, tbl_Autor.Nome_Autor AS Autor 
FROM tbl_Livro INNER JOIN tbl_Autor
ON tbl_Livro.ID_Autor = tbl_Autor.ID_Autor 
```
## Atualizar VIEWS
```SQL
ALTER VIEW vw_LivroAutores
AS SELECT tbl_Livro.Nome_Livro AS Livro,
tbl_Livro.Preco_livro AS Preço,
tbl_Autor.Nome_Autor AS Autor 
FROM tbl_Livro
INNER JOIN tbl_Autor
ON tbl_Livro.ID_Autor = tbl_Autor.ID_Autor;
```

## JOIN
- Usado para combinar dados de duas ou mais tabelas que se relacionam.

**Existem vários tipos de JOIN, mas o mais utilizados:**
### INNER JOIN
Retorna quando houver ao menos dado em ambas as tabelas(correspondencia em ambas as tabelas).

### OUTER JOIN
Retorna mesmo quando NÃO há correspondencia em uma das tabelas(ou ambas).
Dividi-se em: LEFT JOIN, RIGHT JOIN e FULL JOIN.

```sql
SELECT Colunas FROM Tabela1
INNER JOIN Tabela2 ON Tabela1.Coluna = Tabela2.Coluna; 
```

> ON chave_primaria = chave_estrangeira

Exemplos:

Consulta e cruza as tabelas onde o ID_Editora ocorre em ambas as tabelas e retorna apenas os registros que o nome da editora começa com S.

```sql
SELECT L.Nome_Livro, E.Nome_Editora
FROM tbl_Livro AS L
INNER JOIN tbl_Editora AS E
ON L.Id_Editora = E.Id_Editora
WHERE E.Nome_Editora REGEXP '^S';
```

Consulta e cruza os dados de todas as tabelas que fazem relação com tbl_livro.

**A tabela mais importante vai no FROM**
```SQL
SELECT L.Nome_Livro AS Livro, A.Nome_Autor AS Autor, E.Nome_Editora AS Editora
FROM tbl_Livro AS L
INNER JOIN tbl_Autor AS A ON L.Id_Autor = A.Id_Autor
INNER JOIN tbl_Editora AS E ON L.Id_Editora = E.Id_Editora;
```

Imagem para representar o funcionamento do INNER JOIN:
<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/inner_join_a1lh1mKyL.png" 
  alt="INNER JOIN"
  />
</p>
<p align="center"><i>INNER JOIN</i></p>

fonte: https://www.youtube.com/watch?v=C_OpAzDImfI&list=PLucm8g_ezqNrWAQH2B_0AnrFY5dJcgOLR&index=32

## OUTER JOINS (LEFT/RIGHT/FULL JOIN)
### LEFT JOIN
Retorna todas as linhas da tabela à esquerda, mesmo que não haja correspondencia na tabela da direita.

### RIGHT JOIN
Retorna todas as linhas da tabela à direita, mesmo que não haja correspondencia na tabela da direita.

### FULL JOIN
Retorna linhas quando houver uma correspondência em qualquer uma das tabelas, **é a combinação do LEFT e RIGHT JOIN**

```sql
SELECT coluna FROM tabela_esquerda 
LEFT (OUTER) JOIN tabela_direita
ON tabela_esquerda.coluna1 = tabela_direita.coluna2;
```
</br>

Consulta que irá me retornar todas os dados da tabela Autor que fazem correspondencia com a tabela de Livro, inclusive os que não fazem(autor que não possuí livro cadastrado)

Caso eu inverta a ordem das tabelas, irá mostrar apenas os livros que possuem autor, pois não existe livro sem autor publicado.
```sql
SELECT * FROM tbl_autor
LEFT JOIN tbl_livro
ON tbl_autor.id_autor = tbl_livro.id_autor
```
> Cada tabela é uma palma da mão, a tabela do FROM vai subir para a outra tabela mescar, LEFT diz para qual lado irá mescar e o lado da tabela do FROM, no caso esquerdo.

Imagem para representar o funcionamento do LEFT (OUTER) JOIN:
<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/leftjoinm_hHlQowDt7.png" 
  alt="LEFT JOIN"
  />
</p>
<p align="center"><i>LEFT JOIN</i></p>

fonte: https://www.youtube.com/watch?v=4m3HNtsFRoI&list=PLucm8g_ezqNrWAQH2B_0AnrFY5dJcgOLR&index=33

### Excluir correspondencias com o LEFT JOIN
```sql
SELECT * FROM tabela_esquerda
LEFT JOIN tabela_direita
ON tabela_esquerda.coluna1 = tabela_direita.coluna1
WHERE tabela_direita.coluna1 IS NULL;
```
</br>

Consulta que irá retornar apenas os autores que não tiver livros publicados.
```sql
SELECT * FROM tbl_Autor
LEFT JOIN tbl_Livro ON tbl_Autor.Id_Autor = tbl_Livro.Id_Livro
WHERE tbl_Livro.Id_livro IS NULL;
```

Imagem para representar o funcionamento do LEFT (OUTER) JOIN excluindo a correspondencia:
<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/left_0xCpW2RnK.png" 
  alt="LEFT JOIN excluindo a correspondencia"
  />
</p>
<p align="center"><i>LEFT JOIN excluindo a correspondencia</i></p>

### RIGHT JOIN
Mesma funcionalidade do LEFT JOIN, apenas inverte a ordem das colunas.

```sql
SELECT * FROM tabela_direita
RIGHT JOIN tabela_esquerda
ON tabela_direita.coluna1 = tabela_esquerda.coluna2;
```

> Cada tabela é uma palma da mão, a tabela do FROM vai subir para a outra tabela mescar, RIGHT diz para qual lado irá mescar e o lado da tabela do FROM, no caso direito.

Consulta para retornar todas as editoras, inclusive as que não publicaram livros
```sql
SELECT * FROM tbl_Livro
RIGHT JOIN tbl_Editora
ON tbl_Editora.id_editora = tbl_Livro.id_editora;
```

Consulta para retornar apenas as editoras que não publicaram livro
```sql
SELECT * FROM tbl_Livro AS L
RIGHT JOIN tbl_Editora AS E
ON E.id_editora = L.id_editora
WHERE L.id_livro IS NULL;
```

Imagem para representar o funcionamento do LEFT (OUTER) JOIN excluindo a correspondencia:
<p align="center">
  <img src="https://ik.imagekit.io/xfddek6eqk/right_join_maDSVHYI7.png" 
  alt="RIGHT JOIN"
  />
</p>
<p align="center"><i>RIGHT JOIN</i></p>

## Concatenação de string com  CONCAT, IFNULL E COALESCE
Concaternar strings usando a função CONCAT.

```sql
CONCAT(string | coluna, string | coluna, ...)
```

```sql
SELECT CONCAT ('Danilo ', 'Bandeira') AS 'Nome Completo';
```

```sql
SELECT CONCAT (Nome_autor, ' ', Sobrenome_Autor) AS 'Nome Completo'
FROM tbl_autor;
```
> Para que o nome da coluna não mostre 'CONCAT...', devo utilizar o AS(ALIAS).

</br>

**Se a string for concatenada com NULL, será retornado apenas NULL.**
```sql
CREATE TABLE IF NOT EXISTS test_nulo(
  id SMALLINT PRIMARY KEY AUTO_INCREMENT,
  item VARCHAR(50),
  quantidade SMALLINT NULL
);

INSERT INTO test_nulo(item, quantidade) VALUES ('Mouse', 10);
INSERT INTO test_nulo(item, quantidade) VALUES ('Teclado', NULL);

-- Irá me retornar normalmente
SELECT CONCAT('A quantidade de ', item, ' é ', quantidade) AS Resultado
FROM test_nulo
WHERE item = 'Mouse';

-- Irá retornar apenas NULL
SELECT CONCAT('A quantidade de ', item, ' é ', quantidade) AS Resultado
FROM test_nulo
WHERE item = 'Teclado';
```

**IFNULL**

Para evitar esse tipo de comportamento, podemos utilizar a função **IFNULL** dentro do **CONCAT**:

```sql
IFNULL(coluna, valor caso seja null)
```

```sql
SELECT CONCAT('A quantidade de ', item, ' é ', IFNULL(quantidade, 0)) AS Resultado
FROM test_nulo
WHERE item = 'Teclado';
```

**COALESCE**

Retornará o primeiro valor não-nulo encontrado em seus argumentos.

```SQL
COALESCE(valor1, valor2, ...)
```

Irá verificar o primeiro valor *NULL*, mas não vai retornar por ser *NULL*.

Irá verificar o segundo valor, como a quantidade de teclado é *NULL*, ele irá pular para a próxima verificação... até chegar no *0*, que é um valor não-nulo, e irá retornar ele.

```sql
SELECT CONCAT('A quantidade de ', item, ' é ', COALESCE(NULL, quantidade, NULL, 0)) AS Resultado
FROM test_nulo
WHERE item = 'Teclado';
```

## Operações aritméticas
É possível realizar operações matematicas simples nos valores de uma coluna e retornar resultados em uma coluna calculada. Para isso, usamos os operadores matématicos comuns:

- (+) soma
- (-) subtração
- (/) divisão
- (*) multiplicação
- (% ou MOD) módulo ou resto da divisão
- (DIV) divisão inteira

Retorna o valor dessa multiplicação.
```sql
SELECT 2 * 2 AS Multiplicação;
```
</br>

Retorna as colunas livro, preço de cada unidade, seguido da coluna que retornará o preço de 5 unidades desse livro.
```sql
SELECT Nome_livro AS Livro,
Preco_livro AS 'Preço unidade',
Preco_livro * 5 AS 'Preço de 5 unidade'
FROM tbl_livro;
```
</br>

Irá retornar 6.0000
```sql
SELECT 2 * 9 / 3;
```
</br>

Para arredondar as casas decimais, posso utilizar a função *TRUNCATE(valor, precisão)*

```sql
SELECT TRUNCATE(2 * 9 / 3, 2);
```

</br>

Para divisão inteira, posso utilizar a função *x DIV y*

Para pegar o resto da divisão, posso utilizar a função *x MOD y*

## Funções matemáticas
É possível utilizar funções matemáticas para retornar valores de uma coluna em outra coluna com valores já calculados

- TRUNCATE(x, y) valor float x com y casas decimais
- CEILING() arredonda pra cima
- FLOOR() arredonda pra baixo
- PI() retorna o valor de pi
- POW(x, y) retorna o valor x elevado a y
- SQRT() raíz quadrada
- SIN() seno de um número dado em radianos
- HEX() hexadecimal de um valor decimal

## Funções e Procedimentos
- Funções e procedimentos são rotinas que serão armazenadas, para que quando aja necessidade, basta chama-lás pelo nome para executar.
- São similares, mas com invocação diferente.
- São invocadas de maneira diferente também.
- Consigo aplicar com inner join ou qualquer outra técnica que aprendi.

```sql
CREATE FUNCTION nome_função(parâmetros)
RETURNS tipos_de_dados_retornados
código_função;
```

> Caso não funciona, executar `SET GLOBAL log_bin_trust_function_creators = 1;`

Invocando uma função
```sql
SELECT nome_função(parâmetros);
```

Criando função
```sql
CREATE FUNCTION fnc_test(a DECIMAL(11, 2), b INT) RETURNS INT
RETURN a * b;
```
Invocando a função *fnc_test*
```sql
SELECT fnc_test(12. 5, 6);
```

Aplicando em uma tabela
```sql
SELECT Nome_livro AS Livro, fnc_test(Preco_livro, 6) AS 'Valor de 6 unidades'
FROM tbl_livro
WHERE id_livro = 2;
```

Excluindo função
```sql
DROP FUNCTION nome_função;
```
## Procedimentos armazenados(Stored procedures)

São uma sub-rotinas disponíveis para aplicações que acessem o SGBD.

Para que usar?
- Para validação de dados
- Controle de acesso
- Execução de declarações SQL complexas
- E outras situações

Criar procedimento
```sql
CREATE PROCEDURE nome_procedimento(parâmetros)
declarações;
```
> Ou posso fazer a criação clicando com o botão direito em *Stored Procedures*, onde ele irá criar já a estrutura fazendo uso do bloco *BEGIN* e *END*.

Invocando procedimento
```sql
CALL nome_procedimento(parâmetros);
```

Deletando procedimento
```sql
DROP PROCEDURE nome_procedimento;
```

Criando meu procedimento que irá retornar o valor de um livro, passando o seu id quando chamar o procedimento.
```sql
CREATE PROCEDURE verPreco(idLivro SMALLINT)
SELECT CONCAT('O preço do livro é ', Preco_livro) AS Preço
FROM tbl_livro
WHERE Id_livro = idLivro;
```

Chamando o procedimento e passando o id do livro pelo parâmetro.
```sql
CALL verPreco(1);
```

Deletando o procedimento.
```sql
DROP PROCEDURE verPreco;
```
## Blocos BEGIN... END
- Delimita um escopo de uma *function* ou *stored-procedures*.
- Cada declaração(SELECT...) possuí um delimitador(;)
- Um SELECT, DROP e afins são declarações.
- BEGIN END pode ser aninhado, como um if.
- **Delimitador(;) pode causar um problema. Para evitar isso, devemos utilizar um comando chamado *DELIMITER* para criar um delimitador diferente do ponto e vírgula**

Criando função utilizando BEGIN...END
```sql
SET GLOBAL log_bin_trust_function_creators = 1;

DELIMITER $$
CREATE FUNCTION aumenta_preco(valor DECIMAL(11, 2), taxa DECIMAL(11, 2)) RETURNS DECIMAL(11, 2)
BEGIN
  RETURN valor * taxa;
END
DELIMITER ;
```

Chamando função
```sql
SELECT aumenta_preco(22.3, 10.00) AS Resultado;
```

Criando uma procedure com o bloco BEGIN...END e chamando.
```sql
DELIMITER //
CREATE PROCEDURE verPreco(idLivro SMALLINT)
BEGIN
  SELECT CONCAT('O valor do livro é: ', Preco_livro) AS Preço
  FROM tbl_livro
  WHERE id_livro = idLivro;
  SELECT 'Procedimento realizado com sucesso!';
END//
DELIMITER ;

-- Chamando o procedure
CALL verPreco(1);
```
Irão abrir duas janelas de resultado: Uma com o primeiro SELECT e outra com o segundo SELECT. **Executou as duas por causa do bloco BEGIN...END e ELAS FORAM SEPARADAS POR ;**.

## Parâmetros em Stored Procedures(procedimentos armazenados)
Existem três parâmetros:
- IN
- OUT
- INOUT

### IN
- **É o modo padrão.** Quando você define um parâmetro IN em um SP, o programa chamador tem que passar um argumento ao procedimento armazenado. Essa passagem de parâmetros é do tipo passagem por valor, **portanto o valor do parâmetro fora do procedimento armazenado permanece inalterado**.

- São semelhantes a parâmetros de função.

- **É IN pois eu forneço valor para ele.**

Exemplo: Se eu tiver uma variável ou uma coluna com o valor X e passar essa variável/coluna com valor IN para um stored procedures... **esse valor será passado e retornado, mas seu valor original será mantido**.

### OUT
- O valor passado por parâmetro é setado para NULL. Ou seja, a diferença entre IN e OUT é que no IN o valor não é alterado(fica com valor original) e no OUT será NULL.

- **É OUT pois eu NÃO forneço valor inicial, mas dentro do procedimento ele é alterado.**

### INOUT
- Trata-se de uma combinação dos parâmetros IN e OUT.
- Isso significa que o programa chamador deve passar argumentos e o procedimento armazenado pode modificar o parâmetro INOUT e repassar o novo valor de volta ao programa chamador.
- **PORTANTO, uma referência à variável externa é passada ao procedimento.**
- Também conhecido como **Passagem por referência.**

Ao chamar esse stored procedure, eu devo passar o nome da editora... então ele fará uma consulta pela tabela de livro e cruzar com a tabela de editora para recuperar os dados necessários... que irá me retornar apenas os livros(nome do livro e editora) da editora passada por parâmetro.
```sql
DELIMITER $$
CREATE PROCEDURE editora_livro(IN editora VARCHAR(50))
BEGIN
  SELECT L.Nome_livro, E.Nome_editora
  FROM tbl_livro AS L
  INNER JOIN tbl_editora AS E
  ON L.Id_editora = E.Id_editora
  WHERE E.Nome_editora = editora;
END $$
DELIMITER ;

CALL editora_livro('Celestial');
```
> Não altera o valor da editora. O nome disso é **passagem por valor**.

#### Criando variável
Posso criar uma variável(sempre começa com @) e atribuir o nome da editora dessa forma:

```sql
SET @minhaeditora = 'Celestial';
CALL editora_livro(@minhaeditora);
```

### Exemplo stored procedure com parâmetro IN
Busca o livro com mesmo id e aumenta o seu valor
```sql
DELIMITER $$
CREATE PROCEDURE aumenta_preco(IN codigo INT, taxa DECIMAL(11, 2))
BEGIN
  UPDATE tbl_livro
  SET Preco_livro = tbl_livro.Preco_livro + (tbl_livro.Preco_livro * 2 / 100)
  WHERE Id_livro = codigo;
END $$
DELIMITER ;

SET @taxa = 10;
SET @codigoLivro = 2;

CALL aumenta_preco(@codigoLivro, @taxa);
```
> **O código do livro não é alterado, pois é um parâmetro IN.**

### Exemplo stored procedure com parâmetro OUT
O valor da variável livro entra com valor NULL, recebe o valor do SELECT e retorna com o valor da seleção. **Ou seja, trata-se de uma passagem por referência.**

**Por que passagem por referência?** Acredito que o valor não existe, então é passado para o procedimento e tem seu valor alterado. Ou seja, alterei o valor do valor que foi passado **que na verdade era null, que é apenas referência de onde aguardar o valor**. Basta revisar esse conceito em 17:40 : https://www.youtube.com/watch?v=STetVKOhLkI&list=PLucm8g_ezqNrWAQH2B_0AnrFY5dJcgOLR&index=39

```sql
DELIMITER //
CREATE PROCEDURE test_out(IN codigo INT, OUT livro VARCHAR(50))
BEGIN
  SELECT Nome_livro
  INTO livro
  FROM tbl_livro
  WHERE id_livro = codigo;
END //
DELIMITER ;

CALL test_out(2, @livro);

SELECT @livro;
```
### Exemplo stored procedure com parâmetro INOUT
Irá receber uma variável que tem um valor inicial de 10, depois irá alterar o valor dela com base no seu valor inicial multiplicado a taxa... e o resultado irá guardar na variável inicial, alterando seu valor.

**É IN pois eu forneço valor para ele. E é OUT pois o valor alterado é armazenado dentro dele.**

```sql
DELIMITER //
CREATE PROCEDURE aumento(INOUT valor DECIMAL(11, 2), taxa DECIMAL(11, 2))
BEGIN
  SET valor = valor + (valor * taxa / 100);
END //
DELIMITER ;

SET @valor = 10;
SELECT @valor; -- irá me retornar 10

CALL aumento(@valor, 50);
SELECT @valor; -- irá me retornar 15

```

## Passagem por referência
Basta imaginar como na matrix:

O personagem está ligado a um computador por meio de um cabo. Qualquer coisa que o personagem sofre no **mundo virtual**, é refletido no corpo dele no **mundo real**, **pois o mundo virtual tem a referência do corpo dele do mundo real.**

## Escopo das variáveis
- Diz respeito aos locais onde a variável "existe", ou seja, onde ela pode ser acessada.

### Níveis de escopo
- Global (acessíveis de qualquer lugar)
- Sessão (variáveis @ e de sistema)
- Parâmetros (nível de rotina, criadas quando a rotina é chamada e destruída quando a rotina encerra)
- Local (limitadas ao bloco BEGIN...END onde foram criadas)

### Local
- Pode ser criada em uma function ou procedure utilizando *DECLARE*.
- Posso inicializar com um valor ou não.
- Ficam disponíveis para o BEGIN...END filhos.
- Seu valor não fica acessível depois que a function/procedure deixa de existir.

Criar variável local
```sql
DECLARE nome_variavel1 tipo, nome_variavel2 tipo
[DEFAULT valor_padrão]
```

Posso setar valor utilizando o *SET* ou *SELECT...INTO*.

```sql
DELIMITER //
CREATE FUNCTION calcula_desconto(idLivro SMALLINT, valorDesconto DECIMAL(11, 2))
RETURNS DECIMAL(11, 2) DETERMINISTIC
BEGIN
  DECLARE preco DECIMAL(11, 2);
  SELECT Preco_livro FROM tbl_livro
  WHERE id_livro = idLivro INTO preco;
  RETURN preco - valorDesconto;
END //
DELIMITER ;

SET @idLivro = 1;

SELECT Preco_livro FROM tbl_Livro
WHERE id_livro = @idLivro;

SELECT calcula_desconto(@idLivro, 10.00);
```

## Blocos condicionais IF e CASE
- Utilizado para testar condições.
- Se tiver muitas comparações com a mesma variável, utilizar o CASE.

Existem dois blocos básicos:
- IF ELSEIF ELSE END IF
- CASE WHEN THEN ELSE END CASE

Sintaxe do IF
```sql
IF condição THEN lista_declarações
  [ELSEIF condição THEN lista_declarações]
  ...
  [ELSE lista_declarações]
END IF;
```

Sintaxe do CASE
```sql
CASE valor_referência
  WHEN valor_comparado THEN lista_declarações
  WHEN valor_comparado THEN lista_declarações
  ...
  ELSE lista_declarações
END CASE;
```
Criar função para calcular imposto, utilizando IF ELSEIF ELSE END IF:
```sql
DELIMITER //
CREATE FUNCTION calcula_imposto(salario DEC(11, 2)) RETURNS DEC(11, 2) DETERMINISTIC
BEGIN
  DECLARE valor_imposto DEC(11, 2);
  IF salario < 1000 THEN SET valor_imposto = 0;
  ELSEIF salario < 2000 THEN SET valor_imposto = salario * 0.15;
  ELSEIF salario < 3000 THEN SET valor_imposto = salario * 0.22;
  ELSE SET valor_imposto = salario * 0.27;
  END IF;
  RETURN valor_imposto;
END //
DELIMITER ;
```

Criar função para calcular imposto, utilizando CASE WHEN THEN ELSE END CASE:
```sql
DELIMITER //
CREATE FUNCTION calcula_imposto_case(salario DEC(11, 2)) RETURNS DEC(11, 2) DETERMINISTIC
BEGIN
  DECLARE valor_imposto DEC(11, 2);
  CASE
    WHEN salario < 1000 THEN SET valor_imposto = salario * 0;
    WHEN salario < 2000 THEN SET valor_imposto = salario * 0.15;
    WHEN salario < 3000 THEN SET valor_imposto = salario * 0.22;
    ELSE SET valor_imposto = salario * 0.27;
  END CASE;
  RETURN valor_imposto;
END //
DELIMITER ;
```
## Comando SHOW, DESCRIBE e mysqlshow
- Utilizados para acessar os metadados no meu sistema.
- Metadados são dados sobre dados, ou seja, informações sobre objetos do sistema, banco de dados, tabelas do banco, colunas do banco...
- **Utilizar a CLI do mySQL.**

### SHOW
2. Digitar na CLI: `HELP SHOW`
3. `SHOW DATABASES`;
4. `USE db_biblioteca`; `SHOW TABLES`; `SHOW CREATE TABLE tbl_livro`;
5. `SHOW CREATE PROCEDURE nome_procedimento`; `SHOW CREATE FUNCTION nome_func`;
6. `SHOW [ FULL ] COLUMNS FROM nome_tabela`; *[] significa que é opcional*
7. `SHOW COLUMNS FROM tbl_livro LIKE "I%"`; *Mostrar as que começam com I*
8. `SHOW COLUMNS FROM tbl_Livro WHERE TYPE LIKE "varchar%"`; *Colunas onde o tipo é varchar, independente do tamanho*
9. `SHOW GRANTS FOR root@localhost`; *Permissões de acesso do usuário root no localhost*
10. `SHOW GRANTS FOR CURRENT_USER`;

### DESCRIBE
- Atalho para o comando `SHOW COLUMNS FROM`
- Posso abreviar para `DESC`
- Não suporta as cláusulas `WHERE` ou `LIKE`

### mysqlshow
- Utilizar o shell do mySQL

Irá mostrar todos os databases.
```bash
mysqlshow -u usuario -p senha
```

Mostrar as todas as tabelas de um database.
```bash
mysqlshow -u usuario -p senha nome_banco
```

Mostrar as todas colunas da tabela de um database, mas caso a tabela tenha _ no nome, não irá funcionar corretamente.
```bash
mysqlshow -u usuario -p senha nome_banco nome_tabela
```
**Por utilizar _ no nome da tabela, o shell irá reconhecer como um Wildcard. Par que mostra corretamente todas as colunas, utilizar:**
```bash
mysqlshow -u usuario -p senha nome_banco nome_tabela %
```

Irá trazer todas as tabelas do banco que começam com *t*, juntamente com a contagem de linhas e colunas(primeiro *v* para colunas, segundo *v* para linhas) 
```bash
mysqlshow -vv -u usuario -p senha nome_banco 't*'
```

Irá trazer informações sobre a coluna de uma tabela especifica do banco.
```bash
mysqlshow -u usuario -p senha nome_banco nome_tabela nome_coluna
```
## Estruturas de repetição LOOP, REPEAT, WHILE e ITERATE
### Bloco iterativo
- Bloco de código que executa comandos repetidamente até que a condição de parada seja satisfeita.
- Pode ser aninhado com outros blocos iterativos.
- Importantes em *functions* e *triggers*.

No mySQL existem:
- LOOP
- REPEAT
- WHILE

## LOOP

```sql
[nome_loop:] LOOP
declarações
END LOOP [nome_loop];
```

Exemplo:
```sql
DELIMITER //
CREATE PROCEDURE acumula(limite INT, OUT resultado INT)
BEGIN
  DECLARE contador INT DEFAULT 0;
  DECLARE soma INT DEFAULT 0;
  loop_test: LOOP
    SET contador = contador + 1;
    SET soma = soma + contador;
    IF contador >= limite THEN LEAVE loop_test;
    END IF;
  END LOOP loop_test;
  SET resultado = soma;
END //
DELIMITER ;

CALL acumula(10, @resultado);

SELECT @resultado;
```
> Declaro duas variáveis *soma* e *contador*, crio o loop e incremento essas duas variáveis. Faço a comparação do contador com o valor *limite* e caso seja satisfeita, vai sair do loop e vai exibir o valor da *soma*.
> LEAVE indica que deve sair do bloco/loop. **Se não tiver, será um loop infinito.**
> Caso o valor 0 seja passado ao *limite*, ele irá retornar 1(valor errado).

## REPEAT
- Semelhante ao *DO WHILE*, já que ele verifica a **condição** apenas depois de executar os códigos.

```sql
[nome_repeat:] REPEAT
declarações
UNTIL condicação
END REPEAT [nome_repeat];
```

Exemplo:
```sql
DELIMITER //
CREATE PROCEDURE acumula_repeat (limite TINYINT UNSIGNED)
BEGIN
  DECLARE contador TINYINT UNSIGNED DEFAULT 0;
  DECLARE soma INT DEFAULT 0;
  myRepeat: REPEAT
    SET contador = contador + 1;
    SET soma = soma + contador;
      UNTIL contador >= limite
  END REPEAT myRepeat;
  SELECT soma;
END //
DELIMITER ;

CALL acumula_repeat(5); -- resultado 15

CALL acumula_repeat(0); -- resultado errado
```

**UNSIGNED(sem sinal) aceita apenas valores positivos.**

Resolvendo o problema quando o usuário passa valores menos que 1 no *REPEAT*, já que o teste dele é depois de executar outros comandos.
```sql
DELIMITER //
CREATE PROCEDURE acumula_repeat2(limite TINYINT UNSIGNED)
main: BEGIN
  DECLARE contador TINYINT UNSIGNED DEFAULT 0;
  DECLARE soma INT DEFAULT 0;

  IF limite < 1 THEN
    SELECT 'O valor passado deve ser maior que 0.' AS Error;
    LEAVE main;
  END IF;

  myRepeat: REPEAT
    SET contador = contador + 1;
    SET soma = soma + contador;
  UNTIL contador >= limite
  END REPEAT myRepeat;

  SELECT soma;

END //
DELIMITER ;

CALL acumula_repeat2(5);
CALL acumula_repeat2(0);
```
## WHILE
- A condição é testada antes de executar o código. Ou seja, pode não executar nenhum código caso a condição não seja satisfeita.

```sql
[nome_while:] WHILE condicao DO
END WHILE [nome_while];
```

Exemplo:
```sql
DELIMITER //
CREATE PROCEDURE acumula_while (limite TINYINT UNSIGNED)
BEGIN
  DECLARE contador TINYINT UNSIGNED DEFAULT 0;
  DECLARE soma INT DEFAULT 0;
  myWhile: WHILE contador < limite DO
    SET contador = contador + 1;
    SET soma = contador + soma;
  END WHILE myWhile;
  SELECT soma;
END //
DELIMITER ;

CALL acumula_while(5);
CALL acumula_while(0);
```

## ITERATE
- **Funciona como um *JUMP*.**
- Significa "inicie o loop novamente à partir desse ponto".
- **É declarado e funciona apenas dentro de LOOP, REPEAT ou WHILE.**

Iterate em um LOOP:
```sql
DELIMITER //
CREATE PROCEDURE acumula_iterate (limite TINYINT UNSIGNED)
BEGIN
  DECLARE contador TINYINT UNSIGNED DEFAULT 0;
  DECLARE soma INT UNSIGNED DEFAULT 0;
  myLoop: LOOP
    SET contador = contador + 1;
    SET soma = contador + soma;
    IF contador < limite THEN
      ITERATE myLoop;
    END IF;
    LEAVE myLoop;
  END LOOP myLoop;
  SELECT soma;
END//
DELIMITER ;

CALL acumula_iterate (10);
```

Iterate em um WHILE:

```sql
DELIMITER $$
CREATE PROCEDURE numeros_pares (limite TINYINT UNSIGNED)
BEGIN
  DECLARE contador TINYINT UNSIGNED DEFAULT 0;
  myWhile: WHILE contador < limite DO
    SET contador = contador + 1;
    IF MOD(contador, 2) THEN
      ITERATE myWhile;
    END IF;
    SELECT CONCAT(contador, ' é um valor par') AS valor;
  END WHILE myWhile;
END $$
DELIMITER ;

CALL numeros_pares (10);
```

> O resultado do *MOD* de um valor dividido por 2 será 0 ou 1. Caso seja 1, o *IF* irá interpretar como *TRUE*, caso 0 será será *FALSE*.

Iterate em um REPEAT:

```sql
DELIMITER $$
CREATE PROCEDURE numeros_par (limite TINYINT UNSIGNED)
BEGIN
  DECLARE contador TINYINT UNSIGNED DEFAULT 0;
  myRepeat: REPEAT
    SET contador = contador + 1;
    IF MOD(contador, 2) THEN
      ITERATE myRepeat;
    END IF;
    SELECT CONCAT(contador, ' é um valor par') AS valor;
    UNTIL contador >= limite
  END REPEAT myRepeat;
END $$
DELIMITER ;

CALL numeros_par(10);
```
## TRIGGERS(gatilhos)
- Associado a uma tabela.
- **Ocorre quando um comando *DML -  Data Manipulation*(INSERT, UPDATE, DELETE) é executado.**

Principais usos dos *TRIGGERS*:
- Verificar integridade dos dados
- Validação dos dados
- Rastreamento e registro de logs de atividades nas tabelas
- Arquivamento de registros excluídos

- Um *TRIGGER* é associado em uma tabela.
- Armazenado no BD como um arquivo separado.
- Não são chamados diretamente, são invocados automaticamente.

Sintaxe do *TRIGGER*:
```SQL
CREATE TRIGGER nome timing operacao
ON tabela_que_vai_agir
FOR EACH ROW
declarações
```
timing: BEFORE | AFTER
operação: INSERT | UPDATE | DELETE

```sql
CREATE TRIGGER myTrigger BEFORE INSERT -- timing e operação
ON tbl_Livro -- tabela ao qual o trigger será associado
FOR EACH ROW -- para cada linha inserida
```

Exemplos:
```SQL
CREATE TABLE IF NOT EXISTS produto(
  id_produto INT NOT NULL AUTO_INCREMENT,
  nome_produto VARCHAR(45) NULL,
  preco_normal DECIMAL(11, 2) NULL,
  preco_desconto DECIMAL(11, 2) NULL,
  PRIMARY KEY(id_produto)
);


DELIMITER $$
CREATE TRIGGER tr_desconto BEFORE INSERT
ON produto
FOR EACH ROW
BEGIN
  SET NEW.preco_desconto = (NEW.preco_normal * 0.88);
END $$
DELIMITER ;

INSERT INTO produto(nome_produto, preco_normal) VALUES ('Chocolate', 1.99);

SELECT * FROM produto;
```

</br>

```sql
CREATE TABLE IF NOT EXISTS produto(
  id_produto INT NOT NULL AUTO_INCREMENT,
  nome_produto VARCHAR(45) NULL,
  preco_normal DECIMAL(11, 2) NULL,
  preco_desconto DECIMAL(11, 2) NULL,
  PRIMARY KEY(id_produto)
);


DELIMITER $$
CREATE TRIGGER tr_desconto BEFORE INSERT
ON produto
FOR EACH ROW
BEGIN
  IF NEW.preco_desconto IS NULL THEN
    SET NEW.preco_desconto = NEW.preco_normal * 0.90;
  END IF;
END $$
DELIMITER ;

INSERT INTO produto(nome_produto, preco_normal) VALUES ('Chocolate', 1.00);
INSERT INTO produto(nome_produto, preco_normal, preco_desconto) VALUES ('Chiclete', 1.00, 0.50);

```
## Gerenciamento de usuários na linha de comando - CREATE USER, SET PASSWORD, RENAME PASSWORD, DROP USER

1. Abrir o terminal mySQL
2. Digitar `SELECT User, Host FROM mysql.user;`. Esses dados vem de uma tabela interna.

### CREATE USER
```bash
$ mysql> CREATE USER nomeUsuario@host IDENTIFIED BY 'senha';
```
Caso eu queira que o usuário posso logar de qualquer host, basta não utilizar o @host
```bash
$ mysql> CREATE USER nome IDENTIFIED BY 'senha';
```

Caso eu queira criar um usuário sem senha, basta retirar o *IDENTIFIED BY* 
```bash
$ mysql> CREATE USER nome@host;
```

### ALTER PASSWORD // SET PASSWORD
**No mysql database server version 5.7.6 or newer.**
```bash
$ mysql> ALTER USER 'nome'@'localhost' IDENTIFIED BY 'senha';
```

**No mysql database server version 5.7.5 or older.**
```bash
$ mysql> SET PASSWORD FOR 'user-name-here'@'hostname' = PASSWORD('new-password');
```

### RENAME USER
```bash
$ mysql> RENAME USER nome@host TO novoNome@host;
```
**Deve ser passado o host, caso contrário, ele irá alterar o host do *USER*.**

### DROP USER
```bash
$ mysql> DROP USER nome@host;
```

## Definindo privilégios de acesso com GRANT e REVOKE
Irá mostrar o que o usuário tem permissão e em qual lugar(se é em todos os bancos ou afins)

```bash
$ mysql > SHOW GRANTS FOR nome@host;
```

Existe vários *roles*, alguns deles são:

Privilégios para trabalhar com dados
| **PRIVILÉGIO** | **DESCRIÇÃO** |
| :-----: | :-----: |
|INSERT|inserir dados em uma tabela|
|UPDATE|atualizar dados em uma tabela|
|DELETE|deletar dados em uma tabela|
|EXECUTE|executar funções e procedimentos armazenados|
|SELECT|efetuar consultas em uma tabela|

Privilégios para modificar a estrutura do banco de dados
| **PRIVILÉGIO** | **DESCRIÇÃO** |
| :-----: | :-----: |
|CREATE|criar tabela ou banco de dados|
|ALTER|modificar uma tabela|
|DROP|excluir uma tabela ou banco de dados|
|CREATE VIEW|criar exibições/tabelas virtuais|
|TRIGGER|criar ou excluir uma trigger em uma tabela|
|INDEX|criar ou excluir um indíce|
|CREATE ROUTINE|criar uma função ou um procedimento armazenado|
|ALTER ROUTINE|alterar uma função ou um procedimento armazenado|


Privilégios administrativos
| **PRIVILÉGIO** | **DESCRIÇÃO** |
| :-----: | :-----: |
|CREATE USER|criar contas de usuários|
|SHOW DATABASES|ver os nomes dos bancos no servidor|
|SHUTDOWN|desligar o servidor|
|RELOAD|recarregar as tabelas que armazenam os privilégios dos usuários do BD. assim ela são atualizadas se tiverem sido alteradas|
|ALL|todos os privilégios disponíveis em um determinado nível, exceto GRANT OPTION|
|GRANT OPTION|permite dar privilégios a outros usuários|
|USAGE|não altera privilégios; usado apenas para tarefas administrativas na conta do usuário|

### Níveis de privilégios
- GLOBAL - acesso a todas as tabelas de todos os bancos de dados; mostra dessa forma na CLI `*.*`
- DATABASE - acesso a todas as tabelas de um banco específico
- TABLE - acesso a todas as colunas de uma tabela
- COLUMN - acesso a colunas especificadas de uma tabela

**As informações de privilégio ficam armazenadas em tabelas especiais chamadas *grant tables***

| **TABELA** | **DESCRIÇÃO** |
| :-----: | :-----: |
|user|armazena nomes e senhas de todos os usuários do servidor. também armazena os privilégios globais que são aplicados a todos os bancos de dados do servidor|
|db|armazena privilégios dos bancos de dados|
|tables_priv|armazena privilégios de tabelas|
|columns_priv|armazena privilégios de colunas|
|procs_priv|armazena privilégios de acesso a funções e stored procedures|

Sintaxe de criar privilégio:
```bash
$ mysql > GRANT privilegio
> ON escopo(bancos e/ou tabelas)
> TO nome@host [IDENTIFIED BY 'senha'];
```
> Caso esse usuario nao exista, ele irá criar. Posso passar o *identified by* para criar a senha também

Exemplo:
```bash
$ mysql > GRANT SELECT
> ON *.*
> TO teste2@localhost;
```
**o primeiro * significa em quais bancos.**
**o segundo * especifíca em quais tabelas daquele banco.**

Todos os privilégios para um database especifíco com a possibilidade de dar privilégios a outros usuários.
```bash
$ mysql > GRANT ALL
> ON db_biblioteca.* ## o * significa todas as tabelas desse banco
> TO teste2@localhost
> WITH GRANT OPTION; ## dar privilégios a outros usuárioss
```

Apenas o privilégio de consulta(read) em todos os databases
```BASH
$ mysql > GRANT SELECT
> ON *.*
> TO teste2@localhost;
```

Privilégio de consulta em nome e sobrenome de autor, podendo apenas atualizar nome do autor de um banco especifíco de uma tabela especifíca.
```BASH
$ mysql > GRANT SELECT(nome_autor, sobrenome_autor), UPDATE(nome_autor)
> ON db_biblioteca.tbl_autor
> TO ana@localhost;
```
## REVOKE
```BASH
$ mysql > REVOKE privilegios
> ON escopo
> FROM nome@host;
```

Remover um privilégio de um usuário de todas as tabelas de um banco especifíco
```bash
$ mysql > REVOKE DELETE
> ON db_biblioteca.*
> FROM ana@localhost;
```

Remover todos os privilégios de dois usuários, inclusive o GRANT OPTION
```bash
$ mysql > REVOKE ALL, GRANT OPTION
> FROM ana@localhost, fabio@localhost;
```

## Criar novo banco de dados e tabelas utilizando apenas o MySQL Workbench
- É possível criar um novo banco e tabelas sem criar as linhas na mão, basta utilizar a interface do MySQL Workbench

## Verificar serviço e criar DER para um banco existente
1. Abrir o menu do Windows, procurar por service e achar a instância do service MySQL e rodar ele.
2. Posso selecionar um banco como padrão(*Set as default schema*)
3. Com o banco selecionado, posso clicar em *Database* > *Reverse Engineer* e ir clicando em next, dessa forma irá gerar o Diagrama Entidade Relacionamento do Banco de dados.
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/DER_7FNvJ0HKB.png" alt="DER de um banco teste gerado pelo MySQL Workbench"/>
    
  </p>
  <p align="center"><i>DER de um banco teste gerado pelo MySQL Workbench</i></p>

## Generated Columns
- Utilizada para gerar ou calcular valores com base em outro coluna da tabela
- Evita que eu faça formulas de cálculo diretamente na aplicação(back-end)

Sintaxe:
```sql
nome_coluna tipo_dados [GENERATED ALWAYS] AS expressao [VIRTUAL | STORED]
constrains
```

- **Utilizar o STORED para evitar que o cálculo seja refeito quando ocorrer uma nova consulta e para SALVAR o valor em uma coluna.**

Exemplos:
```SQL
CREATE TABLE IF NOT EXISTS Users(
  id INT PRIMARY KEY AUTO_INCREMENT,
  first_name VARCHAR(50) NOT NULL,
  last_name VARCHAR(50) NOT NULL,
  full_name VARCHAR(100) GENERATED ALWAYS AS (CONCAT(first_name, ' ', last_name))
);
```

```SQL
CREATE TABLE IF NOT EXISTS Numbers(
  id INT PRIMARY KEY AUTO_INCREMENT,
  num1 INT NOT NULL,
  num2 INT NOT NULL,
  num3 VARCHAR(100) GENERATED ALWAYS AS (num2 * num1)
);
```
```SQL
CREATE TABLE IF NOT EXISTS tbl_Vendas(
  id INT PRIMARY KEY AUTO_INCREMENT,
  Preco_produto DECIMAL(11, 2) NOT NULL,
  Quantidade INT NOT NULL,
  Desconto DECIMAL(11, 2) NOT NULL,
  Preco_total DECIMAL(11, 2) GENERATED ALWAYS AS (Preco_produto * Quantidade * (1 - DESCONTO / 100)) STORED
);

INSERT INTO tbl_Vendas(Preco_produto, Quantidade, Desconto) VALUES (10.00, 5, 10);
INSERT INTO tbl_Vendas(Preco_produto, Quantidade, Desconto) VALUES (100.00, 1, 1);
INSERT INTO tbl_Vendas(Preco_produto, Quantidade, Desconto) VALUES (5.00, 50, 25);
INSERT INTO tbl_Vendas(Preco_produto, Quantidade, Desconto) VALUES (33.33, 5, 10);
```

## *ENUM*
- Usado para criar enumerações que são lista de **valores permitidos** em uma tabela.

### Grande vantagem de utilizar *ENUM*
- **Economiza espaço no banco, pois não será necessário criar uma outra tabela que terá.**
- Os dados terão no máximo de 1 à 2 bytes, independente do tamanho do dado ali dentro.

Exemplo:
- Ao invés de criar uma tabela com os possível tamanhos e conectar com a tabela de *Camisas* por meio de uma *foreign key*
- Só existem 4 tamanhos de camisas possível nesse banco, pois isso, posso utilizar o *ENUM*.
- **Só é válido se tivermos a certeza de que os tamanhos de camisão NUNCA IRÃO MUDAR**.

```SQL
CREATE TABLE IF NOT EXISTS Camisas(
  id INT AUTO_INCREMENT PRIMARY KEY,
  tipo VARCHAR(45),
  tamanho ENUM('pequeno', 'medio', 'grande', 'extra-grande')
);

-- irá inserir dois dados corretamente
INSERT INTO Camisas VALUES ('regata', 'pequeno'), ('regata', 2);

-- não irá inserir, pois medium não faz parte dos valores possível na coluna ENUM
INSERT INTO Camisas VALUES ('regata', 'medium');
```

Visualizar os valores permitidos em um *ENUM*
```sql
SHOW FULL COLUMNS FROM Camisas;

SHOW COLUMNS FROM Camisas LIKE 'tamanho';
```

Visualizar os números de índice dos valores enumerados(basta chamar a coluna do enum e somar com 0)
```sql
SELECT nome, tamanho + 0 AS tamanho FROM Camisas;
```

**É possível observar na imagem abaixo a economia de espaço que o *ENUM* traz. Ao invés de armazenar a palavra *pequena/média/grande/extra-grande* ele armazena apenas o índice.**
 <p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/enum2_T5p8u6ilB.png" alt="SELECT de uma tabela com ENUM"/>
    
  </p>
  <p align="center"><i>SELECT de uma tabela com ENUM</i></p>

### Desvantagem de utilizar *ENUM*
Ao tentar organizar pela coluna *ENUM* o resultado não será retornar em ordem alfabetica mas sim pelos valores inseridos no *ENUM*

```sql
SELECT * FROM Camisas
ORDER BY tamanho;
```

**Para resolver esse problema**
```sql
SELECT * FROM Camisas
ORDER BY CAST(tamanho AS CHAR);
```

CAST - converte o valor para caractere ou date(chegar documentação).

## Operador UNION
- Permitir combinar o resultado de duas ou mais consultas em um único resultado
- Cada declaração *SELECT* deve ter o mesmo número de colunas, tipos de dados e ordem de colunas.

Sintaxe:

```sql
SELECT declaracao01
UNION [ALL]
SELECT declaracao02
UNION [ALL]
SELECT declaracao03
UNION [ALL]
[ORDER BY colunas];
```
- *ALL* serve para exibir todos os resultados incluindo os repetidos, pois por padrão eles são eliminados.
- *ORDER BY* enxega apenas a primeira declaração *SELECT*, ou seja, tenho que ordenar pelas colunas do primeiro *SELECT*

Exemplo01:

Retornar nomes de livros e preços dos livros.

Caso o preço do livro seja >= R$60,00 mostrar a mensagem "Livro caro" em uma coluna à direita no resultado da consulta. Caso contrário, mostrar a mensagem "Livro razoável".

Ordernar por preço, do mais barato ao mais caro.

```sql
SELECT Nome_livro Livro, Preco_livro Preço, 'Livro caro' Resultado
FROM tbl_livro WHERE Preco_livro >= 60.00
UNION
SELECT Nome_livro Livro, Preco_livro Preço, 'Livro razoável' Resultado
FROM tbl_livro WHERE Preco_livro < 60.00
ORDER BY Preço;
```

Exemplo02:

Retornar nomes de livros, preços e datas de publicação dos livros.

Caso a data de publicação seja anterior a 15/04/2012, mostrar o preço acrescido de 15% em seu valor. Caso o livro custe mais de 65 reais, descontar 10% em seu valor.

```sql
SELECT nome_livro Livro, preco_livro Preço, data_pub Publicacao, ROUND((preco_livro * 0.90), 2) Preco_final
FROM tbl_livro WHERE preco_livro > 65.00
UNION DISTINCT
SELECT nome_livro Livro, preco_livro Preço, data_pub Publicacao, ROUND((preco_livro * 1.15), 2) Preco_final
FROM tbl_livro WHERE data_pub < '20201101';
```

## EVENT
- Executado de acordo com um agendamento previo feito pelo desenvolvedor(Database administrador).

Pode ser de dois tipos:
1. Único: ocorre apenas uma vez, em um momento especifíco.
2. Recorrente: Se repete em intervalos de tempos configurados(toda semana, todo dia... todo mês).

Para isso, devo utilizar a variável de eventos *event_scheduler*, que por padrão está desligada.
```sql
SHOW VARIABLES LIKE 'event%';
```

Ativar/Desativar o agendador de eventos:
```sql
SET GLOBAL event_scheduler = ON | OFF;
```

Sintaxe:
```sql
CREATE EVENT nome_evento
ON SCHEDULE
  { AT timestamp | EVERY intervelado
    [STARTS timestamp] [ENDS timestamp] }
  [ON COMPLETE PRESERVE]
DO
  bloco_comandos_sql || procedimento;

```

- **Every nesse caso é o recorrente. Nesse caso, devo passar o *timestamp* de início e fim.**
- *ON COMPLETE PRESERVE* diz para guardar o evento depois que ele foi executado, caso contrário, ele irá excluír o evento(padrão).

### ALTER EVENT
Podemos alterar um event já criado com esse comando.

```sql
ALTER EVENT nome_evento AÇÃO
```
Com essa *AÇÃO* é possível habilitar ou desabilitar um evento, ou renomeá-lo(Sem que seja necessário excluir um evento do sistema).

AÇÃO inclui *DISABLE*, *ENABLE* e *RENAME*.

### SHOW EVENT
Permite visualizar todos os eventos do sistema ou de um banco de dados especifíco.

```sql
SHOW EVENTS;

SHOW EVENTS FROM nome_banco;
```

### DROP EVENT
Podemos excluir evento com esse comando.
```sql
DROP EVENT IF EXISTS nome_evento;
```
## Implementação do Banco de dados da faculdade
- Começar criando as tabelas que não possuí chave estrangeira, pois fica mais fácil.
- Criação das tabelas *departamento*, *curso*, *disciplina*, *turma* e *professor*.
- No caso dos ids, por serem *UUID*, terão como domínio *binary(16)* mas serão convertidos antes da inserção dos dados para *binary*.

```sql
CREATE DATABASE IF NOT EXISTS db_college;

USE db_college;

CREATE TABLE IF NOT EXISTS departament(
  id_departament BINARY(16) PRIMARY KEY,
  name_departament VARCHAR(30)
);

CREATE TABLE IF NOT EXISTS course(
  id_course BINARY(16) PRIMARY KEY,
  name_course VARCHAR(40) NOT NULL,
  id_departament INT,
  CONSTRAINT fk_course_id_departament
  FOREIGN KEY (id_departament)
  REFERENCES deparment(id_departament)
    ON UPDATE CASCADE
    ON DELETE SET NULl
);

CREATE TABLE IF NOT EXISTS discipline(
  id_discipline BINARY(16) PRIMARY KEY,
  name_discipline VARCHAR(40) NOT NULL
  hours_discipline INT UNSIGNED NOT NULL,
  description_discipline VARCHAR(80),
  num_student INT UNSIGNED
  id_deparment BINARY(16)
  CONSTRAINT fk_discipline_id_department
    FOREIGN KEY (id_deparment)
    REFERENCES deparment(id_department)
    ON UPDATE CASCADE
    ON DELETE SET NULL
);

CREATE TABLE IF NOT EXISTS class(
  id_class BINARY(16) PRIMARY KEY,
  period_class ENUM('morning', 'evening', 'night') NOT NULL,
  num_student INT UNSIGNED,
  date_start DATE,
  date_finished DATE
  id_course BINARY(16),
  CONSTRAINT fk_class_id_course
    FOREIGN KEY(id_course)
    REFERENCES course(id_course)
    ON UPDATE CASCADE
    ON DELETE SET NULL
);

CREATE TABLE IF NOT EXISTS professor(
  id_professor BINARY(16) PRIMARY KEY,
  first_name VARCHAR(30) NOT NULL,
  last_name VARCHAR(70) NOT NULL,
  status_professor BOOLEAN,
  id_departament BINARY(16),
  CONSTRAINT fk_professor_id_professor
    FOREIGN KEY (id_departament)
    REFERENCES departament(id_departament)
    ON UPDATE CASCADE
    ON DELETE SET NULL
);

CREATE TABLE IF NOT EXISTS student(
  id_student BINARY(16) PRIMARY KEY,
  first_name VARCHAR(30) NOT NULL,
  last_name VARCHAR(70) NOT NULL,
	cpf VARCHAR(11) NOT NULL,
  gender VARCHAR(15) NOT NULL,
  status_student BOOLEAN NOT NULL,
  name_mother VARCHAR(50) NOT NULL,
  name_father VARCHAR(50),
  email VARCHAR(50) NOT NULL,
  whatsapp VARCHAR(20) NOT NULL,
  id_class BINARY(16),
  id_course BINARY(16),
  CONSTRAINT fk_student_id_course
    FOREIGN KEY (id_course)
    REFERENCES course(course) ON UPDATE CASCADE ON DELETE SET NULL,
	CONSTRAINT fk_student_id_class
		FOREIGN KEY(id_class)
		REFERENCES class(id_class) ON UPDATE CASCADE ON DELETE SET NULL
);

CREATE TABLE IF NOT EXISTS type_phone(
	id_type_phone BINARY(16) PRIMARY KEY,
  type_phone VARCHAR(10) DEFAULT 'Mobile'
);


CREATE TABLE IF NOT EXISTS phone_student(
	id_phone BINARY(16) PRIMARY KEY,
  number_phone VARCHAR(20),
  id_student BINARY(16) NOT NULL,
  id_type_phone BINARY(16) NOT NULL,
  CONSTRAINT fk_phone_student_id_student
		FOREIGN KEY (id_student)
		REFERENCES student(id_student) ON UPDATE CASCADE ON DELETE CASCADE,
	CONSTRAINT fk_phone_student_type_phone
		FOREIGN KEY (id_type_phone)
    REFERENCES type_phone(id_type_phone) ON UPDATE CASCADE ON DELETE CASCADE
);

CREATE TABLE IF NOT EXISTS type_region(
	id_region BINARY(16) PRIMARY KEY,
  type_region VARCHAR(11)
);

CREATE TABLE IF NOT EXISTS address_student(
	id_address_student BINARY(16) PRIMARY KEY,
  street VARCHAR(40) NOT NULL,
  number_house INT NOT NULL,
  complement VARCHAR(50),
  zipcode VARCHAR(8) NOT NULL,
  id_student INT,
  id_region INT,
  CONSTRAINT fk_address_student_id_student
		FOREIGN KEY(id_student)
		REFERENCES student(id_student) ON UPDATE RESTRICT ON DELETE RESTRICT,
	CONSTRAINT fk_address_student_id_region
		FOREIGN KEY(id_region)
    REFERENCES type_region(id_region) ON UPDATE RESTRICT ON DELETE RESTRICT
);

CREATE TABLE IF NOT EXISTS history_student(
  id_history_student BINARY(16) PRIMARY KEY,
  date_begin DATE NOT NULL,
  date_end DATE,
  id_student INT NOT NULL,
  CONSTRAINT fk_history_student_id_student
    FOREIGN KEY (id_student)
    REFERENCES student(id_student)
      ON UPDATE CASCADE
      ON DELETE CASCADE
);

CREATE TABLE IF NOT EXISTS history_discipline(
  id_history_student BINARY(16),
  id_discipline BINARY(16),
  PRIMARY KEY(id_history_student, id_discipline)
  CONSTRAINT fk_history_disciplina_id_history_student
    FOREIGN KEY (id_history_student)
    REFERENCES history_student(id_history_student)
      ON UPDATE CASCADE
      ON DELETE RESTRICT,
  CONSTRAINT fk_history_disciplina_id_discipline
    FOREIGN KEY (id_discipline)
    REFERENCES discipline(id_discipline)
      ON UPDATE CASCADE
      ON DELETE RESTRICT
);

CREATE TABLE IF NOT EXISTS professor_discipline(
  id_professor BINARY(16),
  id_discipline BINARY(16),
  PRIMARY KEY(id_professor, id_discipline)
  CONSTRAINT fk_professor_discipline_id_professor
    FOREIGN KEY (id_professor)
    REFERENCES professor(id_professor)
      ON UPDATE CASCADE
      ON DELETE RESTRICT,
  CONSTRAINT fk_professor_discipline_id_discipline
    FOREIGN KEY (id_discipline)
    REFERENCES discipline(id_discipline)
      ON UPDATE CASCADE
      ON DELETE RESTRICT
);

CREATE TABLE IF NOT EXISTS student_discipline(
  id_student BINARY(16),
  id_discipline BINARY(16),
  PRIMARY KEY(id_student, id_discipline)
  CONSTRAINT fk_student_discipline_id_student
    FOREIGN KEY (id_student)
    REFERENCES student(id_student)
      ON UPDATE CASCADE
      ON DELETE RESTRICT,
  CONSTRAINT fk_student_discipline_id_discipline
    FOREIGN KEY (id_discipline)
    REFERENCES discipline(id_discipline)
      ON UPDATE CASCADE
      ON DELETE RESTRICT
);

CREATE TABLE IF NOT EXISTS course_discipline(
  id_course BINARY(16),
  id_discipline BINARY(16),
  PRIMARY KEY(id_course, id_discipline)
  CONSTRAINT fk_course_discipline_id_course
    FOREIGN KEY (id_course)
    REFERENCES course(id_course)
      ON UPDATE CASCADE
      ON DELETE RESTRICT,
  CONSTRAINT fk_course_discipline_id_discipline
    FOREIGN KEY (id_discipline)
    REFERENCES discipline(id_discipline)
      ON UPDATE CASCADE
      ON DELETE RESTRICT
);

```

## Inserção de dados
- Para fazer a inserção de *UUID* no campo é necessário utilizar a função de conversão de *UUID* para *binary*

```sql
INSERT INTO departament (id_departament, name_departament)
VALUES
(UUID_TO_BIN(UUID()), 'Tech'),
(UUID_TO_BIN(UUID()), 'Nutrição'),
(UUID_TO_BIN(UUID()), 'Biológicas'),
(UUID_TO_BIN(UUID()), 'Estágio');

SELECT BIN_TO_UUID(id_departament) id, name_departament name
FROM departament;

INSERT INTO professor(id_professor, first_name, last_name, status_professor, id_departament) 
VALUES(UUID_TO_BIN(UUID()), 'Danilo', 'Bandeira', true, UUID_TO_BIN('2c185450-310c-11eb-9349-4ccc6a690672')),
(UUID_TO_BIN(UUID()), 'Ana', 'Banana', true, UUID_TO_BIN('51ad0eec-285d-11eb-8ce0-4ccc6a690672'));

INSERT INTO course(id_course, name_course, id_departament) 
VALUES
(UUID_TO_BIN(UUID()), 'Computer Science', UUID_TO_BIN('df968aaf-285c-11eb-8ce0-4ccc6a690672')),
(UUID_TO_BIN(UUID()), 'Nutrição', UUID_TO_BIN
('df9677f3-285c-11eb-8ce0-4ccc6a690672'));

SELECT BIN_TO_UUID(id_class) id, name_course
FROM course;

INSERT INTO class(id_class, period_class, num_student, date_start, date_finished, id_course)
VALUES(UUID_TO_BIN(UUID()), 'morning', 40, '2014-01-01', '2017-12-31', UUID_TO_BIN('6373ee0a-31ca-11eb-9349-4ccc6a690672')),
(UUID_TO_BIN(UUID()), 'morning', 40, '2017-01-01', '2020-12-01', UUID_TO_BIN('64c0cb68-31ca-11eb-9349-4ccc6a690672'));

INSERT INTO discipline
(id_discipline, 
name_discipline, 
hours_discipline, 
description_discipline,
num_student,
id_departament) VALUES
(UUID_TO_BIN(UUID()),'Math', 70, 'Learn about Math', 40, UUID_TO_BIN('2c185450-310c-11eb-9349-4ccc6a690672')),
(UUID_TO_BIN(UUID()),'Software Engineer', 80, 'How to create', 40, UUID_TO_BIN('2c185450-310c-11eb-9349-4ccc6a690672')),
(UUID_TO_BIN(UUID()),'Health', 60, 'How to create', 40, UUID_TO_BIN('51ad0eec-285d-11eb-8ce0-4ccc6a690672'));

INSERT INTO student(
id_student, 
first_name, 
last_name, 
cpf, 
gender, 
status, 
name_mother, 
name_father, 
email,
whatsapp, 
id_class, 
id_course) VALUES
(
  UUID_TO_BIN(UUID()),
  'Danilo',
  'Bandeira',
  '00000000000',
  'Male', 
  true, 
  'Maria', 
  'José',
  'danilobandeira29@gmail.com',
  '86 995451048',
  UUID_TO_BIN('b626c7b2-31cb-11eb-9349-4ccc6a690672'),
  UUID_TO_BIN('6373ee0a-31ca-11eb-9349-4ccc6a690672')
),
(
  UUID_TO_BIN(UUID()),
  'Ana',
  'Banana',
  '00000000000',
  'Female', 
  true, 
  'Da guia', 
  'Carlos',
  'ana@banana.com',
  '86 995451048',
  UUID_TO_BIN('b6270a91-31cb-11eb-9349-4ccc6a690672'),
  UUID_TO_BIN('64c0cb68-31ca-11eb-9349-4ccc6a690672')
);



INSERT INTO type_phone(id_type_phone)
VALUES (UUID_TO_BIN(UUID()));


INSERT INTO phone_student(id_phone_student, number_phone, id_student, id_type_phone)
VALUES (
  UUID_TO_BIN(UUID()),
  '86 9 9999-9999',
  UUID_TO_BIN('03d88e7c-329b-11eb-9349-4ccc6a690672'),
  UUID_TO_BIN('fdf0bfb3-335d-11eb-9349-4ccc6a690672')
);


INSERT INTO type_region(
  id_type_region,
  type_region
) VALUES (UUID_TO_BIN(UUID()), 'avenida');



INSERT INTO address_student(
  id_address_student,
  street,
  number_house,
  zipcode,
  id_student,
  id_type_region
) VALUES(
  UUID_TO_BIN(UUID()),
  'Francisco Marreiros',
  '24',
  '64079010',
  UUID_TO_BIN('03d88e7c-329b-11eb-9349-4ccc6a690672'),
  UUID_TO_BIN('78176293-335e-11eb-9349-4ccc6a690672')
);

ALTER TABLE history_discipline 
ADD COLUMN value FLOAT,
ADD COLUMN frequency INT;

INSERT INTO history_student(id_history_student, date_begin, date_end, id_student, value, frequency)
VALUES(
  UUID_TO_BIN(UUID()), 
  '1995-10-29', 
  '2013-10-31',
  UUID_TO_BIN('03d88e7c-329b-11eb-9349-4ccc6a690672'),
  9.3,
  10
);

INSERT INTO history_discipline(id_history_student, id_discipline, value, frequency) VALUES
(
  UUID_TO_BIN('03d88e7c-329b-11eb-9349-4ccc6a690672'), 
  UUID_TO_BIN('f64e09b3-3299-11eb-9349-4ccc6a690672'),
  9.8,
  40
);

INSERT INTO professor_discipline(id_professor, id_discipline) VALUES (
  UUID_TO_BIN('d4656643-31c8-11eb-9349-4ccc6a690672'),
  UUID_TO_BIN('f64e09b3-3299-11eb-9349-4ccc6a690672')
);

INSERT INTO student_discipline(id_student, id_discipline) VALUES (
  UUID_TO_BIN('03d90961-329b-11eb-9349-4ccc6a690672'),
  UUID_TO_BIN('f64e0b85-3299-11eb-9349-4ccc6a690672')
);

INSERT INTO course_discipline(id_course, id_discipline) VALUES(
  UUID_TO_BIN('6373ee0a-31ca-11eb-9349-4ccc6a690672'),
  UUID_TO_BIN('f64d30c1-3299-11eb-9349-4ccc6a690672')
);

INSERT INTO course_discipline(id_course, id_discipline) VALUES (
  UUID_TO_BIN('6373ee0a-31ca-11eb-9349-4ccc6a690672'),
  UUID_TO_BIN('f64e09b3-3299-11eb-9349-4ccc6a690672')
);

ALTER TABLE history_discipline CHANGE value note FLOAT;

INSERT INTO phone_student(id_phone_student, number_phone, id_student, id_type_phone) VALUES
(
	UUID_TO_BIN(UUID()),
    '86 3236-3186',
    UUID_TO_BIN('03d88e7c-329b-11eb-9349-4ccc6a690672'),
    UUID_TO_BIN('edd51b95-365c-11eb-874a-4ccc6a690672')
);

INSERT INTO type_phone(id_type_phone, type_phone) VALUES (UUID_TO_BIN(UUID()), 'House');


```

Fazendo algumas alterações na criação do banco para depois fazer a inserção dos dados...a ideia é verificar o comportamento de opções de foreign key(on update/on delete restrict, cascade, set null, no action). Além do uso do UUID diretamente no banco.

- Para deletar um registro especifico, devo fazer:
```sql
DELETE FROM departament
WHERE id_departament = UUID_TO_BIN('6d92eac2-2861-11eb-8ce0-4ccc6a690672');
```
- Fiz alterações em algumas colunas e coloquei os ids de forma correta.
- Realizei alguns testes como *INNER JOIN*, *LEFT/RIGHT JOIN*. Mas farei mais testes.

1. O banco precisou sofrer pequenas alterações, como na tabela *history_discipline*, onde a coluna da nota estava armazenando inteiro e ao invés de float(4, 2).
2. Faltou inserir dados na tabela *history_discipline*.
3. Inseri mais dados em algumas tabelas, para que seja possível observar algumas consultas.

## Testes
O objetivo dos testes é pontuar se tudo está de acordo: relacionamentos, tipos de dados e afins.

1. Mostrar dados do aluno e seus dados, dados do curso e dados da turma.
```sql
SELECT BIN_TO_UUID(id_student) id, first_name name, email, name_mother mother FROM student S
INNER JOIN class C
ON C.id_course = S.id_Course
INNER JOIN course
ON course.id_course = S.id_course
ORDER BY first_name;
```
2. Todas as disciplinas cursadas por um aluno, incluindo suas notas.
```sql
SELECT * FROM student S
INNER JOIN student_discipline SD
ON SD.id_student = S.id_student
INNER JOIN discipline D
ON D.id_discipline = SD.id_discipline
INNER JOIN history_student HS
ON HS.id_student = S.id_student
INNER JOIN history_discipline HD
ON HS.id_history_student = HD.id_history_student;
```
3. Nome dos professores, as disciplinas que eles ministram e a carga horária
```sql
SELECT CONCAT(P.first_name, ' ', P.last_name) name, D.hours_discipline hours, D.name_discipline discipline FROM professor P
INNER JOIN professor_discipline PD
ON P.id_professor = PD.id_professor
INNER JOIN discipline D
ON D.id_discipline = PD.id_discipline;
```
> Na interface da aplicação, deve ser tratado para que não apareça, por exemplo, o nome do professor mais de uma vez se ele ministrar mais de uma matéria.

4. Gerar um "relatório" com nomes, sobrenomes, CPF dos alunos, tipo e números do telefone e endereço completo.
```sql
SELECT CONCAT(S.first_name, ' ', S.last_name) student, cpf, CONCAT(A.street, ', ', A.number_house) adress, A.additional, TR.type_region, TP.type_phone, PS.number_phone FROM student S
INNER JOIN address_student A
ON A.id_student = S.id_student
INNER JOIN type_region TR
ON A.id_type_region= TR.id_type_region
INNER JOIN phone_student PS
ON S.id_student = PS.id_student
INNER JOIN type_phone TP
ON TP.id_type_phone = PS.id_type_phone
ORDER BY PS.number_phone DESC;

```

5. Consultar todas as disciplinas, indicando seus departamentos, cursos e professores.
```sql
SELECT D.name_discipline discipline, C.name_course, CONCAT(P.first_name, ' ', P.last_name) professor, DD.name_departament departament
FROM discipline D
INNER JOIN departament DD
ON D.id_departament = DD.id_departament
INNER JOIN professor_discipline PD
ON D.id_discipline = PD.id_discipline
INNER JOIN professor P
ON P.id_professor = PD.id_professor
INNER JOIN course_discipline CD
ON D.id_discipline =  CD.id_discipline
INNER JOIN course C
ON CD.id_course = C.id_course;

```

**O trabalho de modelar e implementar o Banco de dados não termina após realizar os testes... ele provavelmente não vai terminar NUNCA, pois sempre haverá algo para se trabalhar: alguma correção ou atualização. Em algum momento alguém irá descobrir. MAS sempre tentar me certificar de que o banco está redondo para que seja possível sua utilização**

**Isso é totalmente normal!!**

# 12 dicas de boas práticas em Modelagem de dados
1. **Nomes de objetos**
- Use apenas nomes significativos para os objetos do banco, como tabelas, colunas e procedimentos armazenados.
- Os nomes devem ser descritivos. **Evite abreviações e siglas** obscuras que possam atrapalhar a compreensão da finalidade do objeto.

2. **Tipos corretos de dados**
- Usar os menores valores possíveis.
- A performance do banco é melhorada se usarmos os menores valores possíveis para os dados que os requisitos permitem.

3. **Normalizar as tabelas**
- A normalização de dados é um **princípio base** dos bancos de dados relacionais, no qual os dados são organizados para minimizar ou eliminar a redundância.
- Normalizar até a 3FN.
- Desnormalizar se necessário.

4. **Usar e Nomear Constraints**
- Ao nomear restrições, use prefixos que as descrevam, como por exemplo "PK" para chave primária ou "FK" para chave estrangeira, seguidos do nome da tabela(s) envolvida(s).
Exemplo: pk_IdAutor, fk_IdEditora.

5. **Identificação dos elementos do MER**
- Identifique os elementos de um modelo entidade relacionamento na seguinte ordem:
  1. Entidades
  2. Relacionamentos
  3. Atributos de entidades
  4. Atributos de relacionamentos

6. **Tabelas associativas**
- Prestar sempre muita atenção em relacionamentos muitos-para-muitos(N:M)
- Sempre que um relacionamento desse tipo ocorrer, simplificá-lo criando uma tabela associativa.

7. **Relacionamentos n-ários**
- Também prestar sempre muita atenção quando surgirem relcionamentos n-ários, como ternários ou quartenários.
- Sempre que um relacionamento desse tipo ocorrer, simplificá-lo criando tabelas associativas.

8. **Documentação**
- Documentar o processo de modelagem é de crucial importância.
- Criar o DER detalhado
- Criar Dicionário de dados(tipo de dado, espaços e como tudo irá se relacionar)
- Na codificação, usar comentários para descrever os scripts.

9. **Prefixos de nomes de objetos**
- Prefixar nomes de objetos para identificar sua categoria:
- tb para table
- vw para view
- db para database
- sp para stored procedure
- tg para trigger

10. **Nomes de tabelas e colunas**
- Use termos no singular para nomes de tabelas. Por exemplo: tblCliente ao invés de tblClientes, pois uma tabela representa uma coleção de entidades.
- Idem para colunas - NomeLivro ao invés de NomesLivros
- Procure não usar acentuação, espaços ou caracteres especiais

11. **Levantamento e Análise de Requisitos**
- Extremamente importante. Saiba levantar todas as informações necessárias para iniciar o processo de modelagem.
- Pergunte o máximo que puder, e anote toda informação fornecida pelo cliente/usuário. Interação sempre!!
- Na dúvida, contate o cliente e pergunte novamente.

12. **Campos de chave primária**
- Tabelas sempre devem possuir uma chave primária.
- Procure usar chaves naturais, sempre que possível.
- Entre uma chave composta ou surrogada, prefira sempre a surrogada.
- Procure usar tipos numéricos em vez de caracteres para economizar recursos e aumentar a performance de busca.

# 5 Dicas bônus relacionadas à programação do banco usando SQL
1. **Usar Views**
- Procure usar views para ocultar complexidade, fornecer dados agregados e restringir o acesso a linhas de colunas das tabelas.

2. **SELECT**
- Evite realizar consultas retornando todas as colunas de uma tabela.
- O ideial é sempre retornar apenas as colunas necessárias para obter melhores performance.

3. **Campos de senha**
- Senhas sempre devem ser guardadas criptografadas, de preferência usando algoritmos fortes e salt.
- A descriptação deve ocorrer na aplicação, quando for necessário.

4. **Sempre utilizar Procedures e Views**
- Aumentam a performance em consultas.
- Diminuem possibilidade de erros.
- Simplificam codificação da aplicação.
- Em alguns casos posso indexar a view para gerar perfomance.

5. **Usar índices em colunas muito consultadas**
- Índices podem aumentar significativamente a performance de acesso em consultas, caso colunas sejam muito frequentemente acessadas.
- Crie índices sempre que detectar essa necessidade, mas cuidado com colunas que são modificadas com frequência.
- **Utilizar somente quando houver mais leitura do que alteração nas colunas**

## Desafio:
**Estudo de caso da academia de ginástica**

Uma academia de ginástica deseja manter um controle do seu funcionamento. Os alunos são organizados em turmas associadas a um tipo específico de atividade. As informações sobre uma turma são número de alunos, horário da aula, duração da aula, data inicial, data final e tipo de atividade.

Cada turma é orientada por um único instrutor para o qual são cadastrados RG, nome, data de nascimento, titulação e todos os telefones possíveis para sua localização. Um instrutor pode orientar várias turmas que podem ser de diferentes atividades. Para cada turma existe um aluno monitor que auxilia o instrutor da turma, sendo que um aluno pode ser monitor no máximo em uma turma.

Os dados cadastrados dos alunos são: código de matricula , data de matrícula, nome, endereço, telefone, data de nascimento, altura e peso. Um aluno pode estar matriculado em várias turmas se deseja realizar atividades diferentes e para cada matrícula é mantido um registro das ausências do aluno.

**Entidadades:**

- Aluno
- Turma
- Instrutor

**Relacionamentos:**

- Aluno está matrículado em uma ou mais turmas
- Aluno monitora apenas uma turma
- Instrutor acompanha uma ou mais turmas
- Turma é composta por alunos
- Turma possuí atividade
- Turma possuí uma chamada

**Atributos:**

**Aluno**

- Código aluno
- Data Matrícula
- Nome
- Endereço
- Telefones
- Data de nascimento
- Altura
- Peso

**Instrutor**

- Código instrutor
- RG
- Nome
- Data de nascimento
- Titulação
- Telefones

**Turma**

- Código turma
- Número de alunos
- Horário da Aula
- Duração da Aula
- Data de inicio
- Data de fim

**Modelo Entidade Relacionament**
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/MER_Academia_5P4Tv5E5K.jpg" alt="MER Academia."/>
    
  </p>
  <p align="center"><i>MER Academia.</i></p>


**Diagrama Entidade Relacionamento(Intermediário)**

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Academia_de_ginastica_GlGmuwFFj.png" alt="DER da acadêmia com novas entidades e alguns atributos."/>
    
  </p>
  <p align="center"><i>DER da acadêmia com novas entidades e alguns atributos.</i></p>


**Dicionário de dados**
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Dicion_rio_de_dados_Entidades_e_Relacionamentos_BQDDYOFgP.png" alt="Dicionário de dados das Entidades e Relacionamentos."/>
    
  </p>
  <p align="center"><i>Dicionário de dados das Entidades e Relacionamentos.</i></p>

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Dicion_rio_de_dados_Atributos1_E-WHY5Nec.png" alt="Dicionário de dados Atributos."/>
    
  </p>
  <p align="center"><i>Dicionário de dados Atributos.</i></p>

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Dicion_rio_de_dados_Atributos2_VqfBqC4TO.png" alt="Dicionário de dados Atributos 2."/>
    
  </p>
  <p align="center"><i>Dicionário de dados Atributos 2.</i></p>


**Implementação**
```sql
CREATE DATABASE IF NOT EXISTS db_academia;
USE db_academia;

CREATE TABLE IF NOT EXISTS tbl_endereco(
	cod INT AUTO_INCREMENT PRIMARY KEY,
    rua VARCHAR(100) NOT NULL,
    numero INT UNSIGNED,
    bairro VARCHAR(50) NOT NULL,
    complemento TEXT
);

CREATE TABLE IF NOT EXISTS tbl_aluno(
	cod INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(50) NOT NULL,
    sobrenome VARCHAR(70) NOT NULL,
	data_nascimento date not null,
    altura decimal(3, 2) not null,
    peso decimal(4, 2) not null,
    telefone varchar(15) not null,
    cod_endereco int not null,
	constraint fk_cod_endereco_tblAluno
		foreign key (cod_endereco) references tbl_endereco(cod) on update cascade
);

create table if not exists tbl_matricula(
	cod int auto_increment primary key,
    cod_aluno int not null,
    constraint fk_cod_aluno_tblMatricula
		foreign key (cod_aluno) references tbl_aluno(cod) on update cascade
);

create table if not exists tbl_instrutor(
	cod int auto_increment primary key,
    rg varchar(10) not null,
    nome varchar(50) not null,
    sobrenome varchar(70) not null,
    data_nascimento date not null
);

create table if not exists tbl_telefone(
	cod int auto_increment primary key,
    tipo_telefone varchar(20) not null,
    cod_instrutor int not null,
    constraint fk_cod_instrutor_tblTelefone
		foreign key(cod_instrutor) references tbl_instrutor(cod) on update cascade on delete cascade
);

alter table tbl_telefone add column telefone varchar(20) not null;

create table if not exists tbl_atividade(
	cod int auto_increment primary key,
    nome varchar(50) not null
);

create table if not exists tbl_turma(
	cod int auto_increment primary key,
    horario timestamp not null,
    duracao time not null,
    data_inicio date not null,
    data_fim date not null,
    numero_alunos int unsigned,
    cod_atividade int not null,
    constraint fk_cod_atividade_tblTurma
		foreign key(cod_atividade) references tbl_atividade(cod) on update cascade
);

alter table tbl_turma modify column horario time not null;

alter table tbl_turma modify column cod_instrutor int;

alter table tbl_turma add column cod_instrutor int not null, add constraint fk_cod_instrutor_tblTurma foreign key (cod_instrutor) references tbl_instrutor(cod);

create table if not exists tbl_aulo_turma(
	cod_aluno int,
    cod_turma int,
    primary key(cod_aluno, cod_turma),
    constraint fk_cod_aulo_tblTurma
		foreign key (cod_aluno) references tbl_aluno(cod) on update cascade,
	constraint fk_cod_turma_tblTurma
		foreign key(cod_turma) references tbl_turma(cod) on update cascade
);

alter table tbl_aluno_turma add column data_matricula datetime not null;

update tbl_aluno_turma set data_matricula = now() where cod_aluno = 1 and cod_turma = 1;

rename table tbl_aulo_turma to tbl_aluno_turma;

create table if not exists tbl_chamada(
	cod int auto_increment primary key,
    cod_aluno int not null,
    cod_turma int not null,
    constraint fk_cod_aulo_tblChamada
		foreign key (cod_aluno) references tbl_aluno_turma(cod_aluno),
	constraint fk_cod_turma_tblChamada
		foreign key(cod_turma) references tbl_aluno_turma(cod_turma)
);

alter table tbl_chamada add column status_aluno boolean not null;

```
**Inserção de Dados**
```sql

insert into tbl_endereco(rua, numero, bairro, complemento) values (
'Francisco marreiros',
'24',
'Novo Horizonte',
'rua dos onibus'
),
(
'Coheb',
'22',
'Angelim 3',
'segunda rua ao sair da henry wall'
);

insert into tbl_aluno(nome, sobrenome, data_nascimento, altura, peso, telefone, cod_endereco) values
('Danilo', 'Bastos Bandeira de Souza', '1993-10-29', 1.70, 52.5, '86 9545-1018', 1),
('Ana Carolina', 'Apolinário da Silva', '1996-10-02', 1.60, 55.0, '86 9999-9999', 2);

insert into tbl_matricula(cod_aluno) values (1), (2);

insert into tbl_instrutor(rg, nome, sobrenome, data_nascimento) values
('111.222', 'Carlos', 'da Silva', '1950-07-15'),
('222.111', 'José', 'Bandeira', '1960-06-13');

insert into tbl_telefone(telefone, tipo_telefone, cod_instrutor) values 
('86 1111-2222', 'Casa', 1), 
('85 2222-2222', 'Trabalho', 2);

insert into tbl_atividade(nome) values ('dança'), ('exercicios');

insert into tbl_turma(horario, duracao, data_inicio, data_fim, numero_alunos, cod_atividade, cod_instrutor) values 
('10:00', '01:00', '2020-12-09', '2020-12-16', 40, 1, 1),
('13:00', '01:00', '2021-01-01', '2021-02-01', 30, 2, 2);

insert into tbl_aluno_turma(cod_aluno, cod_turma, data_matricula) values
(1, 1, curdate()),
(2, 2, curdate());

insert into tbl_chamada(cod_aluno, cod_turma, status_aluno) values (2, 1, true), (1, 2, false);

```

**Testes**
```sql
select * from tbl_aluno;
select * from tbl_endereco;
select * from tbl_aluno_turma;
select * from tbl_chamada;
select * from tbl_instrutor;
select * from tbl_telefone;
select * from tbl_turma;
select * from tbl_atividade; 

select * from tbl_aluno A
inner join tbl_endereco E
on A.cod_endereco = E.cod;

select * from tbl_aluno A
inner join tbl_matricula M
on A.cod = M.cod_aluno;

-- todo os instrutores e seus telefones
select concat(I.nome, ' ', I.sobrenome) 'nome completo', T.tipo_telefone 'local', T.telefone from tbl_telefone T
inner join tbl_instrutor I
on I.cod = T.cod_instrutor;

-- turma e o nome da atividade daquela turma, juntamente com o instrutor daquela turma
select concat(I.nome, ' ', I.sobrenome) instrutor, A.nome atividade, T.horario from tbl_turma T
inner join tbl_instrutor I
on T.cod_instrutor = I.cod
inner join tbl_atividade A
on T.cod_atividade = A.cod;

-- aluno, suas turmas que estao matriculados, todas as chamadas realizadas para saber se os alunos estavam presente em todos os dias e o nome das atividades
select A.nome, tbl_aluno_turma.data_matricula, C.status_aluno, C.cod_turma, C.cod cod_chamada, AA.nome, T.cod from tbl_aluno A
inner join tbl_aluno_turma
on A.cod = tbl_aluno_turma.cod_aluno
inner join tbl_chamada C
on C.cod_turma = tbl_aluno_turma.cod_turma
inner join tbl_turma T
on T.cod = tbl_aluno_turma.cod_turma
inner join tbl_atividade AA
on AA.cod = T.cod_atividade;

-- todos os alunos que estao matriculados em turmas
select * from tbl_aluno A
inner join tbl_aluno_turma AA
on A.cod = AA.cod_aluno;

-- todos os alunos, inclusive os que não possuem matriculas
select * from tbl_aluno A
left join tbl_aluno_turma AA
on A.cod = AA.cod_aluno;

-- apenas os alunos que não possuem matriculas
select * from tbl_aluno A
left join tbl_aluno_turma AA
on A.cod = AA.cod_aluno
where AA.cod_aluno is null;

select * from tbl_aluno;

select * from tbl_turma;

delete from tbl_aluno_turma where cod_aluno = 2 and cod_turma = 1;

create index idx_aluno_turma_dataMatricula
on tbl_aluno_turma(data_matricula);

show index from tbl_aluno_turma;

explain select * from tbl_aluno_turma where data_matricula = '0000-00-00 00:00:00';

select * from tbl_chamada;

select * from tbl_aluno_turma;

```

## Desafio 2
**Estudo de caso do cinema**

Um cinema possui várias salas de cinema, as quais exibem filmes em horários diversos. O cinema tem interesse em saber quais filmes estão atualmente em cartaz, em que salas e em que horários.

Cada sala possui um nome (único) e capacidade (número de lugares). Os filmes são caracterizados por seu nome em português, nome na língua original (se estrangeiro), diretor, ano de lançamento, tipo, e sinopse. Não existem dois filmes com o mesmo nome (em português) e ano de lançamento.

Eventualmente, podem existir para o filme premiações ou indicações para premiação (e.g. Palma de Ouro em 1987, Oscar de melhor atriz em 89, indicado para melhor filme estrangeiro em 1996), e esta informação é usada para divulgação dos filmes.

Uma exibição de filme ocorre em uma dada sala e horário. Um mesmo filme pode ser exibido na mesma sala, em vários horários. Para filmes muito procurados, o cinema pode ter exibição simultâneas em várias salas (em horários simultâneos ou não). Filmes diferentes podem passar na mesma sala, desde que obviamente não no mesmo horário.

O cinema só trabalha com horários fixos de filmes, os quais atualmente são: 16:00, 17:00, 18:00, 19:30, 20:00, 22:00, 24:00.

A cada um destes horários está vinculado um conjunto de funcionários responsáveis pelo bom andamento das atividades do cinema naquele horário, e que desempenham uma função (ex: caixa, balas, lanterninha, bilheteiro).

Cada funcionário é caracterizado pelo número da carteira da trabalho (único), nome, data de admissão e salário. Para maior satisfação dos funcionários, existe um rodízio das funções conforme o horario (ex: um mesmo funcionário pode ser caixa no horario das 16:00, e baleiro no horário das 21:00). Todo horário tem pelo menos três funcionários alocados.

**Entidades:**
- Sala
- Sala_horario_filme
- Horario
- Filme
- Funcao
- Func_horario_funcao
- Funcionario
- Filme_diretor
- Diretor
- Filme_indicacao
- Indicacao
- Filme_genero
- Genero

**Relacionamentos:**
- Sala exibe filme por horario
- Sala tem horario
- Filme tem horario
- Funcionario tem horario
- Funcionario tem funcao por horario
- Filme pode possuir indicacao/premiacao
- Filme possui genero(s)
- Filme possui diretor(es)

**Atributos:**

**Sala**
- Cod
- Número de lugares

**Sala_horario_filme**
- Cod_sala
- Cod_filme
- Cod_horario

**Filme**
- Cod
- Nome português(unique)
- Nome na língua origem(Caso não seja nacional)
- Ano de lançamento

**Horario**
- Cod
- Horario

**Filme_indicacao**
- Cod_filme
- Cod_indicacao

**Indicacao**
- Cod
- Descricao
- Ano
- Premiacao

**Filme_genero**
- Cod_filme
- Cod_genero

**Genero**
- Cod
- Nome

**Filme_diretor**
- Cod_filme
- Cod_diretor

**Funcionario**
- Cod
- Nome
- Sobrenome
- Data_admissao

**Funcao**
- Cod
- Nome

**Func_horario_funcao**
- Cod_funcionario
- Cod_horario
- Cod_funcao

## Modelo-Entidade Relacionamento

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/MER_Cinema_CFfN_Oa0e.jpg" alt="Modelo-Entidade Relacionamento Cinema."/>
    
  </p>
  <p align="center"><i>Modelo-Entidade Relacionamento Cinema.</i></p>


## Diagrama-Entidade Relacionamento
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/DER_Cinema_FF-nsuTTO.jpg" alt="Diagrama Entidade Relacionamento Cinema"/>
    
  </p>
  <p align="center"><i>Diagrama Entidade Relacionamento Cinema</i></p>

**Dicionário de dados**
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Dicion_rio_de_dados_Cinema_1_IWhAY_zpj.png" alt="Dicionário de dados parte 1"/>
    
  </p>
  <p align="center"><i>Dicionário de dados parte 1</i></p>

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Dicion_rio_de_dados_Cinema_2_oukoupagB.png" alt="Dicionário de dados parte 2"/>
    
  </p>
  <p align="center"><i>Dicionário de dados parte 2</i></p>
<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Dicion_rio_de_dados_Cinema_3_5Oybm9j-6.png" alt="Dicionário de dados parte 3"/>
    
  </p>
  <p align="center"><i>Dicionário de dados parte 3
</i></p>

<p align="center">
    <img src="https://ik.imagekit.io/xfddek6eqk/Dicion_rio_de_dados_Cinema_4_Fdy_2YX6p.png" alt="Dicionário de dados parte 4"/>
    
  </p>
  <p align="center"><i>Dicionário de dados parte 4</i></p>

**Implementação**
```sql
create database db_cinema;

use db_cinema;

create table if not exists tbl_sala(
	cod int auto_increment primary key,
    capacidade int not null
);

create table if not exists tbl_filme(
	cod int auto_increment primary key,
    nome_brasileiro varchar(100) not null unique,
    nome_original varchar(100),
    ano date not null
);

create table if not exists tbl_indicacao(
	cod int auto_increment primary key,
    descricao text not null,
    premiado boolean not null default false
);

create table if not exists tbl_genero(
	cod int auto_increment primary key,
    genero varchar(20) not null
);

create table if not exists tbl_diretor(
	cod int auto_increment primary key,
    nome varchar(100) not null
);

create table if not exists tbl_horario(
	cod int auto_increment primary key,
    horario datetime not null
);

create table if not exists tbl_funcao(
	cod int auto_increment primary key,
    nome varchar(30) not null
);

create table if not exists tbl_funcionario(
	cod int auto_increment primary key,
    nome varchar(50) not null,
    sobrenome varchar(70) not null,
    data_contratacao date not null
);

create table if not exists tbl_funcionario_horario_funcao(
	cod_funcionario int,
    cod_horario int,
    cod_funcao int,
    primary key(cod_funcionario, cod_horario, cod_funcao),
    constraint fk_codFuncionario_tblFuncionarioHorarioFuncao
		foreign key(cod_funcionario) references tbl_funcionario(cod) on update cascade,
	constraint fk_codHorario_tblFuncionarioHorarioFuncao
		foreign key(cod_horario) references tbl_horario(cod) on update cascade,
	constraint fk_codFuncao_tblFuncionarioHorarioFuncao
		foreign key(cod_funcao) references tbl_funcao(cod) on update cascade
);

create table if not exists tbl_sala_horario_filme(
	cod_sala int,
    cod_horario int,
    cod_filme int,
    primary key(cod_sala, cod_horario, cod_filme),
    constraint fk_codSala_tblSalaHorarioFilme
		foreign key(cod_sala) references tbl_sala(cod) on update cascade,
    constraint fk_codFilme_tblSalaHorarioFilme
		foreign key(cod_filme) references tbl_filme(cod) on update cascade,
	constraint fk_codHorario_tblSalaHorarioFilme
		foreign key(cod_horario) references tbl_horario(cod) on update cascade
);

create table if not exists tbl_filme_indicacao(
	cod_filme int,
    cod_indicacao int,
    primary key(cod_filme, cod_indicacao),
    constraint fk_codFilme_tblFilmeIndicacao
		foreign key(cod_filme) references tbl_filme(cod) on update cascade,
	constraint fk_codIndicacao_tblFilmeIndicacao
		foreign key(cod_indicacao) references tbl_indicacao(cod) on update cascade
);

create table if not exists tbl_filme_genero(
	cod_filme int,
    cod_genero int,
    primary key(cod_filme, cod_genero),
    constraint fk_codFilme_tblFilmeGenero
		foreign key(cod_filme) references tbl_filme(cod) on update cascade,
    constraint fk_codGenero_tblFilmeGenero
		foreign key(cod_genero) references tbl_genero(cod) on update cascade
);

create table if not exists tbl_filme_diretor(
	cod_filme int,
    cod_diretor int,
    primary key(cod_filme, cod_diretor),
    constraint fk_codFilme_tblFilmeDiretor
		foreign key(cod_filme) references tbl_filme(cod) on update cascade,
	constraint fk_codDiretor_tblFilmeDiretor
		foreign key(cod_diretor) references tbl_diretor(cod) on update cascade
);

alter table tbl_indicacao drop column premiado;
alter table tbl_indicacao drop column ano;

alter table tbl_filme_indicacao add column premiado boolean not null default false;

alter table tbl_filme_indicacao add column ano date not null;

select * from tbl_indicacao;

select * from tbl_filme_indicacao;

```

**Inserção de dados**
```sql
insert into tbl_sala(capacidade) values (10), (20), (30);

insert into tbl_filme(nome_brasileiro, nome_original, ano)
values 
('Vingadores Ultimato', 'Avengers: Endgame', '2019-03-29'),
('Vingadores Guerra Infinita',  'Avengers: Infinity War', '2018-03-29'),
('Sherlock Holmes: O Jogo das Sombras', 'Sherlock Holmes: A Game of Shadows', '2011-12-29');

insert into tbl_filme(nome_brasileiro, nome_original, ano)
values ('Bill e Ted', 'Bill & Ted', '1993-10-01');

insert into tbl_diretor(nome) values ('Anthony Russo'), ('Joe Russo'), ('Guy Ritchie');

insert into tbl_genero(genero) values ('Action'), ('Sci-fi'), ('Adventure'), ('Mistery');

insert into tbl_indicacao(descricao) values ('Sucesso de bilheteria'), ('Melhor história'), ('Melhor interpretação');

insert into tbl_horario(horario) values ('2019-03-29 16:00:00'), ('2019-03-29 22:00:00'), ('2019-03-30 00:00:00'), ('2019-03-30 14:00:00');

insert into tbl_funcao(nome) values ('bala'), ('bilhete'), ('pipoca');

insert into tbl_funcionario(nome, sobrenome, data_contratacao) values ('Danilo', 'Bandeira', '2019-01-01'), ('Ana Carolina', 'Banana', '2019-01-01'), ('José', 'Bandeira', '2019-01-01');

insert into tbl_sala_horario_filme(cod_sala, cod_horario, cod_filme) values(1, 2, 1), (2, 2, 3), (3, 3, 3);

insert into tbl_sala_horario_filme(cod_sala, cod_horario, cod_filme) values (1, 1, 2);

insert into tbl_funcionario_horario_funcao(cod_funcionario, cod_horario, cod_funcao) values(1, 2, 1), (1, 3, 2), (2, 2, 2), (3, 3, 1);

insert into tbl_filme_diretor(cod_filme, cod_diretor) values(1, 1), (1, 2), (2, 1), (2, 2), (3, 3);

insert into tbl_filme_genero(cod_filme, cod_genero) values(1, 1), (1, 2), (1, 3), (2, 1), (2, 2), (2, 3), (3, 4), (3,3), (3, 1);

insert into tbl_filme_indicacao(cod_filme, cod_indicacao, ano, premiado) values(1, 3, '2020-02-09', true), (2, 1, '2019-02-09', false), (3, 2, '2014-02-09', true);

```

**Testes**
```sql
select * from tbl_sala;
select * from tbl_horario;
select * from tbl_filme;
select * from tbl_funcionario;
select * from tbl_diretor;
select * from tbl_genero;
select * from tbl_filme_diretor;
select * from tbl_filme_indicacao;

-- todos os filmes(nome em brasileiro e original, caso exista), capacidade da sala, horarios de exibição e quais indicações e premiações o filme ganhou
select F.nome_brasileiro 'nome brasileiro', F.nome_original 'nome original', F.ano 'ano do filme', S.capacidade 'capacidade da sala',
H.horario 'exibição', I.descricao, FI.premiado 'Foi premiado?', FI.ano 'ano premiação'
from tbl_filme F
inner join tbl_sala_horario_filme SHF
on SHF.cod_filme = F.cod
inner join tbl_sala S
on S.cod = SHF.cod_sala
inner join tbl_horario H
on H.cod = SHF.cod_horario
inner join tbl_filme_indicacao FI
on FI.cod_filme = F.cod
inner join tbl_indicacao I
on I.cod = FI.cod_indicacao;

-- todos os filmes com seus diretores e premiações
select F.nome_brasileiro, D.nome, I.descricao, FP.ano, FP.premiado from tbl_filme F
inner join tbl_filme_diretor FD
on FD.cod_filme = F.cod
inner join tbl_diretor D
on D.cod = FD.cod_diretor
inner join tbl_filme_indicacao FP
on FP.cod_filme = F.cod
inner join tbl_indicacao I
on I.cod = FP.cod_indicacao;

-- todos os filmes, inclusive os que não estão sendo exibidos em nenhuma sala/horário
select * from tbl_filme F
left join tbl_sala_horario_filme SHF
on F.cod = SHF.cod_filme
left join tbl_sala S
on S.cod = SHF.cod_sala
left join tbl_horario H
on H.cod = SHF.cod_horario;

-- todos os funcionários e suas funções em determinadas datas que estão sendo exibidos filmes
select F.nome, FF.nome, H.horario, tbl_filme.nome_brasileiro, SHF.cod_sala from tbl_funcionario F
inner join tbl_funcionario_horario_funcao FHF
on F.cod = FHF.cod_funcionario
inner join tbl_funcao FF
on FF.cod = FHF.cod_funcao
inner join tbl_horario H
on H.cod = FHF.cod_horario
inner join tbl_sala_horario_filme SHF
on SHF.cod_horario = H.cod
inner join tbl_filme
on tbl_filme.cod = SHF.cod_filme;

```