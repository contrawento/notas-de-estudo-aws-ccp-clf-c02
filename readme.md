# Notas de estudo para a certificação AWS Cloud Practitioner CLF-02

Essas são as minhas anotações de estudo que fiz enquanto cursava a [trilha da Alura](https://www.alura.com.br/formacao-aws-certified-cloud-practitioner) para essa certificação. Foi dividida em tópicos curtos para referenciar aos conteúdos completos direto da AWS.

Reforço que foi escrita a partir da perspectiva de um profissional de TI atuante, então alguns conceitos foram abstraídos para que o estudo não ficasse cansativo ou repetitivo. Em alguns momentos também é misturado o inglês com o português propositalmente para facilitar a assimilação de alguns conceitos.

> _Importante mencionar que quando fiz essa trilha, os cursos na Alura já estavam um pouco desatualizados, então é importante revisar os conteúdos através das documentações oficiais na AWS._

Fonte: https://aws.amazon.com/pt/certification/certified-cloud-practitioner/

## Sumário <!-- omit from toc -->

- [Notas de estudo para a certificação AWS Cloud Practitioner CLF-02](#notas-de-estudo-para-a-certificação-aws-cloud-practitioner-clf-02)
- [Domínios de conteúdo](#domínios-de-conteúdo)
- [Domínio 3 - Tecnologia e Serviços Cloud](#domínio-3---tecnologia-e-serviços-cloud)
  - [Métodos de Deploying e Operating](#métodos-de-deploying-e-operating)
    - [Elastic Beanstalk](#elastic-beanstalk)
    - [CloudFormation](#cloudformation)
    - [OpsWorks](#opsworks)
    - [CodeCommit](#codecommit)
    - [CodeDeploy](#codedeploy)
    - [CodePipeline](#codepipeline)
    - [Elastic Container Services](#elastic-container-services)
  - [Serviços Globais](#serviços-globais)
  - [Serviços On-Premise](#serviços-on-premise)
  - [IAM - Identity and Access Management](#iam---identity-and-access-management)
    - [Users](#users)
    - [Groups](#groups)
    - [Roles](#roles)
  - [S3 - Simple Storage Service](#s3---simple-storage-service)
  - [EC2 - Elastic Compute Cloud](#ec2---elastic-compute-cloud)
    - [On-Demand Instances](#on-demand-instances)
    - [Reserved Instances](#reserved-instances)
    - [Spot Instances](#spot-instances)
    - [Dedicated Hosts](#dedicated-hosts)
  - [RDS - Relational Database Service](#rds---relational-database-service)
  - [DynamoDB - NoSQL Database](#dynamodb---nosql-database)
  - [Elastic Loading Balance](#elastic-loading-balance)
    - [Application Load Balancer](#application-load-balancer)
    - [Network Load Balancer](#network-load-balancer)
    - [Gateway Load Balancer](#gateway-load-balancer)
  - [Auto Scaling](#auto-scaling)
  - [Well-Architected Framework](#well-architected-framework)
  - [AWS Support](#aws-support)
- [Domain 1 - Conceitos da Nuvem](#domain-1---conceitos-da-nuvem)
  - [As 6 vantagens da Computação em Nuvem](#as-6-vantagens-da-computação-em-nuvem)
  - [IaaS - Infraestrutura como um Serviço](#iaas---infraestrutura-como-um-serviço)
  - [PaaS - Plataforma como um Serviço](#paas---plataforma-como-um-serviço)
  - [SaaS - Software como um Serviço](#saas---software-como-um-serviço)
  - [Modelos de Computação em Nuvem](#modelos-de-computação-em-nuvem)
- [Domain 2 - Segurança e Conformidade](#domain-2---segurança-e-conformidade)
  - [Benefícios da AWS Security](#benefícios-da-aws-security)
  - [Modelo de Resposabilidade Compartilhada](#modelo-de-resposabilidade-compartilhada)
    - [Security of the Cloud - AWS Responsability](#security-of-the-cloud---aws-responsability)
    - [Security in the Cloud - Customer Responsability](#security-in-the-cloud---customer-responsability)
  - [AWS Cloud Compliance](#aws-cloud-compliance)
    - [AWS Artifact](#aws-artifact)
  - [Serviços Relacionados](#serviços-relacionados)
    - [AWS WAF - Web Application Firewall](#aws-waf---web-application-firewall)

# Domínios de conteúdo

A prova de certificação é dividida em quatro domínios:
- **Domain 1:** Cloud Concepts.
- **Domain 2:** Security and Compliance.
- **Domain 3:** Technology and Cloud Services.
- **Domain 4:** Billing, Pricing and Support.

Se você já é um técnico de TI que trabalha ou já tem alguma formação com Cloud, a recomendação é que você comece pelo domínio 3 para conhecer (ou rever) o funcionamento das principais ferramentas e serviços. Depois você segue na ordem 1, 2 e 4.

Fonte: https://docs.aws.amazon.com/pt_br/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html#cloud-practitioner-02-domains

# [Domínio 3 - Tecnologia e Serviços Cloud](https://docs.aws.amazon.com/pt_br/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain3.html)

> _O domínio 3 representa 34% do conteúdo pontuado no exame._

A infraestrutura global da AWS é definida por **AWS Regions** e **Availability Zones**.
- **AWS Regions** é um local físico com múltiplas AZs.
- **Availability Zones** são diferentes datacenters dentro de uma região, com recursos de infraestrutura redundantes.
- Ambos recursos são isolados, porém AZs de uma mesma região são interconectadas por um **low-latency link**.
- **Edge Locations** são endpoints usandos para _cachear_ conteúdo. Frequentemente usado pelo CloudFront e CDNs.

Em questão de **quantidade**:
Edge Locations > Availability Zones > Regions

Para escolher uma AWS Region, leva-se em consideração:
- Leis locais sobre armazenamento de dados.
- Latência para usuários finais.
- Serviços disponíveis na região.

Como formas de acessar os serviços, a plataforma disponibiliza:
- AWS Management Console (Interface WEB).
- Interface de linha de comando (CLI).
- Kits de desenvolvimento (SDKs).

## Métodos de Deploying e Operating

### [Elastic Beanstalk](https://docs.aws.amazon.com/elastic-beanstalk/)

Serviço de deploying e scaling de web applications e serviços desenvolvidos em Java, .NET, PHP, Node.js, Python, Ruby e Go, além de servidores Docker, Apache, NGINX, Passenger e IIS.

Você faz upload do código e a ferramenta faz o deploy automático de forma gratuita.

### [CloudFormation](https://docs.aws.amazon.com/cloudformation/)

Provê uma linguagem comum para provisionar recursos na AWS. Permite utilizar linguagens de programação ou um arquivo de texto simples utilizando templates.

### [OpsWorks](https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/aws-opsworks.html)

Serviço de gerenciamento de configurações que provê instâncias gerenciadas pelo **Chef** e pelo **Puppet**. Permite utilizar essas ferramentas para automatizar deploys e configurações entre **instâncias do EC2**.

### [CodeCommit](https://docs.aws.amazon.com/codecommit/)

É um **source central service** (serviço de gerenciamento de códigos-fonte) que hospeda repositórios baseados em **Git**. Elimina a necessidade de gerenciar a infraestrutura de um sistema de controle de versões.

### [CodeDeploy](https://docs.aws.amazon.com/codedeploy/)

Automatiza deploy de softwares em uma variedade de **serviços de computação** como o **EC2**, **Fargate** e **Lambda** e também em servidores on-premise.

### [CodePipeline](https://docs.aws.amazon.com/codepipeline/)

Automatiza as fases de **build**, **test** e **deploy** no processo de release toda vez que é feita uma alteração no código, baseado em um modelo pré-definido.

Essa ferramenta não possui **upfront fees** nem **long-term commitments**.

### [Elastic Container Services](https://docs.aws.amazon.com/ecs/)

Permite gerenciar containers Docker diretamente pela AWS. Elimina a necessidade de gerenciar a infraestrutura do orquestrador de container.

Dentro do ECS, o **Fargate** é uma interface de gerenciamento de containers que abstrai alguns detalhes de infraestrutura.

## Serviços Globais

Funcionam como um todo **independente de região**.

- **IAM:** Identity and Access Management.
- **Route53:** Serviço de DNS.
- **CloudFront:** Serviço de CDN.
- **SNS:** Notificações.
- **SES:** Serviço de e-mail.

> _**Obs.:** O S3 é um serviço configurado regionalmente mas possui uma visão global._


## Serviços On-Premise

Podem ser executados localmente, **fora da nuvem AWS**.

- **Snowball:** Hardware físico para transferência de grandes volumes de dados.
- **Storage Gateway:** Cache local conectado ao S3.
- **CodeDeploy** e **OpsWorks:** Serviços de gerenciamento e deploy de código, funciona tanto em nuvem quanto localmente.
- **IoT Greengrass:** Intermediário entre dispositivos IoT locais e os serviços da AWS.

## [IAM - Identity and Access Management](https://docs.aws.amazon.com/iam/)

Permite gerenciar de forma segura o acesso à serviços e recursos na AWS para seus usuários.

- Gerenciar usuários IAM e seus acessos.
- Gerenciar roles IAM e suas permissões.
- Gerenciar **usuários federados** e suas permissões.
  - Grupos de usuários administrados externamente.

### Users

Identidades para pessoas ou aplicações específicas.

### Groups

Coleções de usuários para facilitar a gestão de permissões.

### Roles

Identidades temporárias sem credenciais permanentes. Você assume quando precisa e elas expiram automaticamente. Exemplos de uso:
- Serviços AWS acessarem outros serviços.
- Usuários assumirem permissões temporárias.
- Acesso externo controlado.


## [S3 - Simple Storage Service](https://docs.aws.amazon.com/s3/)

Serviço de armazenamento baseado em objeto, planejado para ter **99.999999999%** de disponibilidade.

- Object-based.
- Tamanho máximo de um arquivo é **5 TB**.
- Key é o nome do objeto.
- Armazenamento ilimitado.
- Armazena em buckets.
- Tipos de S3:
  - S3 Standard.
  - S3 Inteligent-Tiering.
  - S3 Standard IA.
  - S3 One Zone IA.
  - S3 Glacier.
  - S3 Glacier Deep Archive.

## [EC2 - Elastic Compute Cloud](https://docs.aws.amazon.com/ec2/)

- Provê capacidade de computação variável na nuvem.
- Reduz o tempo necessário para deploy de um servidor.
- Permite escalar a cacpacidade conforme uso.

### On-Demand Instances

Você paga por cacpacidade de computação por hora, sem compromisso de longo prazo. Se resume a: precisou mais, paga mais. Precisou menos, paga menos.

### Reserved Instances

Provê descontos no uso de instâncias fazendo uma reserva por alguns anos.

### Spot Instances

Ainda mais descontos para quando você precisar de uma instância específica em um pré-determinado espaço de tempo.

### Dedicated Hosts

A AWS te disponibiliza um servidor físico exclusívo. Tipo de instância muito específico, voltado para cenários onde há **requisitos especiais de hardware ou de licenciamento**.

## [RDS - Relational Database Service](https://docs.aws.amazon.com/rds/)

Fornece instâncias de banco de dados com capacidade variável e processos de administração automatizados (configuração de hardware, SO, do próprio banco, atualizações e backups).

É disponibilizado em diversos tipos de instância, inclusive as otimizadas para memória, performance ou I/O.

É possível escolher entre as engines: Amazon Aurora, PostgreSQL, MySQL, Oracle Database, SQL Server e Maria DB.

## [DynamoDB - NoSQL Database](https://docs.aws.amazon.com/dynamodb/)

Um banco de dados **key-value** e de documentos, capaz de entregar altíssima performance em qualquer escala.

Totalmente configurável, multi-região, multimaster com segurança, backup e restore embutidos.

Possui in-memory cache para grandes aplicações na internet.

## [Elastic Loading Balance](https://docs.aws.amazon.com/elasticloadbalancing/)

Automaticamente distribui tráfego entre múltiplos alvos, tais como instâncias EC2, containers e endereços IP. Pode fazer esse controle em uma ou entre várias AZs.

### Application Load Balancer

Faz o balanceamento de tráfego HTTP e HTTPS.

### Network Load Balancer

Faz o controle de balanceamento em conexões TCP, para alta performance no tráfego de rede.

### Gateway Load Balancer

Combina um balanceador de carga de rede com um endpoint da AWS (VPC Endpoint) para distribuir tráfego para dispositivos virtuais de terceiros (firewalls, IDS/IPS e etc.).

## [Auto Scaling](https://docs.aws.amazon.com/autoscaling/)

Ajuda a manter a disponibilidade de aplicacções, automaticamente adicionando ou removendo instâncias EC2 de acordo com condições pré-estabelecidas.

O serviço do Auto Scaling não gera cobrança, é cobrado apenas o recurso aplicado.

## [Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

Conceito desenvolvido para ajudar arquitetos de Cloud a construir ambientes seguros, de alta performance, resiliente e eficiente para suas aplicações.

É baseado em 5 pilares:
- **Excelência operacional:** capacidade de executar e monitrar sistemas para entregar valor comercial.
- **Segurança:** proteger dados, sistemas e ativos contra ameaças e acessos não autorizados.
- **Confiabilidade:** garantir que a aplicação funcione corretamente e se recupere de falhas.
- **Eficiência em performance:** usar recursos computacionais de forma otimizada para atender aos requisitos.
- **Otimização de custos:** executar sistemas ao menos custo possível sem comprometer a qualidade.

> _Obs.: Altamente recomendado ler toda a documentação do framework na AWS._

## [AWS Support](https://docs.aws.amazon.com/aws-support/)

Todos os planos de suporte permitem acesso ao **atendimento ao cliente** (**costumer service**), documentação, whitepapers e forúm de suporte.

Para **atendimento técnico** (**technical support**) e outros recursos de planejamento, deploy e otimização do ambiente, você poder escolher um plano de suporte conforme necessidade.

- **Business+ Support:** Plano mínimo recomendado para workloads de produção na AWS.
- **Enterprise Support:** recomendado para workloads essenciais aos negócicos, que requerem assistência personalizada.
- **Unified Operations:** para workloads de missão crítica que exigem maior resiliência e conhecimento especializado em aplicações.

<br>

# [Domain 1 - Conceitos da Nuvem](https://docs.aws.amazon.com/pt_br/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain1.html)

> _O domínio 1 representa 24% do conteúdo pontuado no exame._

Computação em nuvem é **a entrega sob-demanda de poder de computação**, bancos de dados, aplicações e outros recursos de TI **através da internet** com a **precificação conforme o uso**.

Uma plataforma de serviços da nuvem provê **rápido acesso a recursos de TI flexíveis** e de baixo custo.

Elimina a necessidade de grandes investimentos em harware e o tempo de gerenciamento do hardware.

Permite provisionar **o tipo e o tamanho certo** de recursos computacionais necessários.

Provisionamento quase instântaneo e **você para apenas pelo que utiliza**,

## As 6 vantagens da Computação em Nuvem

- Troca do investimento por despesa variável.
- Benefício de economia devido à escala.
- Provisionamento apenas dos recursos necessários.
- Recursos disponibilizados rapidamente.
- Não tem gastos com manutenção de Data Center.
- Permite ser global em minutos.

## IaaS - Infraestrutura como um Serviço

Contém partes básicas de uma nuvem e provê recursos de redes, computadores (virtual ou até hardware dedicado) e espaço de armazenamento.

## PaaS - Plataforma como um Serviço

Remove a necessidade de **gerenciar a infraestrutura** (hardware e sistemas operacionais) e permite **focar no deployment** e gerenciamento das aplicações.

## SaaS - Software como um Serviço

Provê um **produto completo** que é executado e gerenciado pelo provedor do serviço. Geralmente são chamados de **end-user applications**.

- Toda parte de gerenciamento e infraestrutura é abstraída.

## Modelos de Computação em Nuvem

- **Pública:** todos os recursos são provisionados em uma nuvem remota.
- **Híbrido:** conecta os recursos de uma infraestrutura local com uma nuvem remota.
- **Privada** (on-premise)**:** recursos virtualizados em infraestrutura local, também podem ser chamados de private cloud.

# [Domain 2 - Segurança e Conformidade](https://docs.aws.amazon.com/pt_br/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain2.html)

> _O domínio 2 representa 30% do conteúdo pontuado no exame._

Para a AWS, segurança na nuvem é questão de **altíssima prioridade**. Na nuvem você utiliza **ferramentas de segurança baseadas em software** para monitorar e proteger o fluxo de informações nos seus recursos.



## Benefícios da AWS Security

- **Keep your data safe:** todos os seus dados em datacenters altamente seguros.
- **Meet compliance requirements:** AWS gerencia diversos programas de compliance.
- **Save money:** corte custos utilizando os datacenters da AWS, sem precisar gerenciar as instalações.
- **Scale quickly:** A segurança escala conforme o seu uso da nuvem.

## Modelo de Resposabilidade Compartilhada

**Segurança e conformidade são de responsabilidade compartilhada entre a AWS e o cliente.** Este modelo compartilhado alivia a carga operacional do cliente enquanto a AWS gerencia **os componentes do sistema operacional e camada de virtualização até a infraestrutura física** onde os serviços operam.

O cliente assume a responsabilidade pelo **sistema operacional virtualizado** (incluindo **atualizações e patches de segurança**), **softwares de aplicação** assim como a **configuração de security groups** no firewall da AWS.

Essas responsabilidades **podem variar dependendo do serviço utilizado**, da integração com seu ambiente de TI e **leis e regulações** que possam ser aplicáveis.

A diferenciação dessa responsabilidade é comumente referida como "Security **of the cloud**" (AWS) versus "Security **in the cloud**" (cliente).

 
|                               Cliente (in the cloud)                               |                 AWS (of the cloud)                 |
| :--------------------------------------------------------------------------------: | :------------------------------------------------: |
|                                  Dados do cliente                                  |                      Software                      |
|                  Plataforma, aplicações, gerenciamento de acessos                  | Computação, armazenamento, banco de dados e redes  |
|                Sistema Operacional, rede e configuração de Firewall                |         Hardware e infraestrututra global          |
| Client e Server-side encryption, integridade de autenticação e proteção de tráfego | Regiões, zonas de disponibilidade e Edge Locations |

> _Obs.: Alguns detalhes variam conforme o serviço._

### Security of the Cloud - AWS Responsability

A AWS é responsável por **proteger a infraestrutura dos serviços ofereciedos na cloud**, composta pelo **hardware**, **software**, **rede** e **instalações**(data centers) que executam os serviços.

### Security in the Cloud - Customer Responsability

A responsabilidade do cliente é definida **conforme os serviços contratados**.

Em um serviço como o EC2 (IaaS) requer que **o cliente faça toda a configuração de segurança e gerenciamento** de suas instâncias.

Para serviços abstraídos, como o **S3** e o **DynamoDB**, a AWS opera a camada de infraestrutura, SO e plataforma. Aqui **o cliente fica responsável por gerenciar os dados** (incluindo criptografia), classificar os recursos e **aplicar as devidas permissões com o IAM**.

## AWS Cloud Compliance

Baseado nos "tradicional programs", ajudam o cliente a estabelecer um ambiente controlado e seguro na nuvem.

A infraestrutura da AWS é desenhada e gerenciada **alinhado com as melhores práticas de segurança** e atendendo a uma variedade de **padrões de segurança em TI**:
- SOC1/ISAE 3402, SOC2, SOC3.
- FISMA, DIACAP, FedRAMP.
- PCI DSS Level 1.
- ISO 9001, ISO 27001, ISO 27017 e ISO 27018.

### AWS Artifact

Uma lista de documentos referentes a segurança e conformidade na AWS.

## Serviços Relacionados

### AWS WAF - Web Application Firewall

Te ajuda a proteger **suas aplicações web** ou **APIs** contra os **web exploits** mais comuns que podem afetar a disponibilidade, comprometer a segurança ou consumir recursos em excesso.

Te permite controlar **como o tráfego chega nas suas aplicações** criando **regras de segurança** que bloqueia os tipos de ataque mais comuns, como **SQL Injection** ou **cross-site scripting** e regras que filtram tráfegos específicos **conforme você definir**.

O custo é baseado em quantas regras você define e em quantas requisições a aplicação recebe.

Pode ser utilizado na **AWS CloudFront** como parte de um CDN, no **Application Load Balancer** para servidores rodando no EC2 ou **Amazon API Gateway** para suas APIs.


