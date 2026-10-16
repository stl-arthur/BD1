# Diagrama de Entidade-Relacionamento - Oficina Mecânica

## Objetivo
O objetivo principal desta atividade prática é elaborar um Diagrama de Entidade-Relacionamento (DER)
através da descrição disponibilizada pelo professor, é necessário que seja aplicado os conceitos vistos
em aula, sendo eles:
* Entidades;
* Relacionamentos;
* Atributos;
* Cardinalidades mínima e máxima;
* Identificadores;
* Atributos de Relacionamentos;
* Generalização e Especificação;
* Entidade Associativa.


## Execução

### Entidades e Atributos
* **Cliente:** código - Identificador, telefone, email, nome.
* **Veículo:** placa - Identificador, modelo, ano, quilometragem.
* **Ordem de Serviço:** número - Identificador, dt_abertura, dt_encerramento, status.
* **Peça:** código - Identificador, descrição, fabricante, val_ref.
* **Funcionário:** matricula - Identificador, nome, dt_admissao.
* **Serviço:** código - Identificador, descrição, valor_referencia, tipo_servico

### Relacionamentos e Cardinalidades

**Cliente - Veículo** - O relacionamento entre eles é de cliente possui veículo,
cada cliente pode possuir nenhum ou mais veículos e cada veículo pode ter somente um único dono (cliente). Levando
em consideração essa especificação teremos uma cardinalidade de: cliente (1, 1) --> possui --> Veículo (0, n)

**Veículo - Ordem de Serviço** - Cada veículo pode ter uma ou mais ordens de serviço porém cada ordem de serviço possui somente
um único veículo. A cardinalidade entre eles fica Veículo (1, 1) --> Pertence --> Ordem de Serviço (1, n)

**Ordem de Serviço - Peça** - Cada ordem de serviço pode utilizar uma ou mais peças, cada peça pode estar em um ou mais ordens de serviço.
A cardinalidade entre ambas é: Ordem de Serviço (1, n) --> Utiliza --> Peça (1, n) 

**Ordem de Serviço - Funcionário - Serviço** - Essa relação foi feita de maneira ternária, o verbo utilizado talvez fique um pouco desconexo
já que estamos utilizando "realiza", então teríamos que Ordem de Serviço realiza Serviço, o que acaba não fazendo muito sentido.
Temos que um mecânico (funcionário) realiza um ou mais serviços, um mecãnico fica responsável por uma ou mais ordens de serviço, e que 
uma ou mais ordens de serviço podem realizar/possuirem um ou mais serviços. Teremos a seguinte cardinalidade:
Funcionário (1, 1) --> realiza --> Serviço (1, n) <-- realiza (contém) <-- Ordem de Serviço (1, n) <-- realiza <-- Funcionário (1, 1)


### Atributos de Relacionamentos

**Ordem de Serviço - Peça** - A relação entre Ordem de Serviço e Peça recebe atributos, "Utiliza" tem como atributos o valor unitário da peça, o valor 
efetivo da peça (preço cobrado de acordo com quantidade) e a quantidade da peça.

**Ordem de Serviço - Funcionário - Serviço** - A relação "Realiza" dessas entidades também recebe alguns atributos, são eles as observações da Ordem de Serviço e o valor efetivo do serviço

### Generalização/Especialização
Na entidade 'Funcionário' (entidade genérica) houve uma especialização,
separando funcionário em mecânico e atendente.
**Mecânico:** Na especificação de mecânico temos o atributo de especialidade, que condiz com a área em que o mecânico atua
**Atendente:** Na especificação de atendente temos o atributo do ramal

Em ambas especializações de funcionário são herdados todos os atributos que a entidade funcionário possui.