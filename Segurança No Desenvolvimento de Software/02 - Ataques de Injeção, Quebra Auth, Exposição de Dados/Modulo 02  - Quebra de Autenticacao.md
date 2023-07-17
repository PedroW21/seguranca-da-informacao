## Identificação e Autenticação

- Identificação
    - Quem é?
    - único para cada usuário;
        -    tem que ser garantido mesmo quando o usuário é 'deletado' do sistema;
        - queremos evitar que duas pessoas tenham o mesmo login separado no tempo.
        - requisito: removação de usuários lógica (nunca removido da tabela, somente indicado em algum campo que foi removido).
- Autenticação
    - Como posso ter certeza que é você mesmo?

- **Mecanismos de autenticação**
    - Algo que só o usuário sabe;       
        - (**autenticação conhecimento:** senha...)
    - Algo que só o usuário tem;
        - (**autenticação posse:** cartão, pendrive com token....);
    - Reconhecimento de características físicas;
        - (**biometrica**, iris, face);

## Autenticação biometrica

- Cada vez mais usada;
    - Cara, incomoda (em alguns casos);
    - Diversos tipos: voz, digital, retina, palma de mão, faces, iris, outras...

- Digital do dedo
    - Barata, mas sujeita a erros, falsos negativos, e pode ser quebrada.

- Retina (melhor em termos de segurança);

- Iris (melhor em termos de segurança);

- Facil;

**Usada pela comodidade, a praticidade do usuário**, não é necessariamente mais segura.


## Autenticação por Posse

- Algo que só o usuário tem
    - Cartão físico;
    - Certificado digital;
    - Tokens;
    - Cartões com senha;

Geralmente é complementada por outra autenticação (como autenticação por conhecimento).

## Autenticação por conhecimento

- Senha, Passphrase, Identificação-positiva;

- Muito usada por sistemas
    - Consiste em uma chave de identificação do usuário (login);
    - Associada a um conjunto de caracteres só conhecido pelo usuário (senha);

- Fácil de implementar;

- Os outros tipos de autenticação podem sofrer do ataque A2 (OWASP 2017)

## Autenticação vs Controle de Sessão (são exatamente a mesma coisa)

- Protocolo HTTP apenas requisições e respostas;

- Ideia de que seria algo público;

- Como garantir a autenticidade do usuário;

- Na criação do HTTP, ele não foi pensado em utilizar a questão do controle de sessão;

- O controle de sessão foi inicialmente implementado pelo netscape navigator (cookie, sessão e etc...);

- Antigamente, o http ate previa um mecanismo de autenticação, que era: a cada requisição feita, você teria que digitar as credenciais novamente.
    - Porém, para evitar esse trabalho, foi pensado numa seguinte solução:
        - Guardavamos as credenciais no navegador, e automaticamente ele enviaria elas em uma nova requisição;
            - Mas é um risco, pois é uma informação critica armazenada no navegador do usuário e que não tinha validade (tempo definido para expirar);
    - Com a solução criada e os problemas citados terem aparecidos, foi pensado numa complementação a essa solução:
        - é criado um token de sessão;
            - que tem uma validade definida, que identifica que a requisição está sendo feito por determinado usuário;
            - é mais seguro armazenar isso do que as credenciais;
            - geralmente o token de sessão é gerado antes mesmo do usuário se autenticar, e depois de autenticado, ele mantém esse token de sessão, o identificando.

## Quebra da Autenticação ou Sessão

    - Um conjunto de ataques;
    
    - Métrica da senha:
        - Tamanho minimo;
            - Numero minimo de letras maiúsculas;
            - Numero minimo de letras minusculas;
            - Numero minimo de digitos;
            - Numero minimo sinais;
            - bloquear a lista de senhas ruins;
            - 8 caracteres para aplicações **externas**;
            - 12 caracteres para aplicações **internas**;
            - (tem um motivo para essa diferenciação);

        - Bloqueio de senha:
            - Bloqueio por tentativas;
                - Por um determinado periodo de tempo (2h...);
                - Ideal é o usuário entra em contrato com o suporte para gerar uma nova senha (mas é/pode ser uma solução custosa);
                - **evitar ataque de força bruta**;
                - bloqueios na 3a ou 5a tentativa;
                    - não faz sentido mais que 5o vezes, pois a possibilidade de usuário ter esquecido além disso é de 99.9%;
            - Não permitir senhas comuns;
            - Senha inicial não pode ser fixa;
                - ideal é ser uma senha sorteada aleatoriamente e enviada ao usuário de alguma maneira (requerer troca de senha depois);
                - ou o usuário ja escolher no cadastro sua senha;
            - Troca periódica da senha;
                - 99.9% das vezes, no cenário publico, o usuário troca a senha e imediatamente esquece a senha, gerando inumeros chamados de suporte;
                - 
            - Reativação da senha (Esqueci minha senha);
        - Armazenamento da senha
            - Senha deve ser armazenada na forma de HASH;
                - diminui a chance de ataque interno (de DBA's, devs e etc);
                - 