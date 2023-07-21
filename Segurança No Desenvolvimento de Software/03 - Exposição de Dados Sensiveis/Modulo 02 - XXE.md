# XXE (XML EXTERNAL ENTITIES)

Pode ter acesso a praticamente a maquina inteira do servidor

- Em determinadas situações, pode ser usada para obter informações

**Pode ser desconsiderado em breve** (ps: 2017)

## Formato XML

- Interface entre sistemas via arquivos
    - Delimitado por colunas (CNAB)
    - Delimitado por separadores (ex: csv)

- Extensible Markup Language
    - Linguagem de marcação extensível
    - Define as colunas, permite evolução e alteração
    - Dimiui os erros na leitura
    - JSON?

### Mas meu sistema não usa XML..

- XML é quase onipresente


- SOAP
- RSS
- XML-RPC 


## Definição de formato dos dados DTD

    - Definição de Tipo de documento;
    - Define um formato XML

jeito mais simplificado de escrever XML, validar e etc...

## DTD pode estar dentro do próprio XML e pode conter várias coisas

- DTD pode unir campos;
- Pode escrever dados no console;
- Pode pegar informações de outros arquivos
- Pode executar um comando no S.O.

Com o DTD você pode executar comandos, e na hora da leitura do arquivo, esse comando é executado

## Ataque XXE pode ser na modalidade Blind

- Pagina não retorna nenhum campo do XML
- Mas o XML é lido interamente

## XML Bomb

- XML com DTD construidos para gerar erro
- Stackoverflow (entidade a tem valor de b, b tem valor de a, chamo a e fica nessa infinidade )

## Previnindo XXE

Desabilitado por default (o DTD )

- Verificar a versão dos componentes que tratam arquivos XML e webservices

- A maior parte dos componentes teve liberação de versão nova para corrigir tal fragilidade

## De forma geral, desabilitar o DTD

- No componente de parser XML
- Versões mais recentes de parsers XML já vem com o DTD desabilitado por default;
- Mas... e se eu uso o DTD?
    - Exitem formas de desabilidades apenas os Entities, mas depende do parser específico;
    - Alguns requerem definir parametros, outros que se crie uma classe dummy.  

## Outras vulnerabilidades possiveis do XML

- XML Schema (*.xsd)
- XPath