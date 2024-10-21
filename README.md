# ORM - Object Relational Mapping (Mapeamento Objeto-Relacional)

Framework que aproveita ao máximo o conceito de orientação a objetos das linguagens e cria uma ponte para o mundo relacional, que é o modelo utilizado nos bancos de dados relacionais.

A função do ORM é fazer a manipulação e o mapeamento dos dados a partir dos objetos e vice-versa.

Melhor ORM para Node JS: Sequelize (Utilizado em grande parte do mercado)

Geralmente os ORM utilizam Query Builder por trás

Nível de Abstração: Definir um Model. Um model dentro do padrão MVC (Model View Controller), ele define basicamente como que será a comunicação da aplicação com o banco de dados.

---

## Consequências

**Pontos Positivos:**

- Poupa Tempo: Com o ORM, evitamos o DRY, você escreve o código em um só lugar, assim ficando mais fácil de manter e reutilizar.

- Utiliza o MVC: De forma obrigatória, deixando o código mais limpo e padronizado.

- Muitas partes são feitas automaticamentes, abstraindo os SGBDs, então migrar de MySQL para PostgreSQL, por exemplo, pode ser extremamente fácil.

- Apesar de precisar saber o que acontece por "trás das cortinas", não precisar escrever SQL pode ser algo positivo. Usar uma LIB, evita problemas de segurança como injeção a SQL, por exemplo.

- Sanitização dos dados utilizando Prepared Statements e transações se torna mais prático.

- Pode codificar 100% com a mesma linguagem de aplicação, sem se preocupar com as particularidades de cada banco de dados.


**Pontos negativos:**

- Performance: modelos mais complexos de ER acabam por gerar uma complexidade que os ORMs podem simplesmente não tratar corretamente.

- Aprender usar um ORM de maneira correta pode ser mais complicado do que ir direto para o SQL.

- Abstrair o banco de dados pode ser perigoso caso o programador fique dependente 100%, e não entenda completamente o que acontece por "trás das cortinas".

---

## Query Builder

O Query Builder é uma ferramenta que permite aos usuários criar consultas personalizadas para acessar informações em um banco de dados por meio de uma interface visual.

Query Builder mais famoso do Node JS: Knex.js. (Sequelize não utiliza este)

Knex é um nível de abstração, ele escreve as querys de uma maneira que funcionam em vários tipos de bancos de dados, como MySQL e PostgreSQL.

---

## Migrations

Como nosso banco de dados vai se comportar em tempo de vida da aplicação. Arquivos serão criados que vão determinar a estrutura da base de dados da aplicação.

Exemplo: Criar uma migration que irá criar a tabela de Usuários. Daqui 3 meses pode criar outra migration para adicionar um campo nesta tabela.

Ou seja, essas migrations vão determinar o histórico de alterações da base de dados, seja criar tabelas, remover tabelas, adicionar novos campos à tabelas, alterar campos em alguma tabela, adicionar relacionamentos, etc.

Dentro de uma migration, existem dois métodos:

up: o que essa migration vai realizar na base de dados, por exemplo, a criação de uma nova tabela.

down: desfazer as alterações realizadas pelo up, por exemplo, deletar a tabela.

Migrations podem ser utilizadas para controle de versões.

---

## Sequelize x Prisma

Embora o Prisma ORM e o Sequelize resolvam problemas semelhantes, eles funcionam de maneiras muito diferentes.

Sequelize é um ORM tradicional que mapeia tabelas para classes de modelo . Instâncias das classes de modelo então fornecem uma interface para consultas CRUD para um aplicativo em tempo de execução.

Prisma ORM é um novo tipo de ORM que atenua muitos problemas de ORMs tradicionais, como instâncias de modelo inchadas, mistura de lógica de negócios com lógica de armazenamento, falta de segurança de tipo ou consultas imprevisíveis causadas, por exemplo, por carregamento lento.

Ele usa o esquema Prisma para definir modelos de aplicativos de forma declarativa. O Prisma Migrate então permite gerar migrações SQL a partir do esquema Prisma e executá-las no banco de dados. As consultas CRUD são fornecidas pelo Prisma Client, um cliente de banco de dados leve e totalmente seguro para Node.js e TypeScript.

O Prisma ORM permite filtrar uma lista com base em um critério que se aplica não apenas aos modelos da lista que está sendo recuperada, mas a uma relação desse modelo. Sequelize não oferece uma API dedicada para filtros de relação. Você pode obter uma funcionalidade semelhante enviando uma consulta SQL bruta ao banco de dados.












