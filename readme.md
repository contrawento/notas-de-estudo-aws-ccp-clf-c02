# Notas de estudo para a certificação AWS Cloud Practitioner CLF-02

Essas são as minhas anotações de estudo que fiz enquanto cursava a [trilha da Alura](https://www.alura.com.br/formacao-aws-certified-cloud-practitioner) para essa certificação. Foi dividida em tópicos curtos para referenciar aos conteúdos completos direto da AWS.

Reforço que foi escrita a partir da perspectiva de um profissional de TI atuante, então alguns conceitos foram abstraídos para que o estudo não ficasse cansativo ou repetitivo. Em alguns momentos também é misturado o inglês com o português propositalmente para facilitar a assimilação de alguns conceitos.

> _Importante mencionar que quando fiz essa trilha, os cursos na Alura já estavam um pouco desatualizados, então é importante revisar os conteúdos através das documentações oficiais na AWS._

Fonte: https://aws.amazon.com/pt/certification/certified-cloud-practitioner/

## Sumário <!-- omit from toc -->

- [Notas de estudo para a certificação AWS Cloud Practitioner CLF-02](#notas-de-estudo-para-a-certificação-aws-cloud-practitioner-clf-02)
- [Domínios de conteúdo](#domínios-de-conteúdo)
- [Domínio 3 - Tecnologia e Serviços Cloud](#domínio-3---tecnologia-e-serviços-cloud)
  - [Formas de acessar os serviços da AWS](#formas-de-acessar-os-serviços-da-aws)
  - [Computação](#computação)
  - [Armazenamento](#armazenamento)
  - [Banco de Dados](#banco-de-dados)
  - [Rede e Entrega (Networking \& Delivery)](#rede-e-entrega-networking--delivery)
  - [Métodos de Deploying e Operating](#métodos-de-deploying-e-operating)
    - [Os "6 R's" da Estratégia de Migração para a AWS](#os-6-rs-da-estratégia-de-migração-para-a-aws)
  - [Serviços Globais](#serviços-globais)
  - [Serviços On-Premise (Híbridos)](#serviços-on-premise-híbridos)
  - [Well-Architected Framework](#well-architected-framework)
    - [4 Estratégias Clássicas de Disaster Recovery (DR) suportadas pela AWS](#4-estratégias-clássicas-de-disaster-recovery-dr-suportadas-pela-aws)
  - [Resumo do Domínio 3](#resumo-do-domínio-3)
- [Domain 1 - Conceitos da Nuvem](#domain-1---conceitos-da-nuvem)
  - [As 6 vantagens da Computação em Nuvem](#as-6-vantagens-da-computação-em-nuvem)
  - [IaaS - Infraestrutura como um Serviço](#iaas---infraestrutura-como-um-serviço)
  - [PaaS - Plataforma como um Serviço](#paas---plataforma-como-um-serviço)
  - [SaaS - Software como um Serviço](#saas---software-como-um-serviço)
  - [Modelos de Computação em Nuvem](#modelos-de-computação-em-nuvem)
  - [Resumo do Domínio 1](#resumo-do-domínio-1)
- [Domain 2 - Segurança e Conformidade](#domain-2---segurança-e-conformidade)
  - [Benefícios da AWS Security](#benefícios-da-aws-security)
  - [Modelo de Resposabilidade Compartilhada](#modelo-de-resposabilidade-compartilhada)
    - [Security of the Cloud - AWS Responsability](#security-of-the-cloud---aws-responsability)
    - [Security in the Cloud - Customer Responsability](#security-in-the-cloud---customer-responsability)
  - [AWS Cloud Compliance](#aws-cloud-compliance)
    - [AWS Artifact](#aws-artifact)
  - [IAM - Identity and Access Management](#iam---identity-and-access-management)
    - [IAM Identity Center](#iam-identity-center)
    - [IAM Access Analyzer](#iam-access-analyzer)
  - [AWS Secrets Manager](#aws-secrets-manager)
  - [AWS WAF - Web Application Firewall](#aws-waf---web-application-firewall)
  - [AWS Shield - Proteção DDoS](#aws-shield---proteção-ddos)
  - [Amazon Inspector](#amazon-inspector)
  - [AWS Trusted Advisor](#aws-trusted-advisor)
  - [Amazon GuardDuty](#amazon-guardduty)
  - [CloudTrail](#cloudtrail)
  - [CloudWatch](#cloudwatch)
  - [AWS Config](#aws-config)
  - [AWS Control Tower](#aws-control-tower)
  - [Service Control Policies (SCPs)](#service-control-policies-scps)
  - [Athena](#athena)
  - [Macie](#macie)
  - [Resumo dos Serviços](#resumo-dos-serviços)
  - [Resumo do Domínio 2](#resumo-do-domínio-2)
- [Domain 4 - Cobranças, Precificação e Suporte](#domain-4---cobranças-precificação-e-suporte)
  - [Pay-as-you-go - Pague pelo uso](#pay-as-you-go---pague-pelo-uso)
  - [Save when you reserve - Economize com reservas](#save-when-you-reserve---economize-com-reservas)
    - [Regional vs. Zonal Reserved Instances](#regional-vs-zonal-reserved-instances)
  - [Pay less by using more - Pague menos por usar mais](#pay-less-by-using-more---pague-menos-por-usar-mais)
  - [Fundamentos da precificação](#fundamentos-da-precificação)
  - [AWS Billing and Cost Management](#aws-billing-and-cost-management)
  - [Serviços Gratuitos](#serviços-gratuitos)
  - [AWS Free Tier](#aws-free-tier)
  - [Pontos de precificação em cada serviço](#pontos-de-precificação-em-cada-serviço)
    - [Amazon EC2](#amazon-ec2)
    - [AWS Lambda](#aws-lambda)
    - [Amazon EBS](#amazon-ebs)
    - [Amazon S3](#amazon-s3)
    - [Amazon RDS](#amazon-rds)
  - [Resource Groups](#resource-groups)
    - [Tags para Cost Allocation](#tags-para-cost-allocation)
  - [AWS Organizations](#aws-organizations)
  - [AWS Pricing Calculator](#aws-pricing-calculator)
  - [AWS Support](#aws-support)
  - [AWS Marketplace e Service Catalog](#aws-marketplace-e-service-catalog)
  - [Resumo Rápido do Domínio 4](#resumo-rápido-do-domínio-4)
- [Links Úteis](#links-úteis)

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
- **Edge Locations** são endpoints usandos para fazer caching de conteúdo, frequentemente usado pelo CloudFront e serviços de CDNs.
  - **AWS Local Zones** são um tipo de infraestrutura AWS que estende os serviços da AWS para mais localidades, permitindo executar aplicações sensíveis à latência mais próximas dos usuários finais. Elas colocam serviços de computação, armazenamento, banco de dados e outros serviços AWS **perto de grandes centros populacionais onde uma Região AWS não existe**. Para começar a usar, é necessário opt-in (aceitar ativamente) pela zona Local Zone desejada.

Em questão de **quantidade**:
- Edge Locations > Availability Zones > Regions
  - 30+ Regiões, 90+ AZs, 400+ Edge Locations (incluindo Regional Edge Caches).

Para escolher uma AWS Region, leva-se em consideração:
- Leis locais sobre armazenamento de dados (residência de dados).
- Latência para usuários finais (proximidade geográfica).
- Serviços disponíveis na região (nem todo serviço está disponível em toda região).

## Formas de acessar os serviços da AWS

Como formas de acessar os serviços, a plataforma disponibiliza:
- AWS Management Console (Interface WEB).
- Interface de linha de comando (CLI).
- Kits de desenvolvimento (SDKs) para diversas linguagens.

## Computação

- **[EC2 - Elastic Compute Cloud](https://docs.aws.amazon.com/ec2/):** Provê capacidade de computação variável na nuvem. Reduz o tempo necessário para deploy de um servidor e permite escalar a capacidade conforme uso. Oferece diferentes modelos de precificação (On-Demand, Reserved, Spot, Dedicated Hosts) e famílias de instâncias otimizadas para computação, memória, armazenamento ou GPU.
- **[Lambda](https://docs.aws.amazon.com/lambda/):** Serviço de computação serverless que executa código em resposta a eventos. Você paga apenas pelo tempo de execução e número de requisições, sem gerenciar servidores.
- **[Elastic Beanstalk](https://docs.aws.amazon.com/elastic-beanstalk/):** Serviço de deploying e scaling de web applications e serviços desenvolvidos em Java, .NET, PHP, Node.js, Python, Ruby e Go, além de servidores Docker, Apache, NGINX, Passenger e IIS. Você faz upload do código e a ferramenta faz o deploy automático de forma gratuita (paga apenas pelos recursos aplicados).
- **[ECS - Elastic Container Service](https://docs.aws.amazon.com/ecs/):** Permite gerenciar containers Docker diretamente pela AWS. Elimina a necessidade de gerenciar a infraestrutura do orquestrador de container. Dentro do ECS, o **Fargate** é uma interface de gerenciamento de containers que abstrai completamente a camada de infraestrutura (serverless para containers).
- **[EKS - Elastic Kubernetes Service](https://docs.aws.amazon.com/eks/):** Serviço gerenciado de Kubernetes, similar ao ECS, mas utilizando o padrão Kubernetes (open-source). Permite executar workloads Kubernetes sem precisar gerenciar o plano de controle.
- **[Outposts](https://docs.aws.amazon.com/outposts/):** Hardware da AWS instalado fisicamente no datacenter do cliente, permitindo executar serviços AWS (EC2, EBS, RDS, etc.) localmente, com integração total à nuvem pública da AWS. Ideal para baixa latência ou residência de dados.
- **[Amazon AppStream 2.0](https://docs.aws.amazon.com/appstream2/):** **Streaming de aplicações** totalmente gerenciado que permite transmitir aplicações desktop para usuários sem reescrever o código. Ele gerencia os recursos AWS necessários para hospedar e executar suas aplicações, escala automaticamente e fornece acesso sob demanda. Os usuários podem acessar as aplicações a partir de navegadores compatíveis com HTML5.

## Armazenamento

- **[S3 - Simple Storage Service](https://docs.aws.amazon.com/s3/):** Serviço de armazenamento baseado em objeto, planejado para ter **99.999999999%** de disponibilidade (11 noves).
  - Object-based (armazena arquivos como objetos).
  - Tamanho máximo de um arquivo é **5 TB**.
  - Key é o nome do objeto (identificador único no bucket).
  - Armazenamento ilimitado.
  - Armazena em buckets (contêineres lógicos).
  - Classes de armazenamento (Storage Classes):
    - S3 Standard (dados acessados com frequência).
    - S3 Intelligent-Tiering (move automaticamente entre camadas).
    - S3 Standard IA (acesso infrequente).
    - S3 One Zone IA (dados replicados em uma única AZ).
    - S3 Glacier (arquivamento de longo prazo, leva minutos/horas para recuperação).
    - S3 Glacier Deep Archive (arquivamento com recuperação em até 12 horas, mas por um menor custo).
- **[EBS - Elastic Block Store](https://docs.aws.amazon.com/ebs/):** Volumes de armazenamento em bloco para uso com instâncias EC2. Persistem independentemente da vida útil da instância. Cobrado por GB e por IOPS.
- **[EFS - Elastic File System](https://docs.aws.amazon.com/efs/):** Sistema de arquivos compartilhado (NFS) para EC2, escala automaticamente e é cobrado pelo uso.
- **[FSx for Windows File Server]():** Permite lançar e escalar armazenamento de arquivos compartilhados para suas aplicações e usuários finais. É um serviço totalmente gerenciado que fornece sistemas de arquivos com suporte ao protocolo SMB. Ideal para migrar servidores de arquivos Windows para a AWS.
- **[Storage Gateway](https://docs.aws.amazon.com/storagegateway/):** Gateway híbrido que conecta ambientes on-premise ao armazenamento da AWS (S3, EBS, etc.). Atua como um cache local para dados armazenados na nuvem.
- **[Snow Family](https://docs.aws.amazon.com/snowball/):** Dispositivos físicos para transferência de grandes volumes de dados para a AWS ou para edge computing.
  - **Snowcone:** dispositivo pequeno, portátil (8 TB), com capacidade de edge computing.
  - **Snowball Edge:** dispositivo robusto com até 80 TB de armazenamento, muito usado para migrações.
  - **Snowmobile:** contêiner de 100 PB para transferências de dados excepcionalmente massivas.

## Banco de Dados

- **[RDS - Relational Database Service](https://docs.aws.amazon.com/rds/):** Fornece instâncias de banco de dados relacionais com capacidade variável e processos de administração automatizados (configuração de hardware, SO, do próprio banco, atualizações e backups). É disponibilizado em diversos tipos de instância, inclusive otimizadas para memória, performance ou I/O.
  - Engines suportadas: Amazon Aurora, PostgreSQL, MySQL, Oracle Database, SQL Server e MariaDB.
- **[DynamoDB](https://docs.aws.amazon.com/dynamodb/):** Banco de dados **key-value** e de documentos (NoSQL), capaz de entregar altíssima performance em qualquer escala. Totalmente configurável, multi-região, multimaster com segurança, backup e restore embutidos.
  - Possui in-memory cache (DAX) para grandes aplicações.
- **[Aurora](https://docs.aws.amazon.com/aurora/):** Banco de dados relacional compatível com MySQL e PostgreSQL, mas com desempenho até 5x maior que o MySQL padrão e 3x maior que o PostgreSQL. Totalmente gerenciado, com armazenamento distribuído e replicação automática.
- **[Redshift](https://docs.aws.amazon.com/redshift/):** Data warehouse (armazenamento analítico) baseado em colunas, otimizado para consultas complexas em grandes volumes de dados.
- **[DMS - Database Migration Service](https://docs.aws.amazon.com/dms/):** Migra bancos de dados relacionais, NoSQL e data warehouses com mínimo downtime. Suporta migrações homogêneas (ex: Oracle para Oracle) e heterogêneas (ex: Oracle para Aurora) com **schema conversion**.

## Rede e Entrega (Networking & Delivery)

- **[VPC - Virtual Private Cloud](https://docs.aws.amazon.com/vpc/):** Rede virtual isolada logicamente dentro da AWS. Componentes principais:
  - Sub-redes (públicas e privadas) distribuídas entre AZs.
  - Internet Gateway (acesso à internet para sub-redes públicas).
  - NAT Gateway (acesso à internet para sub-redes privadas).
  - Network ACLs (firewall stateless a nível de sub-rede) e Security Groups (firewall stateful a nível de instância).
- **[Direct Connect](https://docs.aws.amazon.com/directconnect/):** Vincula sua rede privada a um local do Direct Connect por meio de um cabo de fibra óptica dedicado. É um serviço consistente e privado, pois sua empresa é a única usuária do link.
- **[Route 53](https://docs.aws.amazon.com/route53/):** Serviço de DNS gerenciado, com alta disponibilidade e escalabilidade. Permite rotear usuários para aplicações dentro e fora da AWS.
- **[CloudFront](https://docs.aws.amazon.com/cloudfront/):** Serviço de CDN que distribui conteúdo com baixa latência utilizando a rede global de Edge Locations. Integra-se com S3, ELB, EC2 e Lambda@Edge.
- **[AWS Wavelenght]():** Incorpora serviços de computação e armazenamento da AWS dentro dos data centers de provedores de telecomunicações na borda da rede 5G. As Wavelength Zones são associadas a uma Região AWS e permite que desenvolvedores construam **aplicações que entregam latência ultrabaixa** para dispositivos móveis e usuários finais.
- **[ELB - Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/):** Automaticamente distribui tráfego entre múltiplos alvos, tais como instâncias EC2, containers e endereços IP. Pode fazer esse controle em uma ou entre várias AZs.
  - **Application Load Balancer (ALB):** Balanceamento de tráfego HTTP e HTTPS (camada 7).
  - **Network Load Balancer (NLB):** Balanceamento de conexões TCP/UDP (camada 4), para alta performance e baixa latência.
  - **Gateway Load Balancer (GWLB):** Combina um balanceador de carga de rede com um endpoint da AWS (VPC Endpoint) para distribuir tráfego para dispositivos virtuais de terceiros (firewalls, IDS/IPS, etc.).
- **[Auto Scaling](https://docs.aws.amazon.com/autoscaling/):** Ajuda a manter a disponibilidade de aplicações, automaticamente adicionando ou removendo instâncias EC2 de acordo com condições pré-estabelecidas.
  - O serviço do Auto Scaling não gera cobrança, é cobrado apenas o recurso aplicado.

## Métodos de Deploying e Operating

- **[Application Migration Service (MGN)](https://docs.aws.amazon.com/mgn/):** Solução **lift-and-shift** automatizada. Pode migrar servidores físicos e quaisquer banco de dados ou aplicativos executados neles para instâncias do EC2.
- **[CloudFormation](https://docs.aws.amazon.com/cloudformation/):** Provê uma linguagem comum (Infrastructure as Code – IaC) para provisionar recursos na AWS. Permite utilizar linguagens de programação ou um arquivo de texto simples utilizando templates (YAML/JSON).
- **[OpsWorks](https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/aws-opsworks.html):** Serviço de gerenciamento de configurações que provê instâncias gerenciadas pelo **Chef** e pelo **Puppet**. Permite utilizar essas ferramentas para automatizar deploys e configurações entre instâncias do EC2.
- **[CodeCommit](https://docs.aws.amazon.com/codecommit/):** Serviço de gerenciamento de código-fonte que hospeda repositórios baseados em **Git**. Elimina a necessidade de gerenciar a infraestrutura de um sistema de controle de versões.
- **[CodeDeploy](https://docs.aws.amazon.com/codedeploy/):** Automatiza deploy de softwares em uma variedade de serviços de computação como **EC2**, **Fargate** e **Lambda** e também em servidores on-premise.
- **[CodePipeline](https://docs.aws.amazon.com/codepipeline/):** Automatiza as fases de **build**, **test** e **deploy** no processo de release toda vez que é feita uma alteração no código, baseado em um modelo pré-definido. Não possui **upfront fees** nem **long-term commitments**.
- **[AWS Step Functions](docs.aws.amazon.com/step-functions/):** **Orquestração serverless** que permite criar fluxos de trabalho (chamados de state machines) para construir aplicações distribuídas, automatizar processos, orquestrar microsserviços e criar pipelines de dados e machine learning. Ele gerencia a lógica da aplicação, implementando branches, execuções paralelas e timeouts, além de executar retries automáticos em caso de erros. Integra-se com mais de 220 serviços AWS e endpoints HTTPS.

### Os "6 R's" da Estratégia de Migração para a AWS

São abordagens para mover aplicações para a nuvem:
- **Rehost ("Lift and Shift"):** mover aplicações para AWS com mudanças mínimas. Estratégia mais rápida.
- **Replatform ("Lift, Tinker, and Shift"):** fazer otimizações mínimas para melhorar performance.
- **Refactor/Re-architect:** reescrever e reestruturar a aplicação para aproveitar ao máximo a nuvem.
- **Repurchase:** substituir a aplicação por um produto SaaS ou solução de terceiros.
- **Retire:** descomissionar aplicações que não são mais necessárias.
- **Retain:** manter a aplicação on-premise por enquanto, migrando futuramente.

> _Obs.: A AWS também menciona uma sétima estratégia (Relocate) em algumas documentações, mas os 6 Rs são os mais consolidados._

## Serviços Globais

Funcionam como um todo **independente de região**.

- **IAM:** Identity and Access Management.
- **Route53:** Serviço de DNS.
- **CloudFront:** Serviço de CDN.
- **SNS:** Simple Notification Service (notificações pub/sub).
- **SES:** Simple Email Service (envio de e-mails).

> _**Obs.:** O S3 é um serviço configurado regionalmente mas possui uma visão global._

## Serviços On-Premise (Híbridos)

Podem ser executados localmente, **fora da nuvem AWS**.

- **Snow Family** (Snowcone, Snowball, Snowmobile): hardware físico para transferência de grandes volumes de dados.
- **Storage Gateway:** cache local conectado ao S3 ou EBS.
- **CodeDeploy** e **OpsWorks:** Serviços de gerenciamento e deploy de código, funcionam tanto em nuvem quanto localmente.
- **IoT Greengrass:** Intermediário entre dispositivos IoT locais e os serviços da AWS.
- **Outposts:** Já citado em ["Computação"](#computação).

## [Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

Conceito desenvolvido para ajudar arquitetos de Cloud a construir ambientes seguros, de alta performance, resilientes e eficientes para suas aplicações.

É baseado em **5 pilares**:

- **Excelência operacional:** capacidade de executar e monitorar sistemas para entregar valor comercial.
- **Segurança:** proteger dados, sistemas e ativos contra ameaças e acessos não autorizados.
- **Confiabilidade:** garantir que a aplicação funcione corretamente e se recupere de falhas.
- **Eficiência em performance:** usar recursos computacionais de forma otimizada para atender aos requisitos.
- **Otimização de custos:** executar sistemas ao menor custo possível sem comprometer a qualidade.

Além do framework conceitual, a AWS disponibiliza a **[Well-Architected Tool](https://aws.amazon.com/well-architected-tool/)**, uma ferramenta gratuita que revisa suas workloads contra os 5 pilares e gera um relatório com recomendações práticas de melhoria.

> _Obs.: Altamente recomendado ler toda a documentação do framework na AWS._

###  4 Estratégias Clássicas de Disaster Recovery (DR) suportadas pela AWS

As estratégias de disaster recovery na AWS são categorizadas em quatro abordagens, variando em custo e complexidade:
| Estratégia               |                                                           Descrição                                                            |            RTO/RPO             |
| :----------------------- | :---------------------------------------------------------------------------------------------------------------------------- | :----------------------------: |
| Backup and Restore       |                            Faz backup dos dados (ex: snapshots, S3) e restaura em caso de desastre.                            | Mais simples e de baixo custo. | Horas |
| Pilot Light              | Mantém uma versão mínima da infraestrutura em execução na região de recuperação. Em caso de desastre, escala-se para produção. |       Dezenas de minutos       |
| Warm Standby             |        Mantém uma versão reduzida mas completa da aplicação em execução na região de recuperação, pronta para escalar.         |            Minutos             |
| Multi-Site Active/Active |                 Executa a aplicação em múltiplas regiões simultaneamente, com tráfego distribuído entre elas.                  |           Tempo real           |

## Resumo do Domínio 3

- **Infraestrutura:** Regiões (30+) → AZs (90+) → Edge Locations (400+). Escolha por compliance, latência e serviços.
- **Computação:** EC2 (vários modelos), Lambda (serverless), Beanstalk (PaaS), ECS/EKS (containers), Outposts (híbrido).
- **Armazenamento:** S3 (objetos, várias classes), EBS (blocos), EFS (arquivos), Storage Gateway (cache), Snow Family (transporte físico).
- **Bancos:** RDS (relacional gerenciado), DynamoDB (NoSQL), Aurora (alta performance), Redshift (DW), DMS (migração).
- **Rede:** VPC (sub-redes, gateways), Direct Connect (link dedicado), Route 53 (DNS), CloudFront (CDN), ELB (balanceadores).
- **Deploy/Operação:** CloudFormation (IaC), Code* (Commit, Deploy, Pipeline), OpsWorks (Chef/Puppet), MGN (migração).
- **Well-Architected:** 5 pilares + ferramenta de revisão.

---

# [Domain 1 - Conceitos da Nuvem](https://docs.aws.amazon.com/pt_br/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain1.html)

> _O domínio 1 representa 24% do conteúdo pontuado no exame._

Computação em nuvem é **a entrega sob-demanda de poder de computação**, bancos de dados, aplicações e outros recursos de TI **através da internet** com a **precificação conforme o uso**.

Uma plataforma de serviços da nuvem provê **rápido acesso a recursos de TI flexíveis** e de baixo custo.

Elimina a necessidade de grandes investimentos e o tempo de gerenciamento do hardware.

Permite provisionar **o tipo e o tamanho certo** de recursos computacionais necessários.

Provisionamento quase instântaneo e **você para apenas pelo que utiliza**,

## As 6 vantagens da Computação em Nuvem

- Troca do investimento (CAPEX) por despesa variável (OPEX).
- Benefício de economia devido à escala (economies of scale).
- Provisionamento apenas dos recursos necessários (evita over/under provisioning). 
- Recursos disponibilizados rapidamente (agilidade).
- Não tem gastos com manutenção de Data Center.
- Permite ser global em minutos (alcance mundial).

## IaaS - Infraestrutura como um Serviço

Contém partes básicas de uma nuvem e provê recursos de redes, computadores (virtual ou até hardware dedicado) e espaço de armazenamento. Exemplo: EC2, VPC.

## PaaS - Plataforma como um Serviço

Remove a necessidade de **gerenciar a infraestrutura** (hardware e sistemas operacionais) e permite **focar no deployment** e gerenciamento das aplicações. Exemplo: Elastic Beanstalk, RDS.

## SaaS - Software como um Serviço

Provê um **produto completo** que é executado e gerenciado pelo provedor do serviço. Geralmente são chamados de **end-user applications**. Exemplo: AWS WorkDocs, Microsoft 365.

- Toda parte de gerenciamento e infraestrutura é abstraída.

## Modelos de Computação em Nuvem

- **Pública:** todos os recursos são provisionados em uma nuvem remota, acessíveis pela internet.
- **Híbrido:** conecta os recursos de uma infraestrutura local com uma nuvem remota.
- **Privada (on-premise):** recursos virtualizados em infraestrutura local, também podem ser chamados de private cloud.

## Resumo do Domínio 1

- **6 vantagens:** CAPEX→OPEX, escala, agilidade, sem manutenção, alcance global, provisionamento sob demanda.
- **Modelos de serviço:** IaaS (infra), PaaS (plataforma), SaaS (software).
- **Modelos de implantação:** pública, híbrida, privada.

---

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

Baseado nos "tradicional compliance programs", ajudam o cliente a estabelecer um ambiente controlado e seguro na nuvem.

A infraestrutura da AWS é desenhada e gerenciada **alinhado com as melhores práticas de segurança** e atendendo a uma variedade de **padrões de segurança em TI**:
- SOC1/ISAE 3402, SOC2, SOC3.
- FISMA, DIACAP, FedRAMP.
- PCI DSS Level 1.
- ISO 9001, ISO 27001, ISO 27017 e ISO 27018.

### AWS Artifact

Uma lista de documentos referentes a segurança e conformidade na AWS (relatórios de auditoria, acordos, etc.). Acesso sob demanda.

## [IAM - Identity and Access Management](https://docs.aws.amazon.com/iam/)

Permite gerenciar de forma segura o acesso à serviços e recursos na AWS para seus usuários.

- Gerenciar usuários IAM e seus acessos.
  - Identidades para pessoas ou aplicações específicas.
- Gerenciar grupos IAM e suas permissões.
  - Coleções de usuários para facilitar a gestão de permissões.
- Gerenciar roles IAM e suas permissões.
  - Identidades temporárias sem credenciais permanentes, você assume quando precisa e elas expiram automaticamente.
  - Exemplos de uso: Serviços AWS acessarem outros serviços, usuários assumirem permissões temporárias e acesso externo controlado.
- Gerenciar **usuários federados** e suas permissões.
  - Grupos de usuários administrados externamente.

### IAM Identity Center

IAM Identity Center (anteriormente AWS Single Sign-On) é um serviço de gerenciamento de identidades baseado em nuvem que simplifica o gerenciamento de acesso de usuários em múltiplas contas AWS, aplicações, SDKs e ferramentas. Ele permite conectar usuários da força de trabalho a todas as suas aplicações gerenciadas pela AWS e contas AWS, fornecendo single sign-on (SSO) e gerenciamento centralizado de identidades e acessos.

### IAM Access Analyzer

Ajuda a identificar recursos (como buckets S3 ou roles IAM) na sua organização e contas que são compartilhados com uma entidade externa. Também identifica acessos não utilizados em sua organização e contas, monitorando continuamente todos os roles e usuários IAM. Outras capacidades incluem:
- Validação de políticas IAM contra a gramática de políticas e melhores práticas da AWS.
- Verificações de políticas personalizadas contra padrões de segurança especificados.
- Geração de políticas IAM baseadas em atividades de acesso registradas no CloudTrail.

## AWS Secrets Manager

Ajuda a criptografar, armazenar e recuperar credenciais com segurança para bancos de dados e outros serviços. Permite gerenciar, recuperar e rotacionar credenciais de banco de dados, credenciais de aplicação, tokens OAuth, chaves de API e outros secrets ao longo de seu ciclo de vida. Suporta nativamente a rotação de credenciais para bancos de dados no RDS, clusters no Redshift e provedores SaaS como Salesforce e Snowflake. Elimina a necessidade de hardcodar informações sensíveis em texto plano.

## AWS WAF - Web Application Firewall

Te ajuda a proteger **suas aplicações web** ou **APIs** contra os **web exploits** mais comuns (OWASP Top 10) que podem afetar a disponibilidade, comprometer a segurança ou consumir recursos em excesso.

Te permite controlar **como o tráfego chega nas suas aplicações** criando **regras de segurança** que bloqueia os tipos de ataque mais comuns, como **SQL Injection** ou **cross-site scripting** (XSS) e regras personalizadas (filtro por IP, geolocalização e limitação de requisições).

O custo é baseado em quantas regras você define e em quantas requisições a aplicação recebe.

Pode ser utilizado em conjunto com **CloudFront** (CDN), **Application Load Balancer** (para EC2) ou **Amazon API Gateway**.

## AWS Shield - Proteção DDoS 

Serviço de proteção à ataques DDoS que assegura aplicações rodando na AWS. Disponível em dois níveis:
- **Standard:** Já vem previamente habilitado sem custo. Monitora o tráfego de rede e finaliza conexões que **aparentam ser tráfego malicioso em tempo-real**.
- **Advanced:** Proteção adicional com custo mensal fixo + taxa por uso. Inclui suporte especializado (AWS DDoS Response Team), proteção contra ataques volumétricos complexos e integração com WAF para regras customizadas.

## Amazon Inspector

Serviço de gerenciamento de vulnerabilidades que descobre workloads e as verifica continuamente em busca de exposição não-intencional na rede. Funciona nos recursos EC2, ECR (containers) e funções Lambda.

Quando detectada uma vulnerabilidade, ele cria uma **descoberta**, um relatório detalhado do problema.

## AWS Trusted Advisor

Ferramenta online que provê apoio em tempo real para provisionar recursos **seguindo as melhores práticas**.

Escaneia sua Infraestrutura na AWS e informa ações reccomendadas baseado em **5 categorias**:
- Otimização de custos.
- Performance.
- Segurança.
- Tolerância à falhas.
- Limites de serviços (alertas sobre aproximação de quotas).

## Amazon GuardDuty

Serviço de detecção de ameaças que monitora continuamente, analisa e processa fontes de dados e logs no seu ambiente AWS. Utiliza feeds de inteligência contra ameaças (listas de IPs maliciosos, domínios, hashes de arquivos) e modelos de **machine learning para identificar atividades suspeitas e potencialmente maliciosas**. Detecta cenários como credenciais AWS comprometidas, exfiltração de dados e destruição de dados que podem levar a ataques de ransomware.

## CloudTrail

Serviço que habilita a **auditoria da sua conta** AWS. Monitora todas as atividades (chamadas de API) executadas no ambiente e gera logs detalhados, facilitando futuras consultas, resolução de problemas e análises forenses.

## CloudWatch

Coleta **dados operacionais e de monitoramento** no formato de logs, métricas e eventos, **provendo uma visualização unificada** de recursos, aplicações e serviços da sua infraestrutura.

Pode ser utilizado para **detectar anomalias**, **configurar alarmes**, **visualizar logs** e **métricas**. A partir dessas informações, também é possível **engatilhar ações automatizadas** (ex: Auto Scaling).

## AWS Config 

Gerenciador de configurações gerais dos serviços da AWS. Facilita a aplicação de **regras de compliance** (ex: verificar se S3 buckets estão públicos). Também gera um **histórico de alterações** das configurações ao longo do tempo.

## AWS Control Tower

Serviço que permite impor e gerenciar regras de governança para segurança, operações e conformidade em escala. Ele oferece a maneira mais fácil de configurar e governar um ambiente AWS multi-account seguro e em conformidade, baseado em melhores práticas estabelecidas. Inclui:
- **Landing Zone:** um ambiente bem-arquitetado e multi-account baseado em melhores práticas de segurança e conformidade.
- **Guardrails (controls):** regras preventivas e detectivas que governam seus recursos AWS.
- **Dashboard:** visibilidade contínua do ambiente.

## Service Control Policies (SCPs)

São um tipo de política de organização que oferece controle central sobre as permissões máximas disponíveis para os usuários e roles IAM na sua organização. Ajudam a garantir que as contas permaneçam dentro das diretrizes de controle de acesso. SCPs podem:
- Restringir quais serviços ou ações suas identidades podem usar.
- Restringir quais recursos suas identidades podem acessar.
- Impor requisitos sobre como suas identidades podem acessar recursos.

Elas são aplicadas a nível de conta ou Organizational Unit (OU) e funcionam como um "guarda-chuva" de permissões, nenhuma permissão pode exceder o que o SCP permite.

## Athena

Serviço de **consulta interativa** (**interactive query**) que **facilita a análise de dados** no **S3** utilizando **SQL padrão**.

É um serviço **serverless** e você paga **apenas pelas queries que executar**.

## Macie

Serviço de segurança que utiliza **machine learning** para **automaticamente descobrir**, **classificar** e **proteger dados sensíveis** na AWS (ex: PII, dados financeiros)..

É capaz de reconhecer dados sensíveis e fornece painéis e alertas de como esses dados estão sendo acessados ou movidos.

> _Obs.: Disponível principalmente para dados armazenados no **S3**._

## Resumo dos Serviços

- **AWS WAF:** Impede ataques na camada 7 (SQLi, XSS, etc.).
- **AWS Shield:** Impede ataques DDoS (Standard/Advanced).
- **AWS Inspector:** Rastreia vulnerabilidades em EC2, ECR e Lambda.
- **AWS Trusted Advisor:** Inspeciona a conta para melhores práticas (5 categorias).
- **CloudWatch:** Monitoramento e observabilidade (métricas, logs, alarmes).
- **CloudTrail:** Logs de auditoria de chamadas de API.
- **AWS Config:** Gerenciamento de configurações e histórico de alterações.
- **Athena:** Consultas interativas com SQL no S3.
- **Macie:** Análise e classificação de dados sensíveis com IA no S3.

## Resumo do Domínio 2

- **Modelo de responsabilidade compartilhada:** AWS cuida da segurança **da** nuvem (hardware, rede, hipervisor); cliente cuida da segurança **na** nuvem (SO, aplicações, dados, IAM).
- **Compliance:** AWS atende diversos padrões (ISO, SOC, PCI, FedRAMP), acesse via **AWS Artifact**.
- **Ferramentas de segurança:** WAF (web), Shield (DDoS), Inspector (vulnerabilidades), Macie (dados sensíveis).
- **Governança e auditoria:** CloudTrail (logs API), CloudWatch (métricas/alarmes), Config (histórico/compliance), Trusted Advisor (boas práticas).
- **Análise:** Athena (SQL serverless no S3).

---

# [Domain 4 - Cobranças, Precificação e Suporte](https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain4.html)

> _O domínio 4 representa 12% do conteúdo pontuado no exame._

## Pay-as-you-go - Pague pelo uso

O método de precificação "pague pelo uso" te permite se adaptar as necessidades do negócio sem grandes compromissos. Melhora a **responsividade à mudanças**.

Neste modelo você provê **recursos na infraestrutura conforme a neessidade** ao invés de previsões, reduzindo o risco de **provisionar de mais ou de menos**.

## Save when you reserve - Economize com reservas

Para alguns serviços como **EC2** e **RDS**, você pode investir em **capacidade reservada**, economizando até **75%** comparando com o equivalente sob demanda. As instâncias reservadas estão disponíveis em 3 opções:

- **No upfront (NURI):** reserva sem pagamento adiantado. Ex: 1 ano garante ~32% de desconto.
- **Partial upfront (PURI):** pagando parcialmente adiantado. Ex: 1 ano garante ~42% de desconto.
- **All upfront (AURI):** pagando toda a reserva de forma adiantada, garante a maior economia. Ex: ~45%+ para 1 ano e até ~75% para 3 anos.

### Regional vs. Zonal Reserved Instances

Uma Zonal Reserved Instance é uma instância reservada comprada para uma Zona de Disponibilidade específica. Principais diferenças vs. Reserved Instance Regional:

| Característica           |                Regional RI                 |                  Zonal RI                   |
| :----------------------- | :----------------------------------------: | :-----------------------------------------: |
| Reserva de capacidade    |           Não reserva capacidade           |    Reserva capacidade na AZ especificada    |
| Flexibilidade de AZ      | Desconto aplica-se a qualquer AZ na região |     Desconto apenas na AZ especificada      |
| Flexibilidade de tamanho |       Sim (dentro da mesma família)        | Não (apenas o tipo e tamanho especificados) |
| Queue de compra          |                    Sim                     |                     Não                     |

O preço é o mesmo para ambos os escopos. Zonal RIs são ideais para workloads críticas que precisam de capacidade garantida em uma AZ específica.

## Pay less by using more - Pague menos por usar mais

Na AWS você consegue descontos baseados no volume de uso e realizar economias conforme o consumo aumentar.

Para serviços como o **S3** e **dados transferidos para fora do EC2** o custo é tabelado em camadas (tiered pricing), então quanto mais você usa, menos é pago por GB.

> _Obs.: Dados transferidos **para a AWS** (inbound) são livres de custo na maioria dos serviços._

## Fundamentos da precificação

Há três ponstos principais de custeamento na AWS: **computação**, **armazenamento** e **transferência de dados para fora** (outbound).

Na **maioria dos casos**, não há cobrança para **transferência de dados para dentro da AWS** ou entre serviços **na mesma região**.

## AWS Billing and Cost Management

Serviço utilizado para **pagar sua fatura da AWS**, monitorar o consumo, analisar e controlar seus custos. Recursos:
- Estimar e planejar seus custos na AWS.
- Receber alertas caso seu custo exceda limites pré-configurados.
- Analisar os gastos com cada recurso da AWS.
- Simplificação no gerenciamento das contas múltiplas.

|                                                               AWS Budget (planejamento)                                                                |                                        AWS Cost Explorer (análise)                                        |
| :----------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
| Permite customizar orçamentos (de custo, uso, reservas ou Savings Plans) que te alertam em caso do consumo exceder os limites ou chegar próximo disso. | Interface que permite visualizar relatórios dos custos e recursos ao longo do tempo(gráficos, previsões). |

## Serviços Gratuitos

Alguns serviços de gerenciamento e infraestrutura base não têm custo adicional:
- Amazon VPC.
- CloudFormation.
- Elastic Beanstalk (apenas os recursos provisionados são cobrados).
- Auto Scaling (a ferramenta em si é gratuita).
- IAM.
- OpsWorks.
- AWS Organizations.
- AWS Config (algumas avaliações básicas podem ter custo, mas o serviço de regras customizadas é pago).

## AWS Free Tier

Alguns produtos, plataformas e serviços possuem uma categoria gratuita, que funcionam dentro algumas condições:
- **Sempre gratuito (Always Free):** disponíveis para todos os clientes, sem expiração (ex: 1 milhão de requisições Lambda/mês, 10 GB de armazenamento no DynamoDB).
- **12 meses grátis:** disponíveis para novos clientes por 12 meses a partir da data de criação da conta (ex: EC2 t2.micro, S3 de 5GB, RDS por 750h/mês).
- **Testes (Trials):** expiram em um curto período (ex: SageMaker por 2 meses, Redshift por 2 meses).

## Pontos de precificação em cada serviço

### Amazon EC2

- Horas de servidor (ou segundos, dependendo do OS).
- Tipo de instância (família, tamanho, geração).
- Modelo de precificação.
  - On-Demand Instances: você paga por capacidade de computação por hora, sem compromisso de longo prazo.
  - Reserved Instances: provê descontos no uso de instâncias fazendo uma reserva por alguns anos.
  - Spot Instances: ainda mais descontos para quando você precisar de uma instância específica em um pré-determinado espaço de tempo.
- Número de instâncias.
- Load balancing (ELB custa separadamente).
- Monitoramento detalhado (CloudWatch métricas extras).
- Auto Scaling (sem custo adicional).
- Elastic IP addresses (não utilizados são cobrados).
- Sistemas operacionais e software packages (AMIs pagas).

### AWS Lambda

A duração da execução do código Lambda é levada em consideração (em milissegundos), além da quantidade de memória alocada para a função. Número de invocações também é faturado. O primeiro milhão de requisições/mês é gratuito.

### Amazon EBS 

- **Volumes:** cobrado conforme o tamanho do volume.
- **Snapshots:** O primeiro é sempre **full** e os seguintes são **incrementais**. Também é cobrado pelo tamanho do snapshot.
- **Transferência de dados:** entrada de dados gratuita e saída ccobrada por GBs transferidos.

### Amazon S3

- **Volumes:** cobrado conforme o tamanho provisionado (GB/mês) e tipo (gp3, io1, etc.).
- **Snapshots:** O primeiro snapshot é sempre **full** e os seguintes são **incrementais**. Cobrado pelo total de dados armazenados nos snapshots.
- **Transferência de dados:** entrada de dados gratuita e saída cobrada por GBs transferidos (aplicam-se as mesmas regras gerais).
- 
### Amazon RDS 

- Horas de servidor ativo (por instância).
- Características do banco (engine, versão, tamanho).
- Tipo de pagamento (On-Demand, Reserved).
- Tipo de deploy (Single-AZ ou Multi-AZ – esta última custa o dobro).
- Número de instâncias de banco.
- Armazenamento provisionado (GB/mês).
- Armazenamento adicional (backup, snapshots).
- Requisições de I/O (para alguns engines).
- Transferência de dados (outbound).

## Resource Groups

Coleção de recursos que compartilham uma ou mais tags, independentes de regiões ou zonas de disponibilidade. Facilita o gerenciamento, visualização e automação de tarefas em um grande número de recursos de uma vez só.

### Tags para Cost Allocation 

O AWS Cost Explorer permite filtrar melhor relatórios usando as tags.

Geralmente os clientes utilizam marcacções de negócio como "centro de custo", "cliente" ou "projeto" para associar os custos da AWS com nomeações tradicionais de alocação de custo.

## AWS Organizations

Serviço de gerenciamento de contas que permite consolidar múltiplas contas AWS em uma **organization** onde você centraliza o gerenciamento. Recursos:
- Gerenciamento e definição da organização e das contas AWS.
- Controle de acessos e permissões (Service Control Policies).
- Auditoria, monitoramento e segurança do ambiente para compliance.
- Compartilhe recursos entre contas (Resource Sharing via RAM).
- Centraliza o gerenciamento de **custos e pagamentos** (Consolidated Billing).

Existe um **soft limit** de 20 contas por organização, e um **hard limit** de uma master (paying) account por organização.

> _Obs.: Esse limite de contas pode ser aumentado mediante solicitação._

Para **Consolidated Billing**, a conta master fatura todas as contas filhas, permitindo obter descontos por volume de uso agregado.

## AWS Pricing Calculator

Permite estimar o custo da AWS baseado em templates disponibilizados pela AWS. Você seleciona os serviços e quantidades e a ferramenta gera relatórios com o custo estimado do ambiente configurado. Muito útil para planejamento financeiro antes de provisionar.

## [AWS Support](https://docs.aws.amazon.com/aws-support/)

Todos os planos de suporte permitem acesso ao **atendimento ao cliente** (**customer service**), documentação, whitepapers e fórum de suporte (comunidade).

Para **atendimento técnico** (**technical support**) e outros recursos de planejamento, deploy e otimização do ambiente, você pode escolher um plano de suporte conforme a necessidade:

- **Basic (gratuito):** Suporte a faturas, acesso à documentação, whitepapers, fóruns da comunidade. Sem suporte técnico.
- **Developer:** Ideal para testes e desenvolvimento. Suporte técnico durante horário comercial (ex: resposta em até 12h para questões gerais, 24h para sistemas em produção). Acesso ao Trusted Advisor (checklists básicas).
- **Business:** Mínimo recomendado para workloads de produção. Suporte técnico 24/7 com tempos de resposta mais rápidos (ex: < 1h para interrupção de produção). Acesso a todas as verificações do Trusted Advisor e a API de suporte.
- **Enterprise:** Recomendado para workloads essenciais aos negócios (missão crítica) que requerem assistência personalizada. Inclui um Technical Account Manager (TAM) dedicado, revisão de arquitetura (Well-Architected), suporte proativo e tempos de resposta ainda menores (ex: < 15 min para interrupção crítica).

## AWS Marketplace e Service Catalog

- **[AWS Marketplace](https://aws.amazon.com/marketplace):** Catálogo digital com soluções de terceiros (AMIs, SaaS, softwares, etc.). A cobrança desses produtos pode ser consolidada na fatura AWS (billing consolidado), simplificando o processo de compra.
- **[AWS Service Catalog](https://aws.amazon.com/servicecatalog):** Permite criar e gerenciar catálogos de serviços aprovados para sua organização. Os administradores definem quais recursos (instâncias EC2, bancos, etc.) podem ser provisionados e os usuários finais solicitam apenas a partir desse catálogo aprovado, garantindo governança e compliance.

## Resumo Rápido do Domínio 4

- **Modelos de precificação:** On-Demand (pay as you go), Reserved (1/3 anos, até 75% desconto), Savings Plans (flexibilidade para EC2/Fargate/Lambda), Spot (ociosos, até 90%).
- **Custos principais:** computação, armazenamento, transferência outbound.
- **Ferramentas de custo:** Cost Explorer (análise), Budgets (alertas), Anomaly Detection (ML), Pricing Calculator (estimativa).
- **Free Tier:** Sempre grátis, 12 meses, Trials.
- **Organizações:** Consolidated Billing, SCPs, Resource Groups com tags.
- **Suporte:** Basic (grátis), Developer, Business (produção), Enterprise (TAM dedicado).
- **Marketplace:** compra de soluções de terceiros.
- **Service Catalog:** catálogo interno de serviços aprovados.

---

# Links Úteis

- Cursos:
  - https://skillbuilder.aws/category/exam-prep/cloud-practitioner-foundational-CLF-C02

- Simulados:
  - https://skillbuilder.aws/learn/E4W52ZKK6P/official-practice-question-set-aws-certified-cloud-practitioner-clfc02--portugus/PHFTZJJQK2
  - https://www.techknow.com.br/tools/aws-cloud-practitioner
