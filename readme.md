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
- **Não deve existir atributos não-chave que determinam funcionamento outro atributo não-chave(ou conjunto deles).**

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

