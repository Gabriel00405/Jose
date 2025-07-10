
Avaliação Nap01 - Tipo01
Este projeto é uma aplicação back-end desenvolvida com Java e Spring Boot para criar uma API RESTful de gerenciamento de produtos. A API permite que clientes cadastrem, consultem, atualizem e removam produtos de um banco de dados.

Estrutura do Projeto e Scripts
Nap01Application.java
Descrição: Esta é a classe principal da aplicação Spring Boot.

Função: Ela contém o método main, que utiliza SpringApplication.run para inicializar a aplicação. A anotação @SpringBootApplication é utilizada para habilitar a auto-configuração, o escaneamento de componentes e a configuração da aplicação.

Produto.java
Descrição: Esta classe representa a entidade Produto e é mapeada para uma tabela no banco de dados.

Função: A anotação @Entity a marca como uma entidade JPA, e @Id e @GeneratedValue definem a chave primária com geração automática de valor. A anotação @Column(nullable = false) garante que o campo nome não possa ser nulo. A classe também possui os atributos descricao, preco e quantidade, além de métodos getters, setters, equals e hashCode.

ProdutoRepository.java
Descrição: Esta é uma interface de repositório para acesso a dados.

Função: Ela estende JpaRepository<Produto, Long>, o que a habilita a herdar métodos prontos do Spring Data JPA para operações CRUD (Create, Read, Update, Delete) em objetos Produto. A anotação @Repository indica que ela é um componente de acesso a dados.

ProdutoController.java
Descrição: Este é o controlador REST da aplicação, responsável por gerenciar as requisições HTTP.

Função: A anotação @RestController a marca como um controlador que retorna dados JSON ou XML diretamente. @RequestMapping("/produtos") define o caminho base para todos os endpoints neste controlador. Ele define os seguintes endpoints:

GET /produtos: Lista todos os produtos.

GET /produtos/{id}: Busca um produto pelo seu ID.

POST /produtos: Adiciona um novo produto.

PUT /produtos/{id}: Atualiza um produto existente.

DELETE /produtos/{id}: Remove um produto com base no ID fornecido.

O controlador utiliza injeção de dependência (@Autowired) para interagir com o ProdutoRepository e executa as operações necessárias. A classe também usa ResponseEntity para retornar respostas HTTP adequadas, como 200 OK, 204 No Content ou 404 Not Found.
