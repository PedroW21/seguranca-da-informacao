
# O que você quer dizer 'Quero um software seguro?' 
# Quais aspectos precisamos atender? 

## Confidencialidade

Propriedade da informação que não está disponível ou revelada para entidades ou processos não autorizados - ISO 27000


- No caso em que se pressupoe em que somente um grupo de pessoas pode ver determinada informação, a esta informação se tem outra ligada, o seu nível de confidencialidade;

- O nível de confidencialidade da informação pode ser obitdo pelos seguintes metodos:
    - ACL (Access Control List) - Lista de controle de acesso;
    - Lista de negação de acesso (x pessoas não podem ver essa informação);
    - Ideal é que a lista seja pequena (por questão de segurança, não operacional);

- No caso da confidencialidade sempre há o proprietário da informação (pessoa ou grupo de pessoas) , que é quem define as regras do jogo;

- Geralmente o proprietário da informação geralmente cria (nasce com) a informação, sendo assim ele deve ter acesso aquela informação por já possuir o conhecimento da mesma.

### Por qual motivo uma informação requer confidencialidade?

- Aspectos legais
    - Lei 12.527/11: define os niveis de confidencialidade;
    - Lei 8.666/93 (quebra de sigilo como crime): Crime liberar informações de licitação;


- Valor do segredo;
    - Propriedade intelectual;
    - Informação comercial;

- Autenticação por conhecimento (autenticar o usuário por algo que so o usuário saiba - senhas (conhecimento de ninguém, somente o usuário));

## Privacidade

'Direito à reserva de informações pessoais e da própria vida privada' - L. Brandeis, S. Warren.

- Eu (usuário) e somente eu tenho o poder de autorizar quais informações certas pessoas/entidades podem ter acesso;

- Quando informamos nossas informações num formulário, já estamos o autorizando a coletar essas informações. Entretando o sistema não está autorizado a utilizar essas informações de outras maneiras (que estejam fora da politica de privacidade).

- Cookies de sessão: são informações privadas ou não? Por ser usado somente no cenário em que o usuário x está realizando ações no sistema;

- Por que se necessita de privacidade do usuário?
    - Proteção do usuário de ataques do sistema contra ele.
    - Proteção do sistema de ataques do usuário (caso mais comum, em que buscamos que o sistema tenha o minimo de informações necessárias do usuário);
    - Aspectos legais:
        - Constituição federal, CRFB/88;
        - LGPD: Lei geral de proteção de dados;
        - GDPR: General data protection regulation;
    - Proteção do individuo:
        - Boa pratica e negocio (para que o usuário continue a usar sua aplicação);
        - Limitação de responsabilidade;

## Integridade

**Toda informação precisa de algum grau de integridade, não há exceções**

```

"Propriedade da informação que é exata e completa"
- ISO 27000

"Refere-se a informação que se mantém exata e é consistente durante o ciclo de vida da informação"
- J. Boritz

```

- Somente pessoas (um ou mais) autorizadas podem alterar aquela informação;

    - Se alguém desse grupo altera a informação, ela se mantem intrega, devido a alteração ter sido realizada da maneira correta (por alguém autorizado);

- Caso qualquer outra pessoa consiga alterar aquela informação, evidentemente houve uma quebra de integridade;

__Exemplo:__

- É esperado que os dados se mantenham integros numa comunicação entre um site e a maquina do usuário (integridade na transmissão de dados); 
- Man in the middle (ataque na transmissão de dados);

- Nem toda quebra de integridade, não acarreta na quebra de confidencialidade;

- Eventos externos podem quebrar a integridade (incendio, inundação, falta de energia...);

**Geralmente confidencialidade e integridade são tratados pelo mesmo mecanismo de controle de acesso**

Porém são coisas distintas, em que há cenários que você irá tratar somente da confidencialidade da informação e não de sua integridade e vice-versa.

É relativamente fácil detectar a quebra de integridade.

**Não há muitas maneiras de detectar a quebra da confidencialidade**

- Versionamento da informação? 

### Porque INTEGRIDADE?

- Valor da informação em si
    - Poucas informações não requerem integridade;
    - Algumas mais criticas que outras;
    - Pode ser menos importante que a confidencilidade;

Ex de Integridade vs Confidencilidade: Chave privada de uma entidade certificadora;

    - Nesse caso se requer mais confidencilidade;
    - Há diversos sensores (de abertura do cofre, de movimento com o servidor e divesos outros), e em caso de positivo em qualque um deles, a chave privada é apagada.
    - Nesse caso de Entidade Certificadora, o  funcionamento do servidor criptografico se da no seguinte sentido:
        - Informações entram, são assinadas, e as informações assinadas saem.
        - Sendo assim a chave privada da EC nunca sai, somente as informações transitam;

### Ciclo de vida da informação

A integridade perdura durante todo o ciclo de vida da informação.

- Criação;
- Acesso e alteração;
- Exclusão;

Informação é um dado com contexto, e a integridade se aplica a informação como um todo.

Ex: se mantivemos um numero de telefone mas perdemos a informação de que ele se trata de um numero de telefone, houve a quebra da integridade da informação.

### Modelos de segurança (matéria especifica de segurança da informação)

- A confidencialidade de uma informação pode ser definida de várias maneiras
    - MLS (Multilevel Security): Baseados em níveis de segurança;
    - Bell-LaPadula: usado para niveis de confidencialidade (public - top secret);
    - Biba: usado para níveis de integridade;
    - Controle de acesso discricionário;


Enquanto a vertical de confidencialidade é de cima para baixo (uma pessoa que tem autorização top secret pode acessar toda a cadeia a baixo), a de integridade é de baixo pra cima (se uma pessoa por exemplo esta no nivel secret, ela so pode criar documetos secret para cima, não conseguindo criar elementos publicos), mas nada impede que a informação possa ser reclassificada.

Niveis:
- Top secret (Ultrassecreto);
- Secret (Secreto);
- Confidential (Confidencial);
- Unclassified (Público);

## Disponibilidade
```
'Propriedade da informação que está disponível para o uso quando demandado por uma entidade autorizada' 
- ISO 27001
```

É facil de detectar a quebra de disponibilidade, assim como medir precisamente a disponibilidade de um sistema.

## Confiabilidade

```
'Confiabilidade é a probabilidade de um sistema estar operacional no tempo t dado que está operacional agora'
- Conceito de engenharia de confiabilidade
```

- Critico em sistemas de tempo real;

Ex: Um sistema de alta disponibilidade mas baixa confiabilidade
- Um sistema que cai muito mas volta rapidamente;

Cenário de alta confiabilidade e baixa disponibilidade:
- O sistema funciona sem cair, mas quando cai é ladeira a baixo;

A única maneira de se garantir a confiabilidade é sistemas paralelos (redundancia), qunado um cair o outro assume; 

## Rastreabilidade

```
'Propriedade de um sistema capaz de verificar o histórico de uma informação com base em registrados'
- ASME Glossary
```

- Capacidade de ligar a alteração, criação ou remoção de uma informação ao usuário que realizou;

- Requisito legal;

- Responsabilização do usuário;

- Melhoria do sistema de segurança;

- Rastreabilidade vs Privacidade;
    - São requisitos antagônicos;

## Autenticidade

```
'Propriedade de uma entidade ou processo que é quem diz ser'
- ISO 27000
```

- Capacidade de comprovar a origem de uma informação;

- Autenticação do usuário;
    - Usuário informa quem é (login);
    - Precisamos ter comprovação dessa informação;
        - Que no caso seria a senha do usuário;
        - Ou cartão, token por pendrive;
        - Por caracteristicas fisicas;

- Assinatura (forma de autenticação mais fraca);

- Sistemas eletronicos são **sempre** mais seguros que as auternativas fisicas;

- Registro de propriedade intelectual;

## Irretratabilidade (não-repudio)

```
'Propriedade de um sistema capaz de provar a ocorrência de um evento ou ação e quais entidades as originaram'
```

- Também conhecida como não-repúdio;
    - Comprovar que o usuário fez determinada ação;
    - (rastreabilidade é meramente **registrar** a informação)

- Capacidade do sistema ligar o usuário a informação de forma a tornar impossível a negação de ação pelo usuário;
    - Mera rastreabilidade não é o suficiente para isso;
    - Requer autenticação do registro da ação pelo usuário;