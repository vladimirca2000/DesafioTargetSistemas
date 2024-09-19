## Modelo Lógico
### Precisamos de quatro entidades principais

1. Cliente: Representa os clientes.
2. Telefone: Representa os telefones associados a um cliente.
3. TipoTelefone: Representa os tipos de telefone.
4. Estado: Representa os estados brasileiros.

### Relacionamentos:
* Um cliente pode ter vários telefones.
* Cada telefone tem um tipo associado.
* Cada cliente reside em um estado.

1. Tabela Cliente
~~~~ sql
CREATE TABLE Cliente (
    ClienteId INT PRIMARY KEY AUTO_INCREMENT,
    RazaoSocial VARCHAR(255) NOT NULL,
    EstadoId INT NOT NULL,
    FOREIGN KEY (EstadoId) REFERENCES Estado(EstadoId)
);
~~~~

2. Tabela Telefone
~~~~ sql
CREATE TABLE Telefone (
    TelefoneId INT PRIMARY KEY AUTO_INCREMENT,
    Numero VARCHAR(15) NOT NULL,
    TipoTelefoneId INT NOT NULL,
    ClienteId INT NOT NULL,
    FOREIGN KEY (TipoTelefoneId) REFERENCES TipoTelefone(TipoTelefoneId),
    FOREIGN KEY (ClienteId) REFERENCES Cliente(ClienteId)
);
~~~~
3. Tabela TipoTelefone
~~~~ sql
CREATE TABLE TipoTelefone (
    TipoTelefoneId INT PRIMARY KEY AUTO_INCREMENT,
    Descricao VARCHAR(50) NOT NULL
);
~~~~
4. Tabela Estado
~~~~ sql
CREATE TABLE Estado (
    EstadoId INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(50) NOT NULL,
    Sigla CHAR(2) NOT NULL
);
~~~~

## Comando SQL para Buscar Clientes e Telefones do Estado de São Paulo
~~~~ sql
SELECT 
    c.ClienteId,
    c.RazaoSocial,
    t.Numero AS Telefone,
    tt.Descricao AS TipoTelefone
FROM 
    Cliente c
JOIN 
    Estado e ON c.EstadoId = e.EstadoId
JOIN 
    Telefone t ON c.ClienteId = t.ClienteId
JOIN 
    TipoTelefone tt ON t.TipoTelefoneId = tt.TipoTelefoneId
WHERE 
    e.Sigla = 'SP';
~~~~

## Relacionamentos (PK e FK):

1. Cliente
* ClienteId: PK
* EstadoId: FK -> Estado(EstadoId)

2. Telefone
* TelefoneId: PK
* ClienteId: FK -> Cliente(ClienteId)
* TipoTelefoneId: FK -> TipoTelefone(TipoTelefoneId)

3. TipoTelefone
* TipoTelefoneId: PK

4. Estado
* EstadoId: PK

## Diagrama
![image](https://github.com/user-attachments/assets/22d84b26-e6e3-4a96-8771-680779e4ad64)



