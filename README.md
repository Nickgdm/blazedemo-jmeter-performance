<pre>
╔═════════════════════════════════════════════════════════════════════════════════════════════════════════╗
║                              TESTE DE PERFORMANCE COM APACHE JMETER BLAZEDEMO                           ║
╚═════════════════════════════════════════════════════════════════════════════════════════════════════════╝
</pre>
Projeto de estudo de teste de performance para o site de demonstração BlazeDemo, utilizando Apache JMeter e dados CSV para parametrizar buscas de voos.

## Sobre o projeto

O repositório contém um plano de teste do JMeter e uma massa de dados para praticar requisições HTTP parametrizadas e execução com usuários virtuais concorrentes.

## Objetivos

- Configurar requisições HTTP para o cenário de busca de voos.
- Parametrizar origem e destino com dados CSV.
- Exercitar o sistema com usuários virtuais concorrentes.
- Praticar a configuração e a execução de um plano de teste de performance.

## Tecnologias e arquivos

- Apache JMeter 5.6.3, versão indicada no plano.
- HTTP/HTTPS.
- CSV para dados de teste.
- `Test Plan.jmx`: plano de teste configurado com 50 usuários virtuais, ramp-up de 180 segundos e duração de 300 segundos.
- `massa_dados.csv`: dados de origem e destino utilizados para parametrizar as requisições.

## Pré-requisitos

- Java compatível com a versão do JMeter instalada.
- Apache JMeter 5.6.3 ou versão compatível.
- Acesso à internet para alcançar o site de demonstração.

## Como executar

1. Instale o Apache JMeter.
2. Clone este repositório.
3. Abra `Test Plan.jmx` no JMeter.
4. Na configuração **CSV Data Set Config**, ajuste **Filename** para apontar para o arquivo `massa_dados.csv` no diretório local do projeto. O plano versionado contém um caminho absoluto específico de outra máquina.
5. Confira se as variáveis `origem` e `destino` correspondem aos cabeçalhos do CSV.
6. Comece com carga reduzida para validar a configuração antes de utilizar os 50 usuários virtuais definidos no plano.

Após validar o plano, também é possível executar em modo não gráfico:

```bash
jmeter -n -t "Test Plan.jmx" -l resultados.jtl
```

## Estrutura do projeto

```text
atividade-jmeter-blazedemo/
├── Test Plan.jmx
├── massa_dados.csv
└── README.md
```

## Desafios práticos

A atividade aborda a parametrização de requisições com CSV e a configuração de usuários virtuais, ramp-up e duração do teste. Um ponto importante é substituir o caminho absoluto do arquivo CSV por um caminho válido na máquina de execução.

## Boas práticas

- Separar a massa de dados do plano de teste.
- Parametrizar origem e destino em vez de fixar todos os valores nas requisições.
- Validar inicialmente com carga reduzida.
- Registrar os resultados em arquivo JTL para análise posterior.

## Aprendizados

A atividade permite praticar a configuração de um plano de teste de performance no Apache JMeter, incluindo requisições HTTP, dados parametrizados por CSV e definição de usuários virtuais, ramp-up e duração. Também reforça a importância de analisar métricas como tempo de resposta, taxa de erro e throughput sem presumir resultados antes da execução.

## Considerações finais

A configuração de carga não representa, por si só, um resultado de performance. Execute testes apenas em ambientes para os quais tenha autorização e registre as métricas observadas.
<pre>
╔═════════════════════════════════════════════════════════════════════════════════════════════════════════╗
║       Atividade desenvolvida durante a formação profissionalizante em Quality Assurance (QA) pela       ║
║                     EBAC — Escola Britânica de Artes Criativas e Tecnologia                             ║
╚═════════════════════════════════════════════════════════════════════════════════════════════════════════╝
</pre>
