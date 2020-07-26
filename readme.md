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

# Diagrama Entidade Relacionamento
- Representação gráfica do **MER**.
- É composto por:
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

