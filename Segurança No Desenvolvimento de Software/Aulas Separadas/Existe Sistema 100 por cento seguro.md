# Segurança no Contexto de Software
 
**Mitigação de riscos indesejados no sistema**

- É um conjunto de aspectos que podem ser mais importantes ou menos importantes a depender do software;

## Principais aspectos de segurança

### Disponibilidade: 

**Impossibilidade de realizar uma ou mais funções esperadas do sistema, há uma quebra de disponibilidade**

- Queda do site;
    - Excesso de tráfego;
    - Bug no sistema;
    - Quebra na disponibilidade de um outro sistema que faz interface com o nosso;

### Integridade:

**Quebra da integridade da informação**

- Essas informações não podem ser violadas por regras que não estejam definidas no sistema, como:
    - Alterando ou removendo alguma informação de forma não esperada, podendo ser das seguintes maneiras:
        - Hacking;
        - Bug;
        - Falha no Banco de Dados;
        - Falha de Hardware (o disco do servidor foi pro buraco);


### Confidencialidade:

**Apenas pessoas autorizadas oissan ter acesso (ver e/ou alterar) determinadas informações tratadas pelo sistema**

- Esse pilar pode ser violada da seguinte maneira:
    - Contorno do mecanismo de controle de acesso;
    - Bug, erro ou fragilidade também pode gerar o rompimento desse pilar;

### Os aspectos acima são os mais importantes por serem os mais custosos aos clientes em caso de quebra;


### Sistemas diferentes tem necessidades diferentes de segurança

### Aspectos de seguranã são únicos a cada sistema

### Outros aspectos de segurança importantes:
    - Rastreabilidade;
    - Privacidade;
    - Autenticidade;
    - Irretratabilidade;



### A segurança é inversamente proporcional ao risco;

OBS: Formula conceitual, demonstra apenas a relação dos mesmos;

Segurança = 1 / Risco;

Risco = Perigos / Salvaguardas;

Perigos = Potenciais quebras de um ou mais aspectos de segurança;

Salvaguardas = Controles ou dispositivos que são implementados para evitar a quebra dos aspectos de segurança, e em caso de quebra, diminuir os efeitos dessa falha;
