# Exposição de dados sensíveis

- Quebra de confidencialidade;
- Agrupamento de ataques que envolvem diversos tipos de fragilidades e mecanismos para se obter informações confidenciais do sistema;
- Falta de criptografia;
- Falha em proteção de dados;
- Comprometimento devido a outras fragilidades;

## Quais informações são sensíveis?

- Qualquer grau de confidencialidade;
- Qualquer grau de privade;

- Classificação das informações
    - Identificar informações sob responsabilidade do sistema;
    - Classificar em informações sensíveis ou não;

## Proteção estática (não são transacionadas, ficam no BD ) ou em movimento

- Informação no seu banco de dados, no seu servidor
    - Problema tipicamente mais simples => proteção ativa
    - Principio da necessidade
    - A5: Quebra do controle de acesso
    - A6: Configuração de segurança incorreta

- Informação em trânsito
    - Problema mais complexo => proteção passiva = criptografia
    - HTTPs

## Criptografia

- Mecanismo para 'esconder' um dado

- Existe a muito tempo
    - Primeiras evidencias em hieróglifos no Egito;
    
- Alguns tipos distintos
    - Hash
    - Simétrica
    - Assimétrica

- Criptografia César 
    - Substituição simples: descola 3 letras pra frente


- Máquina Enigma
    - Decisiva na 2a grande guerra
    - Allan Turing

# Tipos de criptografia

## Hash

- Mão unica

## Simétrica

- Há uma chave;
- Fornece ao algoritimo uma chave e o conteudo a ser criptografado
- Gera um elemento criptografado que pode ser decriptografado tendo essa chave;
### Tipos:
    - DES (56 bits) - inseguro
    - TDEA = 3DES (168 bits) - peter fica com medo
    - AES ( Rijndeal, 128bits ) - mais usado hj em dia e recomendado
    - IDEA (128 bits) - recomenda
    - Blowfish (32 a 448bits)

### Como é usado?

- Chave Secreta
    - Dois elementos possuem uma mesma chave que usam para conversar entre si
- Chave de sessão
    - Dois elementos dispõe de um meio de sortear uma chave temporária para ser usada entre si
- Kerberos
    - Servidor de tickets gerencia a comunicação entre os elementos


### Exploração de criptografia simétrica

**Nunca fazer nossas proprias criptografias**

- Ataque a cifra => muito custosa se criptografia for bem feita
    - Algoritimos fracos
    - Algoritimos antigos
    - Algoritimo feito em casa, XOR
    - Base64 não é criptografia

- Ataque a chave => mais provável
    - Sistema de chave secreta
    - Servidor de tickets

## Criptoanálise

- Frequencia de letra, ditongos, tritongos, quadritongos
    - Exitem  tabelas para português
    - Diversos sistemas para execução

## Assimétrica

- Tem duas chaves;
- Chaves são geradas em pares (ligação matemática)
- Contéudo é so decriptografado somente com outra chave (a que não criptografou o conteúdo)

- RSA (Rivest, Shamir, Adleman) 
- ECC (Curvas elipticas)

Pode ser utilizada para assinatura digital 
Ps: diferente de criptografia

## Interfaces com outros sistemas

- Via web services
    - Use HTTPs com todas as proteções indicadas, certificados válidos e ambas as pontas

- Via arquivos
    - Use criptografia assimetrica, criptografe com a chave pública do sistema para onde vai mandar
    - Assine digitalmente para garantir a origem do dado
    - Criptografia simétrica => cuidado

- SMTP, FTP, etc... 

###  Criptografia vs Assinatura digital

Criptografia é garantir que a informação não é apresentavel, e assinatura é garantir a fonte da informação

### Criptografia correta

a criptografia funciona em blocos

- Vetor IV (Initializing Vector) inicializado corretamente e enviado junto com o dado criptografado 
- chave gerada conforme prescrito pelo algoritmo
- Preenchimento (padding) de dados adequados
- Certificados válidos

AES sempre criptografa um conjunto de 8 bytes

O IV deve ter numeros sorteados

Padding: tem tencnicas para fazer com que a criptografia não seja enfraquecida em um cenario onde uma inforamção de 10 bytes precisa ser criptografada num algoritimo que faz de 8 em 8 blocos
    - nesse cenário seria criptografado 8 bytes, e os 2 restantes passaria pro proximo bloco em que seria informado no final dele o tamanho desse conteudo

## Exposição de Dados Sensíveis

- Falha na proteção ativa (A5 e A6)
    - Mensagem de erro e informações internas
- Falta de HTTPS
    - ou HTTPS com certificado inválido
- Falha na proteção passiva


