# EXERCÍCIOS BANCO DE DADOS  
## Descrição
Atividades corespondentes as atividades realizadas em sala de aula. 
## ETAPA 1:
 Crie uma tabela Produtos com os seguintes itens id_produto, nome, preço,
 estoque, perecível, marca, nacionalidade.
 Atribua a cada campo seu respectivo tipo;
 Os itens: nome; preço; estoque; perecível não poderão receber valores nulos;
 O id_produto deve ser utilizado como chave-primaria.

Create table Produtos (
	id_produto INT AUTO_INCREMENT PRIMARY KEY,
	nome VARCHAR(50) NOT NULL,
	preco DECIMAL(9,2) NOT NULL,
	estoque INT NOT NULL,
	perecivel CHAR NOT NULL,
	marca VARCHAR(50),
	nacionalidade VARCHAR(100)
	);

 ![exer1](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/TabelaProdutos.png)
 
/*Após a criação insira cinco produtos, todos devem ter seus respectivos campos
preenchidos;
Verifique se todos os dados foram inseridos;
Ao término inicie a segunda etapa.*/

INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('sabonete', 5.00, 8, 'N','Jhonson','Brasileira');

INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('shampoo', 9.00, 14, 'N','Jhonson','Brasileira');
	
INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('leite', 4.90, 32, 'S','Hercules','Brasileira');

INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('refrigerante', 3.50, 4, 'S','coca-cola','Brasileira');

INSERT INTO Produtos (nome, preco, estoque, perecivel, marca, nacionalidade)
VALUES('esponja de aco', 1.50, 22, 'N','Bombril','Brasileira');

![exer2](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/Inser%C3%A7%C3%A3o5ProdutosTabela.png)

![exer3](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/SelecionadoTodosProdutos.png)

## ETAPA 2:
/*Gere um relatório informando quantos produtos estão cadastrados*/

SELECT COUNT(*) FROM Produtos;

![exer4](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/QtProdutosCadastrados.png)

/*Gere um relatório informando o preço médio dos produtos*/

	SELECT AVG(preco) as "preco_media" FROM Produtos;

![exer5](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/MediaProdutos.png)

/*Selecione a média dos preços dos produtos em 2 grupos: perecíveis e não
perecíveis*/
	
	SELECT perecivel, AVG(preco) AS "media_precos"
	FROM Produtos
	GROUP BY perecivel;

![exer6](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/MediaProdutosPereciveisNaoPereciveis.png)

/*Selecione a média dos preços dos produtos agrupados pelo nome do produto*/

	SELECT nome, AVG(preco) AS "media_precos"
	FROM Produtos
	GROUP BY nome;

![exer7](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/MediaPrecoNome.png)

/*Selecione a média dos preços e total em estoque dos produtos*/

	SELECT AVG(preco) AS media_precos, SUM(estoque) AS "total_estoque"
	FROM Produtos;

![exer8](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/MediaPrecoTotalEstoque.png)

/*Selecione o nome, marca e quantidade em estoque do produto mais caro*/

	SELECT nome, marca, estoque, MAX(preco) AS "produto_mais_caro"
	FROM Produtos; 

![exer9](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/NomeMarcaQtEstoqueMaisCaro.png)
 
/*Selecione os produtos com preço acima da média*/

	SELECT nome, preco FROM Produtos
	WHERE preco > (SELECT AVG(preco) FROM Produtos);

![exer10](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/ProdutosprecoAcimaMedia.png)

/*Selecione a quantidade de produtos de cada nacionalidade*/

	SELECT COUNT(nacionalidade) AS "quantidade_produto_cada_nacionalidade"
	FROM Produtos;	

 ![exer11](https://raw.githubusercontent.com/FabioCCamarg/Aula7BD/main/imagens/QtProdutoCadaNacionalidade.png)

 ## ETAPA 3: 
 Execute toda a atividade no WorkBench da Oracle;

Comente o código esclarecendo o que está sendo feito no bloco de código;

Crie um repositório remoto (GITHUB);

Envie somente o script SQL para o repositório;

Crie o ReadMe com base no modelo disponibilizado em aula;

Tire um print da tela do WorkBench e insira no ReadMe;

Envie na atividade somente o link do repositório criado.
