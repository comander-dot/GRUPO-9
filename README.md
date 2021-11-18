# GRUPO-9

CREATE TABLE Pessoa(
	codigo INTEGER PRIMARY KEY,
	nome VARCHAR(50)
);

CREATE TABLE Veiculo(
	codigo INTEGER PRIMARY KEY,
	modelo VARCHAR(50),
	cod_pessoa INTEGER,
	
	CONSTRAINT fk_cod_pess FOREIGN KEY (cod_pessoa)
		REFERENCES Pessoa(codigo)
);

INSERT INTO Pessoa(codigo, nome) 
	VALUES(1, 'Ana'), (2, 'Caio'), (3, 'Amanda'),
	(4, 'Bruno'), (5, 'Carlos');
	
INSERT INTO Veiculo(codigo, modelo, cod_pessoa)
	VALUES(1, 'Civic', 2), (2, 'Toro', 5);
	
SELECT P.nome, V.modelo FROM Pessoa as P, Veiculo as V 
	WHERE V.cod_pessoa = P.codigo; 
