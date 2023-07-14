# Conceitos de Desenvolvimento de Software

- Tratamento de dados: coleta, análise, aprovação, transformação, interface.

- Procedimentos manuais ou documentais são transformados pela migração para mecanismos digitais.

Todo software tem um conjunto de atividades que são realizadas antes do mesmo ser usado.

Um cojunto de processos durante a utilização do software.

Tem processos que ocorrem após o uso do software.

**Nunca existe segurança de software desacoplados dos processos ao redor do mesmo**

Os requisitos não se referem somente ao software, obviamente o mesmo terá que implementar eles. Mas os processos em torno do software devem também implementar os requisitos.

Segurança abrange todo o escopo em que aquele software será executado.

## Todo software é uma mudança

- Cada nova versão implica não apenas em alteração do sistema, mas de alteração de procedimento, aprendizagem de operadores, etc.

- Humanos são propensos a repetição de algo, manter o status quo, então sempre que há uma nova versão daquele software, notaremos uma certa resistencia do usuário.

- O usuário sempre encherga o sistema novo como mais inseguro que o anterior (mesmo que tenhamos feito melhorias significativas);

    - Como resolver?
        - Treinando o usuário;
        - O processo de deploy do software deve ter em paralelo um acompanhamento adequado com o usuário (o treinando para utilizar aquele software).
        - **Educação do usuário é importante**
        - **Inclusive nos aspectos de segurança**


- Softwares são mecanismos complexos => propensos a falhas.

## Porque software tem tantos erros?

- Custo de atualização
    - É relativamente barato consertar um software, se comparado com o custo de um hardware
    - Hardware = Produto independente;
    - Software = Evolução contínua;
    - Porém, nem todo erro é barato...
        - Ariane 5 (foguete UE);
            - O software do Ariane 4 foi utilizado no 5 (ps: o 4 era mais lento em sua execução), porém no software havia um problema em que um double era jogado num valor int, o que causou seu overflow.
            - Entretando isso ocorreu somente por o Ariane 5 ter um poder de processamento maior, o que o Ariane 4 pecava.
        - Ping of Death (1995-96):
            - Problema no protocolo TCP/IP;
            - Uma má formatação no pacote que fazia o ping e o servidor ia de americanas;
        - Instituto de Cancer do Panama (2000):
            - Calculou erroneamente a dose de radioterapia pra pacientes com cancer, ocasionado na morte de 8 pacientes;

**A raiz da tolerancia da falha de software é seu custo**

**A ideia de software seguro é desenvolver um software que pode ter falhas, mas que sejam de custo pequeno, assim programando de forma segura para que falhas criticas ocorram**

## Processo de Desenvolvimento de Software

- Levantamento inicial;
    - Descrever por alto o que vai ser seu sistema;
- Especificação;
    - Coletar do usuário final o que ela precisa daquele sistema; 
- Análise do projeto;
    - Quais ferramentas, o que vai existir, como ira construir o software;
- Codificação;
- Teste;
    - Identificação de falhas e correção de problemas;
- Colocação em produção;
- Manutenção;
- Decomissionamento do sistema?
    - Quando ele não é mais utilizado, como seria esse processo?
    - Não é besteira, as vezes é necessário fazer algumas comprovações jurídicas;

## Modelos de processo de desenvolvimento

- Cascata (Waterfall)
    - Uma atividade após a outra;
- Espiral interátivo (vamos fazendo ciclos em paralelo)
    - Multiplos ciclos;
    - Ex: 
        - ciclo 1: tests
        - ciclo 2: codificando
        - ciclo 3: levantando requisitos
- Prototipagem evolucionária (agile)
    - Sistema simples vai evoluindo;
- Codificação e correção (comum nos brasil)
    - Codifica ai que depois a gente acerta;

### Metodo Royce (1970) - Cascata

**O único em que você sabe exatamente quanto tempo você irá gastar nele**

    - Percursor dos demais modelos ( o pai de todos);
    - Processo simples de entender;
    - Simples de implantar;
    - Inflexível;
        - Dificil correção de falhas caso seja algo que vem das etapas anteriores;
        - Nos requisitos do sistema, o cliente sabe pouco sobre o sistema, quando ele começa a ver a tela surgindo, começa a levantar questionamentos, pedir trocar e etc.;
        - A vantagem dos outros metodos é permitir em tempo 'real' que o cliente veja o produto sendo feito, e assim poder modificar mais rapidamente e com menos custo o que ele vier a pedir.
    - Só no final produz algo;
    - Difícil de corrigir erros;
    - Bom para sistemas pequenos;

### Metodo Boehm (1986) - Espiral

- Boehm 1986
    - Equipe aprende ao longo do tempo;
- Minimiza os riscos;
- Priorização das atividades;
- Acomoda ajustes;
- Complexo;
    - Sem noção exata do tempo de desenvolvimento;
- Ineficaz em equipes com mudanças frequentes;
    - Equipe que conheça, que saiba utilizar o modelo. Uma equipe treinada;

### Prototipagem (Agile - eu acho)

- Divide o sistema em pequenos passos;
- Modelo em cascata dentro de cada passo;
- Primeira vesão rápida;
- Clientes indecisos;
- Riscos grandes;
- Impossível determinar o prazo total;


## Metodoligas mais conhecidas

- Análise essencial
    - Modelo em cascata;
    - Cascata;

- RUP
    - Rational Unified Process
    - UML, Modelagem de Dados e etc.
    - Mecanismos de desenvolvimento muito burocraticos;
    - Espiral interativo;
    - Processo baseado na UML
    - Atores;
    - Casos de uso;
    - Classes;
    - Dificil implementação;
- Agile
    - Extreme Programming;
    - Scrum;
    - SaaS: Software as a Service;
    - Manifesto Agile (2001): Literalmente o conteúdo abaixo
        - Individuos e interações sobre processos e ferramentas;
        - Software funcional sobre documentação extensa;
        - Colaboração do cliente sobre negociação contratual;
        - Resposta a mudança sobre planejamento;

## E o legado?

- Legado é o sfotwarer que ainda é usado, ainda atende a necessidade do usuário, mas apresenta altos custos para a manutenção;

- Estima-se um custo:
    - 60% maior para adicionar novas funcionalidades;
    - 17% maior para concertar bugs;

- Risco para a segurança;

## Linguages e tipos de sistemas

Compilado e Interpretado

- Java é um puxadinho de ambos, mas tem a fragilidade de caso o codigo intermediario seja obtido, a engenharia reversa do mesmo não é muito complexa.

- Android é um pouco mais complexo do que somente java, ele apos compilado e gerado o codigo intermediario, ele passa por um processo de otimização chamado de Odexing Dalvik-Cache;

## Como evitar aplicações maliciosas de serem instaladas?

- Cetificado de assinatura de código;
- Sign tool (ferramenta de assinatura do código); 
    - Em caso de alteração naquele software, quando o usuário for verificar a assinatura do software, vai dar como inválido (o software foi adulterado);
    - Tanto android como iphone fazem a verificação da assinatura digital;
    - No caso do IOS, além da assinatura do desenvolvedor, o executavel tem que ter a assinatura da Apple. Caso não tenha uma das duas, o sistema se recusa a instalar;
    - O Windows faz isso, que quando ele não encontra a assinatura do desenvolvedor, ele aparece uma tela do tipo 'O Windows protegeu seu pc';

## Arquitetura de Sistemas

- Interface;
- Lógica;
- Dados;

### Mainframe vs Standalone

Mainframe: todos os componentes estão no servidor, e o usuário faz uma mera conexão via terminal

Standalone: todos os componentes estão na máquina do usuário;

### Cliente Servidor

- A interface e lógica esta no cliente, e os dados estão no servidor;

- Geralmente em Delphi, C++ Builder, VB6;

- **Arquitetura em desuso por questão de segurança**
    - Pois não há como garantir a proteção do BD de acesso direto e alterações nele;

## Arquiteturas mais comuns

- 3 ou N camadas;
- Web;
- Mobile;

## Arquitetura de um sistema web

- Navegador => faz requisições => servidor web recebe as requisições => servidor bd recebe pedidos do servidor web => e responde ate chegar a resposta da requisição originária.

- Orientado a requisições e respostas;
 