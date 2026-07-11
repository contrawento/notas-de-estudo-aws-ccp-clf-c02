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

# Domínios de conteúdo

A prova de certificação é dividida em quatro domínios:
- **Domain 1:** Cloud Concepts.
- **Domain 2:** Security and Compliance.
- **Domain 3:** Technology and Cloud Services.
- **Domain 4:** Billing, Pricing and Support.

Se você já é um técnico de TI que trabalha ou já tem alguma formação com Cloud, a recomendação é que você comece pelo domínio 3 para conhecer (ou rever) o funcionamento das principais ferramentas e serviços. Depois você segue na ordem 1, 2 e 4.

Fonte: https://docs.aws.amazon.com/pt_br/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html#cloud-practitioner-02-domains

# Domínio 3 - Tecnologia e Serviços Cloud

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

- IAM: Identity and Access Management.
- Route53: Serviço de DNS.
- CloudFront: Serviço de CDN.
- SNS: Notificações.
- SES: Serviço de e-mail.

> _**Obs.:** O S3 é um serviço configurado regionalmente mas possui uma visão global._