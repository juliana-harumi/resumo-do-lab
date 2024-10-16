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

# Tipos de Serviços de Nuvem no Azure

- **IaaS (Infraestrutura como Serviço)**: Permite a criação de uma infraestrutura de TI com pagamento conforme o uso, alugando servidores, máquinas virtuais, armazenamento, redes e sistemas operacionais de um provedor de nuvem.
- **PaaS (Plataforma como Serviço)**: Fornece um ambiente para a criação, o teste e a implantação de aplicativos de software, sem a necessidade de gerenciar a infraestrutura subjacente.
- **SaaS (Software como Serviço)**: Os usuários se conectam e utilizam aplicativos baseados na nuvem pela Internet, como Microsoft Office 365, e-mail e calendários.

## Modelo de Responsabilidade Compartilhada

- **IaaS**: O serviço de nuvem mais flexível. Você configura e gerencia o hardware para seu aplicativo.
- **PaaS**: Focado no desenvolvimento de aplicativos. O gerenciamento da plataforma é realizado pelo provedor de nuvem.
- **SaaS**: Modelo de pagamento conforme o uso. Os usuários pagam pelo software que utilizam em um modelo de assinatura.

## Tipos de Serviço de Nuvem - Laboratório

Dentro do console do Azure, ao clicar em **Criar Máquinas Virtuais**, é possível visualizar uma ampla gama de configurações. Agora, vamos focar na arquitetura e no sistema operacional.

- Na opção **Imagem**, você pode escolher entre várias opções de sistemas operacionais. Ao selecionar o sistema operacional, a opção **Tamanho** já exibe o valor em Reais por mês. Vale lembrar que tudo o que você criar é de sua responsabilidade.
- Na próxima página, é possível adicionar discos, configurar a rede, gerenciar e monitorar, entre outras opções.
- Ainda no console, ao clicar em **Criar Bancos de Dados SQL**, existe a opção de criar um servidor. Você deve clicar em **Criar um novo**, onde será necessário definir um nome, localização, método de autenticação e selecionar um administrador. É importante lembrar que você não terá acesso a esse servidor, ele é apenas para o banco de dados.
- Além disso, durante a criação do banco de dados, você poderá selecionar a **Redundância do Armazenamento de Backup** (lembre-se do SLA). No final, será exibido o custo mensal do banco de dados.

# Componentes da Arquitetura do Azure

## Regiões
O Azure possui a maior quantidade de regiões globais entre os provedores de nuvem, com mais de 60 regiões em mais de 140 países. Cada região é composta por um ou mais datacenters localizados próximos, permitindo maior flexibilidade, escalabilidade e menor latência para os usuários. Além disso, as regiões garantem conformidade com a legislação local de dados e preservam a residência dessas informações. 

[Mais informações](https://azure.microsoft.com/pt-br/explore/global-infrastructure/geographies#:~:text=O%20Azure%20est%C3%A1%20dispon%C3%ADvel%20ou,%2C%20Alemanha%2C%20Gr%C3%A9cia%2C%20It%C3%A1lia%2C)

## Zonas de Disponibilidade
As zonas de disponibilidade protegem contra interrupções ao isolar fisicamente datacenters dentro da mesma região. Cada datacenter possui sua própria alimentação, sistema de resfriamento e rede. Esses datacenters são interligados por redes de fibra óptica privadas para garantir continuidade e alta disponibilidade.

## Pares de Regiões
As regiões em pares são separadas por, no mínimo, 300 milhas, garantindo maior resiliência. Certos serviços do Azure replicam automaticamente os dados entre essas regiões. Em caso de falhas, uma região será priorizada para recuperação. Além disso, as atualizações de sistema são distribuídas em momentos diferentes para reduzir o impacto no serviço.

## Regiões Soberanas
- **Serviços Governamentais dos EUA**: Atendem às necessidades de segurança e conformidade de entidades federais, estaduais e municipais dos EUA.
- **Azure China**: A Microsoft é o primeiro provedor de serviços de nuvem pública internacional na China, conforme as leis e regulamentações do governo chinês.

## Recursos do Azure
No Azure, você pode utilizar diversos recursos como armazenamento, redes e máquinas virtuais para construir suas soluções de nuvem.

## Grupos de Recursos
Os grupos de recursos são contêineres que permitem gerenciar e organizar diferentes recursos em um único local. Esses recursos podem estar localizados em diferentes regiões e ser movidos entre grupos conforme necessário. Além disso, é possível utilizar vários grupos de recursos para um único aplicativo.

## Assinaturas do Azure
Cada assinatura no Azure fornece acesso seguro e autorizado aos serviços. Ela também oferece controle sobre o faturamento, gerando relatórios individuais para cada assinatura, e possibilita a definição de permissões para o acesso aos recursos.

## Grupos de Gerenciamento
Grupos de gerenciamento facilitam a organização de várias assinaturas do Azure. Todas as assinaturas associadas a um grupo herdam automaticamente as regras de gerenciamento aplicadas a ele.

## Componentes da Arquitetura do Azure - Laboratório
Ao criar um **Grupo de Recursos** no Azure, a sua assinatura padrão será selecionada automaticamente. Caso tenha mais de uma, basta escolher a alternativa adequada. A criação de um grupo de recursos é obrigatória e você deve nomeá-lo e escolher a região onde será implementado. As marcações (tags) permitem identificar e classificar os recursos. Após a criação do grupo, é possível verificar logs de auditoria, permissões e eventos de automação. O primeiro recurso que você deve criar dentro do grupo é uma **VNET** (rede virtual), que permite criar uma rede isolada na nuvem.

# Computação e Rede

## Serviços de Computação no Azure
O Azure disponibiliza serviços de computação sob demanda, fornecendo recursos como armazenamento, processadores, memória, rede e sistemas operacionais.

### Máquinas Virtuais no Azure
As VMs (máquinas virtuais) do Azure simulam computadores físicos por meio de software, incluindo processador virtual, memória, rede e armazenamento. Esse serviço de IaaS oferece grande flexibilidade e controle total aos usuários.

#### Conjuntos de Dimensionamento de VMs
Os conjuntos de dimensionamento permitem ajustar automaticamente a capacidade de computação, garantindo balanceamento de carga conforme necessário.

### Área de Trabalho Virtual do Azure
A Área de Trabalho Virtual do Azure oferece virtualização de áreas de trabalho e aplicativos na nuvem, eliminando a necessidade de servidores adicionais de gateway e reduzindo o risco de obsolescência. Ele suporta sessões múltiplas em uma única implantação.

## Serviços de Contêineres do Azure
Os contêineres fornecem um ambiente virtualizado mais leve, sem a necessidade de gerenciamento completo do sistema operacional, respondendo às demandas dinâmicas de forma ágil.

- **Instâncias de Contêiner do Azure**: PaaS que roda um ou mais contêineres.
- **Aplicativos de Contêiner do Azure**: PaaS para balanceamento e escalonamento de cargas.
- **Serviço de Kubernetes do Azure**: Orquestração de contêineres para arquiteturas distribuídas.

### Azure Functions
Um serviço PaaS que suporta computação serverless, permitindo a execução de código sob demanda, sem a necessidade de manter infraestrutura ativa.

## Comparação das Opções de Computação do Azure

### Máquinas Virtuais
Servidores baseados na nuvem que suportam sistemas operacionais Windows e Linux. Indicados para migrações do tipo lift-and-shift e fornecem o pacote completo do sistema operacional.

### Área de Trabalho Virtual
Oferece uma experiência de desktop baseada em nuvem, acessível por aplicativos ou navegadores modernos, com suporte a múltiplos logins de usuários simultâneos.

### Contêineres
Uma solução leve e modular, ideal para microsserviços, com alta escalabilidade e resiliência, funcionando em cima do sistema operacional do host.

## Serviços de Aplicativos do Azure
O Azure App Services é uma plataforma gerenciada para desenvolvimento, implantação e escalabilidade de aplicativos web e APIs, compatível com linguagens como .NET, Node.js, Java, Python, entre outras. Ele oferece PaaS com alto desempenho, segurança e conformidade.

## Rede Virtual no Azure (VNet)
A VNet do Azure permite que os recursos se comuniquem entre si, com a Internet e com redes locais.

- **Pontos de Extremidade Públicos**: Acessíveis via Internet.
- **Pontos de Extremidade Privados**: Restritos a redes internas.
- **Sub-redes**: Segmentam a rede conforme necessário.
- **Emparelhamento de Rede**: Conecta redes privadas diretamente.
- **Gateway de VPN**: Transfere dados criptografados entre redes locais e virtuais do Azure via Internet.
- **ExpressRoute**: Conexão privada para estender redes locais ao Azure.

## DNS do Azure
Oferece alta confiabilidade e desempenho por meio de servidores DNS globais usando Anycast. O DNS do Azure facilita a gestão de domínios externos e do Azure em um único serviço, com controle de acesso baseado em funções, monitoramento e registros detalhados.

- **Nomes de Domínio Personalizados**: Possibilidade de criar domínios privados em redes virtuais.
- **Registros de Alias**: Apontam diretamente para recursos do Azure.

# Armazenamento no Azure

## Contas de Armazenamento
Cada conta de armazenamento precisa de um nome exclusivo em nível global. Ela fornece acesso à Internet mundialmente e determina os serviços de armazenamento e opções de redundância.

## Redundância de Armazenamento

| Tipo de Redundância | Descrição | Durabilidade |
|---------------------|-----------|--------------|
| **LRS** (Local Redundant Storage) | Armazenamento com redundância em um único datacenter na região primária. | 11 noves |
| **ZRS** (Zone Redundant Storage) | Armazena dados em três zonas de disponibilidade dentro da região primária. | 12 noves |
| **GRS** (Geo-Redundant Storage) | Armazena os dados em um datacenter na região primária e outro na secundária. | 16 noves |
| **GZRS** (Geo-Zone Redundant Storage) | Armazena os dados em três zonas de disponibilidade na região primária e em um datacenter na região secundária. | 16 noves |

- **LRS**: Recomendado para ambientes não produtivos.
- **ZRS**: Recomendado para ambientes produtivos.

## Tipos de Armazenamento

### Blob do Azure
Ideal para o armazenamento de grandes volumes de dados não estruturados, como textos ou arquivos binários.

### Disco do Azure
Oferece discos persistentes para máquinas virtuais, aplicativos e outros serviços que necessitam de armazenamento.

### Fila do Azure
Serviço de armazenamento e recuperação de mensagens com capacidade de até 64 KB, adequado para grandes volumes de mensagens.

### Arquivos do Azure
Cria um compartilhamento de arquivos de rede altamente disponível, acessível via protocolo SMB (Bloco de Mensagens do Servidor).

### Tabelas do Azure
Fornece uma solução para o armazenamento de dados estruturados não relacionais com chave/atributo, utilizando um design sem esquema.

## Pontos de Extremidade Públicos para Serviços de Armazenamento

| Serviço de Armazenamento | Ponto de Extremidade |
|--------------------------|----------------------|
| **Armazenamento de Blobs** | `https://<nome-da-conta>.blob.core.windows.net` |
| **Data Lake Storage Gen2** | `https://<nome-da-conta>.dfs.core.windows.net` |
| **Arquivos do Azure** | `https://<nome-da-conta>.file.core.windows.net` |
| **Armazenamento de Filas** | `https://<nome-da-conta>.queue.core.windows.net` |
| **Armazenamento de Tabelas** | `https://<nome-da-conta>.table.core.windows.net` |

## Camadas de Acesso no Armazenamento do Azure

- **Frequente**: Otimizado para dados acessados com frequência.
- **Esporádico**: Para dados acessados com pouca frequência e armazenados por pelo menos 30 dias.
- **Frio**: Para dados acessados raramente e armazenados por no mínimo 90 dias.
- **Arquivo Morto**: Para dados raramente acessados e armazenados por pelo menos 180 dias, com latência flexível.

## Migração para o Azure

### Azure Data Box
Uma solução de armazenamento capaz de suportar até 80 terabytes de dados, ideal para migração de backups de recuperação de desastres para o Azure. Oferece transporte seguro de dados e pode ser usada em locais com conectividade limitada.

### AzCopy
Ferramenta de linha de comando que facilita a cópia de blobs ou arquivos de e para o Azure Storage, permitindo sincronização unidirecional.

## Gerenciamento de Armazenamento no Azure
Interface gráfica compatível com Windows, MacOS e Linux, semelhante ao Windows Explorer, que facilita a gestão dos recursos de armazenamento.

## Sincronização de Arquivos no Azure
Oferece sincronização bidirecional entre os arquivos armazenados localmente e no Azure, mantendo os arquivos mais acessados localmente e otimizando o espaço em disco com a camada de nuvem.

# Identidade, Acesso e Segurança

## Microsoft Entra ID
O **Microsoft Entra ID** é o serviço de gerenciamento de identidade e acesso baseado em nuvem no Microsoft Azure. Localmente (on-premises), ele continua conhecido como **Active Directory**.

### Principais Funcionalidades:
- **Autenticação**: Permite que funcionários acessem os recursos com suas credenciais.
- **Logon Único (SSO)**: Um único login concede acesso a vários aplicativos.
- **Gerenciamento de Aplicativos**: Controla o acesso a aplicativos corporativos.
- **Negócios para Negócios (B2B)**: Facilita o gerenciamento de identidade para parceiros externos.
- **Gerenciamento de Dispositivos**: Integra dispositivos de forma segura ao ambiente corporativo.

## Microsoft Entra Domain Services
Com o **Microsoft Entra Domain Services**, você obtém os benefícios dos serviços de domínio baseados em nuvem sem a necessidade de gerenciar controladores de domínio. Ele permite a execução de aplicativos legados que não suportam padrões de autenticação modernos e sincroniza automaticamente com o Microsoft Entra ID.

## Comparação entre Autenticação e Autorização

| **Autenticação**                                      | **Autorização**                                    |
|-------------------------------------------------------|----------------------------------------------------|
| Identifica a pessoa ou serviço que está acessando um recurso. | Define o nível de acesso que a pessoa ou serviço autenticado tem. |
| Solicita credenciais de acesso válidas.               | Determina quais dados e operações estão autorizados. |
| Base para criar controles de identidade e acesso seguros. | Define o que pode ser feito com os dados acessados. |

## Autenticação Multifator (MFA)
A **autenticação multifator** adiciona uma camada extra de segurança ao exigir dois ou mais fatores para autenticação:
- **Algo que você sabe** (ex.: senha)
- **Algo que você possui** (ex.: celular)
- **Algo que você é** (ex.: impressão digital)

## Acesso Condicional
O **Acesso Condicional** aplica regras para garantir segurança com base em:
- Associação de usuário ou grupo.
- Localização por endereço IP.
- Dispositivo usado.
- Aplicativo acessado.
- Detecção de risco.

## Controle de Acesso Baseado em Função (RBAC)
O **RBAC** permite um gerenciamento de acesso granular, atribuindo permissões específicas para funções. Isso garante que cada usuário tenha apenas o acesso necessário para realizar seu trabalho. Ele também habilita o controle de acesso ao portal do Azure e aos recursos.

## Proteção em Camadas
A **proteção em camadas** fornece uma abordagem defensiva em múltiplos níveis, garantindo que ataques a uma camada sejam isolados das demais, aumentando a resiliência do sistema.

## Microsoft Defender para Nuvem
O **Microsoft Defender para Nuvem** é um serviço de monitoramento que protege ambientes de datacenters locais e do Azure. Ele oferece:
- Recomendações de segurança.
- Detecção e bloqueio de malware.
- Análise de ataques potenciais.
- Controle de acesso just-in-time para portas.

# Gerenciamento e Governança

## Fatores que Afetam os Custos

1. **Tipo de Recurso**: Os custos variam conforme o tipo de recurso, com base no uso monitorado por medidores. O número de medidores associados depende do tipo de recurso.
2. **Consumo**: Em um modelo de pagamento por uso, o consumo é o principal fator que gera custos.
3. **Manutenção**: Monitorar o ambiente Azure pode ajudar a identificar e reduzir custos desnecessários, como desligar máquinas virtuais subutilizadas.
4. **Área Geográfica**: O mesmo tipo de recurso pode ter preços diferentes dependendo da localização, impactando os custos do Azure.
5. **Tráfego de Rede**: Transferências de dados de entrada são geralmente gratuitas, mas o custo de dados de saída e entre recursos do Azure pode ser influenciado por zonas de cobrança.
6. **Assinatura**: O tipo de assinatura e sua configuração afetam o custo. Assinaturas gratuitas, por exemplo, permitem explorar recursos do Azure sem custo.

## Azure Marketplace
O **Azure Marketplace** é uma plataforma onde os clientes podem encontrar, testar, comprar e provisionar aplicativos e serviços de centenas de provedores, todos certificados para rodar no Azure. O Marketplace oferece:
- Plataformas de contêiner de software livre.
- Imagens de máquinas virtuais e bancos de dados.
- Software para compilação e implantação de aplicativos.
- Ferramentas para desenvolvedores.
- E muito mais, com mais de 10.000 itens disponíveis.

## Calculadora de Preços
A **Calculadora de Preços** do Azure é uma ferramenta que ajuda a estimar os custos dos produtos Azure. As opções de configuração variam entre produtos, mas incluem:
- Região.
- Camada.
- Opções de cobrança.
- Opções de suporte.
- Programas e ofertas.
- Preços para desenvolvimento e teste.

## Calculadora de Custo Total de Propriedade (TCO)
A **Calculadora TCO** ajuda a estimar a economia ao migrar para o Azure, comparando os custos de infraestrutura local com os custos de uso de produtos e serviços na nuvem Azure.

## Gerenciamento de Custos do Azure
O **Gerenciamento de Custos** oferece várias funcionalidades:
- **Relatórios**: Relatórios detalhados de cobrança.
- **Enriquecimento de Dados**: Aumenta o detalhamento das informações financeiras.
- **Orçamentos**: Permite a definição de limites de gastos.
- **Alertas**: Notificações quando os gastos excedem o orçamento.
- **Recomendações**: Sugestões de otimização de custos.

## Marcas (Tags)
As **Tags** são metadados que podem ser atribuídos a recursos no Azure. Elas:
- Organizam recursos de forma lógica em uma taxonomia.
- Consistem em pares nome-valor.
- São úteis para fins de relatórios e organização, especialmente para análise de custos.

# Governança e Conformidade no Azure

## Azure Policy

O **Azure Policy** é uma ferramenta fundamental para aplicar padrões organizacionais e garantir a conformidade em grande escala. Ele promove uma governança eficaz, garantindo consistência em questões regulatórias, de segurança, custo e gerenciamento. A ferramenta oferece uma avaliação contínua dos recursos do Azure para identificar aqueles que não estão em conformidade com as políticas definidas. Além disso, conta com políticas e iniciativas pré-definidas, categorizadas em áreas como armazenamento, rede, computação, segurança e monitoramento.

## Bloqueios de Recursos

Os **bloqueios de recursos** no Azure oferecem uma camada adicional de proteção, impedindo a exclusão ou modificação acidental de recursos importantes. Eles podem ser aplicados em diferentes níveis, como assinaturas, grupos de recursos ou até em recursos individuais. Esses bloqueios garantem maior controle e segurança em ambientes críticos.

### Tipos de Bloqueios

| Tipo de Bloqueio | Ler | Atualizar | Excluir |
| ---------------- | --- | --------- | ------- |
| **Excluir** | Sim | Sim | Não |
| **Somente Leitura (ReadOnly)** | Sim | Não | Não |

## Microsoft Purview

O **Microsoft Purview** é uma solução abrangente que integra governança, risco e conformidade de dados, oferecendo uma visão unificada dos dados em diferentes ambientes, incluindo locais, multinuvem e SaaS. Ele facilita a **descoberta automatizada de dados**, a **classificação de dados confidenciais** e oferece **linhagem de dados de ponta a ponta**, ajudando as organizações a manter o controle sobre a conformidade de seus dados de forma mais eficiente.

# Ferramentas de Gerenciamento e Implantação no Azure

## Ferramentas para Interagir com o Azure

O Azure oferece uma variedade de ferramentas para facilitar a interação e o gerenciamento de seus recursos:

- **Portal do Azure**: Interface gráfica para gerenciamento e monitoramento de recursos.
- **Azure PowerShell**: Conjunto de cmdlets que permite automatizar tarefas diretamente pelo terminal.
- **Azure Cloud Shell**: Shell interativo acessível diretamente pelo navegador, com suporte para Bash e PowerShell.
- **Interface de Linha de Comando (CLI)**: Ferramenta de linha de comando multiplataforma para gerenciar os serviços Azure.

## Azure Arc

O **Azure Arc** permite a gestão centralizada de recursos de TI, como servidores e clusters Kubernetes, seja em ambientes locais ou em outras nuvens, utilizando o Azure como plataforma de governança. Ele facilita o controle, a segurança e a conformidade, independentemente de onde os recursos estejam localizados.

## Azure Resource Manager (ARM)

O **Azure Resource Manager (ARM)** é uma camada de gerenciamento que possibilita criar, atualizar e excluir recursos dentro da sua assinatura do Azure. Ele oferece uma maneira eficiente de organizar e gerenciar os serviços de forma centralizada.

### Infraestrutura como Código

A abordagem de **Infraestrutura como Código** (IaC) ajuda a manter consistência nas implantações, além de facilitar o gerenciamento de configurações em larga escala. Usando IaC, você pode provisionar novos ambientes rapidamente, utilizando uma configuração padrão, o que garante replicabilidade e agilidade.

## Modelos do Azure Resource Manager (ARM)

Os **modelos do ARM** são arquivos no formato JSON que definem a infraestrutura a ser implantada no Azure. Com uma abordagem declarativa, você pode automatizar a criação de recursos sem a necessidade de escrever comandos manuais. 

Principais características dos modelos ARM:

- **Sintaxe declarativa**: Define os recursos a serem implantados.
- **Resultados repetíveis**: Garante que as mesmas configurações sejam aplicadas em várias implantações.
- **Orquestração**: Coordena a ordem de criação dos recursos.
- **Arquivos modulares**: Suporte a modularidade para gerenciar infraestruturas complexas.
- **Validação integrada**: Permite verificar se o modelo está correto antes de ser implantado.
- **Código exportável**: Capacidade de exportar a configuração para reutilização futura.

# Ferramentas de Monitoramento do Azure

## Assistente do Azure

O **Assistente do Azure** é uma ferramenta que analisa os recursos implantados e fornece recomendações com base nas melhores práticas para otimizar suas implantações no Azure. Ele oferece sugestões em várias categorias:

- **Confiabilidade**: Garantir que seus recursos estejam altamente disponíveis.
- **Segurança**: Recomendações para melhorar a segurança dos seus ativos.
- **Desempenho**: Otimizações para manter a performance ideal de seus aplicativos.
- **Custo**: Dicas para gerenciar e reduzir seus gastos.
- **Excelência Operacional**: Melhoria nas operações e gestão de recursos.

## Integridade do Serviço do Azure

A **Integridade do Serviço do Azure** é um conjunto de serviços que mantém você informado sobre o estado geral do Azure, identificando possíveis problemas que podem impactar seus recursos ou serviços.

- **Status do Azure**: Visão geral da integridade de todos os serviços em todas as regiões do Azure.
- **Integridade do Serviço**: Exibição focada apenas nos serviços e regiões que você está utilizando. Problemas em regiões ou serviços que você não utiliza não são mostrados.
- **Resource Health**: Visão personalizada da integridade dos seus recursos específicos no Azure, fornecendo informações detalhadas sobre o status de cada um.

## Azure Monitor

O **Azure Monitor** é uma ferramenta que maximiza a disponibilidade e o desempenho de seus aplicativos e serviços ao coletar, analisar e agir com base em dados de telemetria. Ele monitora tanto ambientes na nuvem quanto ambientes locais, fornecendo insights cruciais para manter o funcionamento ideal dos seus sistemas.
