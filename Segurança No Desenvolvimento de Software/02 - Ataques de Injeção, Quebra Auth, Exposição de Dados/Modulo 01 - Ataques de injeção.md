# Vulnerabilidades em Software

- Grande parte é especifica para o sistema;

- Algumas são genéricas e agrupadas em categorias;

- OWASP faz catalogação das vulnerabilidades mais comuns
    - OWASP Top 10
        - 2017
    - Focado em aplicações web;
    - No curso, terá outras vulnerabilidades;

## OWASP - Open Web Application Security Project

### Injeção
    - Dois sistemas em que um monta comando para o outro
        - Ex: Usuário envia um dado mal formado para o sistema intermediário, que acaba por não entender aquele dado e gerar um comando pro sistema final de alto risco;
            - Fluxo:
                - User => Middle Sys => Final Sys;
        
    - Tem vários tipos de ataque de injeção, mas será exemplificado aqui o SQL Injection;

## SQL Injection (Direto)

É quando o servidor não trata os dados do usuário e com isso monta uma query insegura (sendo assim o atacante envia um pedaço de query que ele deseja).

Também tem o refletido, em que é cadastrado no BD um comando, que posteriomente quando for montado uma tela e aquele comando for lido, o ataque sera executado.

Utiliza a ferramenta de SQL Map
Há também o Blind SQL Injection, onde você obtem as informações pelo tempo, ex: o atacante executa diversas querys mal foramdas, e o tempo de reação do server para da erro, ele calcula e extrai assim bit a bit do bd.
Ex2: o bit da primeira letra da palavra é x ou y? se for x é A se for Y é B e assim segue...


### Como evitar?

- Fazendo um select parametrizado, pois quando se tem paramentros, o BD entende que aquilo faz parte do parametro, de seu conteudo, e não parte da query.

- Validação de dados de entrada de forma restritiva;
- Uso de frameworks de persistência conhecidos;
- Queries avulsas, se necessárias, com uso de parameters;
- Configuração do banco de dados para não aceitar dois comandos numa mesma linha;
- Usuário para conexão ao banco de dados deve ter no mínimo de direitos possíveis;
- Teste e inspeção de código no processo;

## LDAP INJECTION

Existem N tipos de banco de dados, o de uso geral (tradicional), geralmente velocidades de escrita e leitura são iguais. Porém vendo a necessidade de algo melhor, surgiu o banco de dados 'Diretório' em que ele é especializado em leitura de dados (usado num cenário onde dados são raramente alterados, mas são muito lidos).

- Diretorio tem a LDAP, para se comunicar com ele;
