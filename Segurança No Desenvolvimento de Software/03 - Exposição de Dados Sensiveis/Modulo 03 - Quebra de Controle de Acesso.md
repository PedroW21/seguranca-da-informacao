# Quebra de Controle de Acesso

- O que é controle de acesso?
    - Quem pode fazer o que com qual dado ou função
    - Confidencialidade, Privacidade, Integridade.

## Casos mais comuns

(Hot Spot)
- Verificação apenas no menu
    - Não verifica a URL (se determinado usuario tem acesso aquela URL)
- Não verifica nos webservices
- Verifica o direito a função, mas não ao dado específico
    - Referencia insegura;

## Contorno do mecanismo

Todo mecanismo de controle de acesso esta sujeito a contorno

- Como resolver?
    - Quanto mais proximo do dado tiver o mecanismo de controle, melhor;
    - Nunca na camada de interface;
    -  Proteger com rigor redobrado todas as interfaces e sistemas após controle de acesso.

Geralmente não põe-se controle de acesso no BD por sua complexidade, e por falta de refinamento nos mecanismos disponiveis para fazer um controle efetivo.


## Função de Controle de Acesso (recomendações)

- Única em todo o sistema;
- Todas as telas devem chamar a função
    - Na montagem da tela
    - No update dos dados no BD

- Usada em WebServices

## Exemplo: Referencia insegura

Para emissão da segunda via era só necessário o CPf da pessoa (quebra de privacidade, caso encontrase alguma conta na concessionária em questão, este comprovante poderia ser utilizado posteriormente em outras aplicações)

problema na url ou algo simples assim:
http://www.xxx.com/segundaViaCelg?id=33
http://www.xxx.com/segundaViaCelg?cpf=33

num iframe
num Ajax

POST (campo hidden)

## Exemplo: Como ganhar o avião do Faustão

- Digite o código de barras da mercadoria
    - Código altamente previsível
    - Pode-se gerar milhões de códigos automáticos

- Mascaramento
    - Milhares de laranjas
    - Acessos distintos
    - Falsificar embalagem

## Qual o problema aqui?

- Referência óbvia facilita o ataque
    - CPF
    - Número de registro
    - Email

- Referência concisa facilita o ataque

- 1,2,3,4, ... x

- Mas o problema real é a falta de controle de acesso.

## Chamada e resposta ideal para uma aplicação

- Retorno apenas com as informações necessárias
- Informações com tipo definido e não ambíguas
- Forma de descrever campos esperados, ou seja, um contrato de interface
- Forma de lidar com erros e exceções

## O que é um webservice?

É quando uma aplicação prove serviços pela web.

Ex: o correios oferece uma api de consulta de cep, você dev cria um servidor que puxa as informações dessa api, e faz os devidos tratamentos para que so seja disponibilizado os dados necessários pra ti/grupo de pessoas.

**Uma maneira simples e facil de uma aplicação acessando outra aplicação**

## Ataques sobre WebServices

- Identificar WebServices usados pela aplicação
    - Muito dificil de identificar os usados pelo servidor
    - Muito simples identificar os usados via AJAX

- Muito comum não haver verificação de controle de acesso

- Outros ataques podem ser possíveis:
    - Injection (Script, SQL, etc...)
    - XSS
    - Insecure Reference

## WebServices seguros

- Entre Servidores
    - Sempre com HTTPS
    - Certificados digitais em ambas as pontas
    - Verificar a autenticidade e o direito de acesso
    - Se sistema externo, identificação do usuário final

- AJAX
    - Sempre com HTTPS
    - Acessando apenas web services no mesmo servidor de  aplicação
    - Controle de acesso pela sessão do browser 

## Outras formas de quebra de autenticação

- Além desses, impossível não mencionar
    - Key Logger
    - Engenharia Social

- Key Logger (inumeros tipos de keylogger)
    - Muito simples
    - Muito efetivo

- Engenharia Social
    - Fishing scams, etc.

## Usuários, Grupos e Perfis

- Geralmente agrupa-se usuários com mesmo tipo de direito
    - Perfis = usuário só está em um perfil de cada vez
    - Grupo = usuário pode estar em mais de um grupo

Batata: funcionários de carreira tendem a acumular permissões e aprender a burlar o sistema.

## Segregação de funções

Ex: ao receber novas atribuições, os gestores esquecem de remover as permissões antigas que não são mais necessárias

- Algumas ações não podem ser feitas pela mesma pessoa

- Nenhuma pessoa pode ter acesso a tudo

## Super-perfis em Gestão de Identidade

Gestão de perfis
