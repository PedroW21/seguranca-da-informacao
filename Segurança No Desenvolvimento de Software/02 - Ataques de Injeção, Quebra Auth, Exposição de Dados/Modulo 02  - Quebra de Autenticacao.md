## Identificação e Autenticação

- Identificação
    - Quem é?
    - único para cada usuário;

- Autenticação
    - Como posso ter certeza que é você mesmo?

- Mecanismos de autenticação
    - Algo que só o usuário sabe; (autenticação conhecimento: senha...)
    - Algo que só o usuário tem; (autenticação posse: cartão, pendrive com token....)
    - Reconhecimento de características físicas (biometrica, iris, face);

## Autenticação biometrica

- Cada vez mais usada;
    - Cara, incomoda (em alguns casos);
    - Diversos tipos: voz, digital, retina, palma de mão, faces, iris, outras...

- Digital do dedo
    - Barata, mas sujeita a erros, falsos negativos, e pode ser quebrada.

- Retina;

- Iris;

- Facil;

**Usada pela comodidade, a praticidade do usuário**, não é necessariamente mais segura.


## Autenticação por Posse

- Algo que só o usuário tem
    - Cartão físico;
    - Certificado digital;
    - Tokens;
    - Cartões com senha;

Geralmente é complementada por outra autenticação (como senha).

## Autenticação por conhecimento

- Senha, Passphrase, Identificação-positiva;

- Muito usada por sistemas
    - Consiste em uma chave de identificação do usuário (login);
    - Associada a um conjunto de caracteres só conhecido pelo usuário (senha);

- Fácil de implementar;


## Autenticação vs Controle de Sessão

- Protocolo HTTP apenas requisições e respostas;

- Ideia de que seria algo público;

- Como garantir a autenticidade do usuário;

- Na criação do HTTP, ele não foi pensado em utilizar a questão do controle de sessão;

## Quebra da Autenticação ou Sessão

    - Pensando no cenário em que o token de sessão está criado e armazenado no browser;
        - 