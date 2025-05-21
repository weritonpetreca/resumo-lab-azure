# Resumo do Lab Azure
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab sobre azure na DIO.

## Tipos de modelos de Nuvem:
Privadas: 
-Públicas:
-Híbridas:
-Multicloud*:

## Gastos financeiros:
-CaPex: Dispêndio com estruturas físicas;
-OpEx: Gastos operacionais de recursos utilizados;

PAYG - Pay as You Go: Pague somente por aquilo que utilizar;

Previsibilidade de custos através de relatórios, calculadoras e escolha de recursos sendo utilizados;

## Benefícios da Nuvem:
-Alta disponibilidade: Maior tempo possivel do serviço ativo -> 99% / 99,9% / 99,95% /99,99%. Por contrato existe um tempo que pode ficar fora por semana/mês. Passando disso é garantido créditos para serem utilizados pelo contratante em outros serviços. SLA (Service Level Agreement)

-Escalabilidade: Ajustar a capacidade do recurso para se ajustar à demanda quando detectado a necessidade.

-Elasticidade: Poder dimensionar o ambiente através de requisições. Ajustar conforme a quantidade de uso, tanto aumentar quanto diminuir.

-Confiabilidade (Resiliência): Design descentralizado para implementações em várias regiões do mundo. Caso uma região passe por instabilidade outra poderá ser acionada.

-Previsibilidade (Confiança): Well-Architected Framework;

-Segurança: Oferece ferramentas, a implementação é responsabilidade pelo cliente.

-Governança (Auditoria): Padrões de gestão corporativa, regulamentação. Modelos de regras a serem seguidas.

-Gerenciabilidade: Várias formas de implementar e gerenciar recursos. Portal com pre definições ou linhas de comandos, API.

## Tipos de Serviços de Nuvem:
(Responsabilidade Compartilhada*)

IaaS (Infrastructure as a Service): Nível mais personalizável, com maior acesso aos detalhes e gerenciamento de hardware. (maior responsabilidade, mais flexível)

PaaS (Platform as a Service): Ignora a camada inicial de infraestrutura subjacente, focando em um ambiente para a criação, teste e implementação de app de software. Gerenciamento de plataforma de responsabilidade do provedor da nuvem.

SaaS (Software as a Service): O aplicativo já existe e a partir de camadas de acesso de pagamento (licenciamento) gerenciamos como ele será usado no ambiente de serviço. (menor responsabilidade)

##  Componentes de Arquitetura do Azure

-Regiões: Alta disponibilidade de regiões ao redor do globo, onde em cada região há uma comunicação entre DataCenters de alta eficiência (baixa latência) para manter o sistema operante caso algum deles dê problema. No caso de indisponibilidade completa da região podemos fazer uma Disaster Recovery acionando uma nova região (Região Par) para rodar os recursos, caso seja possível, até a restauração do serviço na região original. Existem regiões soberanas com acesso restrito, por exemplo pro governo/militar dos EUA e para a China, gerenciada pela empresa 21Vianet.

-Grupos de Recursos: Servem como um painel contendo os recursos nececssários para um projeto específico. Podemos migrar aos recursos, porém não podemos renomear o nome do grupo e não podem ser utilizados ao mesmo tempo em outros grupos de recursos. Podem estar em regiões diferentes.

## Assinaturas do Azure

Uma conta pode ter vários tipos de assinaturas, mas uma assinatura está associada somente a uma conta. Melhor organização para o pagamento da conta, referindo cada setor com sua respectiva assinatura, uma vez que é gerado boletos relacionadas a cada assinatura e também podemos dividir o permissionamento a cada setor utilizando grupos de gerenciamentos.

## Serviços de Computação do Azure

Serviço sob demanda que fornece recursos de computação, entre eles:

### Máquinas Virtuais (VMs): 
Emulações de software de computadores físicos. Inclui processador virtual, memória, armazenamento e rede. Entra no IaaS, permitindo personalização e exigindo maior responsabilidade. Podemos utilizar Conjuntos de dimensionamento de VMs para balancear a carga dimensionando os recursos automaticamente (Todas as VMs para a mesma finalidade).

Para termos um Conjunto de Disponibilidade de VMs devemos configurar elas de forma que existam no mínimo 3 Domínios de Falha (Hacks) com diferenteas Domínios de Atualização (DA), que são uma linha de VMs dispostas em DF diferentes, podendo então ocorrer manutenções em um layer de DA sem que o funcionamento do DF seja afetado.

### Área de Trabalho Virtual:
É uma virtualização de área de trabalho e aplicativo executada em nuvem.
Permite um gerenciamento mais centralizado. Podemos trabalhar com multiseção, com várias pessoas acessando a mesma área e utilizando um diretório específico, ou separar uma VM exclusiva

### Serviços de Contêiners
É um ambiente leve e virtualizado que não exige o gerenciamento do sistema operacional e pode responder a alterações sob demanda, podendo ser criado e destruído conforme a necessidade (Por exemplo o Docker).
Instâncias de Contêiner: oferta de PaaS que executa um contêiner ou pod de contêiners.
Aplicativos de Contêiner: oferta de PaaS, como instâncias de contêiners, que pode balancear a carga e escalar.
Serviço de Kubernetes (AKS): serviço de orquestração para contêiners com arquiteturas distribuidas e grandes volumes de contêiners.

### Azure Functions:
Modelo de execução baseadas em eventos, uma oferta PaaS. Uma programação pra realizar atividades conforme determinadas situações.

## Serviços de Aplicativo Azure:
Plataforma totalmente gerenciada para criar, implantar e dimensionar aplicativos Web e APIs rapidamente. Trabalha com .NET, .NET Core, Node.js, Java, Python ou Php. Oferta PaaS.

## Serviços de Rede do Azure:
-A Rede Virtual do Azure (VNet) permite que os recursos do Azure se comuniquem uns com os outros através de um subconjunto de redes, com a internet e com as redes locais. Se temos duas VNets elas nao se comunicam por padrão, temos que ter configurações específicas. Cuidado nas configurações de IPs para não causar Overlap em redes que se comunicam.

-Gateway de VPN: usado para enviar tráfego criptografado entre uma rede virtual do Azure e uma no local pela internet pública.

-Express Route: Comunicação direto via cabo (mais caro), do DataCenter ao cliente.

-DNS do Azure: Resolvedor de Nomes que respondem por um IP. Pode criar nomes de dominios privados e totalmente personalizados

## Microsoft Entra ID
Serviço de diretório que permite que façamos login tanto de aplicativos de nuvem ou de apps que desenvolvemos, gerenciando as identidades. Garante a autenticação, forneça um logon unico (SSO - Single Sign On) para usar vários serviços,

### Autenticação
Identifica a pessoa ou serviço buscando acesso a um recurso. Solicita credenciais de acesso legítimo. Base para criar princípios de identidade e controle de acesso de grupos.

### Autorização
Determina o nível de acesso de uma pessoa ou serviço autenticado. Define quais dados eles podem acessar e o que podem fazer com eles.

## Autenticação Multifator (MFA):
Fornece segurança adicional para as identidades, exigindo dois ou mais elementos para autenticação completa.
-Algo que vc sabe -> Algo que vc possui -> Algo que vc é.

## Autenticação B2B (Business to Business)
Deixar que usuários externos utilizem uma conta de parceiro para acessar diretórios e serviços internos.

## Autenticação B2C (Business to Customer)
Fornce acesso através de uma identidade externa a um usuário de parte dos serviços disponíveis.

## Acesso Condicional
-Associação de usuário ou grupo;
-Local do IP;
-Dispositivo;
-Aplicativo;
-Detecção de Risco;

## Controle de Acesso baseado em Função (RBAC)
-Gerenciamento de acesso de granularidade fina. Divida as tarefas dentro da equipe e conceda somente a quantidade de acesso que os usuários precisam para trabalhar. O gerenciamento é herdável, todas as permissões abaixo daquela concedida serão disponibilizadas automaticamente.

## Confiança Zero
Protege os ativos em qualquer lugar com uma política central. Sempre presumir que algo pode dar errado. Uma abordagem em camadas para proteger sistemas de computador. Forncer vários níveis de proteção, então ataques a uma camada são isolados das camadas subsequentes.

## Defender for Cloud
Serviço de monitoramento que fornece proteção contra ameaças nos Datacenters do Azure e locais. Fornece recomendações, detecta e bloqueia malware, analisa e identifica ataques potenciais e controla o acesso just-in-time para as portas.
