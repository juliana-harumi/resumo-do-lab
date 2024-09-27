# resumo-do-lab
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO

# Localizando Serviços por Categoria no Azure

Após a criação da sua conta na Azure, siga os passos abaixo para explorar e personalizar o seu ambiente.

> **Nota**: Contas de avaliação (Trial) podem ter limitações para criação de alguns serviços ou acesso a determinadas regiões, devido a custos mais elevados. Nem todos os serviços ou regiões estarão disponíveis durante o uso gratuito.

## Alterando o Idioma e Personalizando o Portal

### Alterar o idioma
1. No portal, clique em **Configurações do portal**.
2. Selecione **Idioma e região** e ajuste conforme a sua preferência.

### Personalizar a aparência do portal
1. Acesse **Configurações do portal**.
2. Escolha a opção **Aparência + exibições de inicialização** para modificar o layout e o estilo do portal.

## Visualizando Serviços no Azure

No painel principal do portal, utilize o menu **Todos os serviços** para visualizar os diversos serviços oferecidos pela Azure, organizados por categorias. Isso facilita a navegação e a descoberta dos serviços que você pode querer explorar.

### Produtos em Versão Prévia
Alguns serviços na Azure podem estar marcados como **versão prévia**. Esses serviços estão em fase de testes iniciais e têm as seguintes características importantes:

- **Sem garantias**: Os serviços em versão prévia podem ser alterados ou até descontinuados.
- **Sem SLA**: Esses serviços **não possuem SLA** (Acordo de Nível de Serviço), ou seja, não há garantias de disponibilidade ou performance.

# Benefícios da Nuvem

- **Alta disponibilidade**: Garante o funcionamento contínuo dos sistemas, mesmo em caso de falhas.
- **Escalabilidade**: Ajusta os recursos conforme a demanda, proporcionando economia, já que você paga apenas pelo que utiliza.
- **Elasticidade**: Permite expandir ou reduzir automaticamente os recursos em resposta a picos ou quedas de demanda.
- **Confiabilidade (Resiliência)**: A descentralização da infraestrutura garante resiliência, mesmo que ocorram problemas em uma região específica.
- **Previsibilidade**: A nuvem oferece previsibilidade no desempenho e nos custos, auxiliada pelo Microsoft Azure Well-Architected Framework.
- **Segurança**: Fornece ferramentas de segurança robustas, mas o cliente ainda precisa implementar muitas medidas, especialmente em IaaS (infraestrutura como serviço).
- **Governança**: Auditorias e atualizações automáticas ajudam a manter a conformidade e a segurança da nuvem.
- **Gerenciabilidade**: Facilita o controle dos recursos da nuvem por meio de portais, APIs e automação, eliminando a necessidade de configuração manual.

# Benefícios da Nuvem - Laboratório

## Valores de SLA

| **SLA**   | **Tempo de inatividade por semana** | **Tempo de inatividade por mês** | **Tempo de inatividade por ano** |
|-----------|-------------------------------------|-----------------------------------|----------------------------------|
| **99%**   | 1,68 horas                          | 7,2 horas                        | 3,65 dias                        |
| **99,9%** | 10,1 minutos                        | 43,2 minutos                     | 8,76 horas                      |
| **99,95%**| 5 minutos                           | 21,6 minutos                     | 4,38 horas                      |
| **99,99%**| 1,01 minutos                        | 4,32 minutos                     | 52,56 minutos                   |
| **99,999%**| 6 segundos                         | 25,9 segundos                    | 5,26 minutos                    |

> **SLA** (Service Level Agreement), em português, “Acordo de Nível de Serviço”, “Contrato de Nível de Serviço” ou “Garantia de Nível de Serviço”.

## Opções de Disponibilidade

Quando criamos uma Máquina Virtual, temos um ícone de **"i"** na frente de cada opção. Esse ícone nos mostra um pequeno resumo do que significa cada opção. Ao clicar na opção **"Saiba mais"**, você é levado diretamente ao documento que explica os detalhes (nem todas as opções possuem essa função).

Na opção de **"Opções de disponibilidade"**, há 4 tipos principais:

1. **Nenhuma redundância de infraestrutura necessária**
2. **Zona de disponibilidade**
3. **Conjunto de dimensionamento de máquinas virtuais**
4. **Conjunto de disponibilidade**

Cada uma dessas estruturas impacta o resultado do SLA. Para saber exatamente qual nível de disponibilidade (99.xx%) é o mais adequado, é necessário consultar a documentação oficial.

Uma outra estratégia de replicação é encontrada nas **Contas de Armazenamento**, na opção **"Redundância"**. Isso também influencia nas regras do SLA. Ou seja, quanto mais replicações eu tiver, mais "9s" consigo garantir, e assim, o meu tempo de inatividade será menor.

