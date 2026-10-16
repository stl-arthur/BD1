# Diagrama de Entidade-Relacionamento - Locadora de Carros

## Objetivo
O objetivo principal é elaborar um Diagrama de Entidade-Relacionamento para 
uma locadora de carros, seguindo os requisitos informados no exercício

## Execução
Baseado nos requisitos informados abstraimos as seguintes informações para a criação do DER

### Entidades e Atributos

* **Cliente:** cpf - Identificador, nome, idade
* **Locação** id_locacao - Identificador, qtde_dias, val_diaria
* **Carro** placa - Identificador, quilometragem

### Relacionamentos e Cardinalidade

**Cliente - Locação** - Um único cliente pode realizar uma ou então não realizar locação.
Temos que a cardinalidade e a relação entre eles é: Cliente (1, 1) --> realiza --> Locação (0, 1)

**Locação - Carro** - Uma única locação pode locar um único carro por vez. A relação e sua cardinalidade é: Locação (1, 1) --> loca --> Carro (1, 1)

### Atributos de Relacionamentos

**Cliente - Locação** - Para o cliente realizar a locação, o relacionamento recebe o atributo de seguro, dentro da realização da locação o cliente
pode ou não contratar um seguro, o seguro contratado gera um aumento de 35 Reais no contrato.

