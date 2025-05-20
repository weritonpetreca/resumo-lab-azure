# Resumo do Lab Azure
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab sobre azure na DIO.

##Tipos de modelos de Nuvem:
-Privadas: 
-Públicas:
-Híbridas:
-Multicloud*:

##Gastos financeiros:
-CaPex: Dispêndio com estruturas físicas;
-OpEx: Gastos operacionais de recursos utilizados;

PAYG - Pay as You Go: Pague somente por aquilo que utilizar;

Previsibilidade de custos através de relatórios, calculadoras e escolha de recursos sendo utilizados;

##Benefícios da Nuvem:
-Alta disponibilidade: Maior tempo possivel do serviço ativo -> 99% / 99,9% / 99,95% /99,99%. Por contrato existe um tempo que pode ficar fora por semana/mês. Passando disso é garantido créditos para serem utilizados pelo contratante em outros serviços. SLA (Service Level Agreement)

-Escalabilidade: Ajustar a capacidade do recurso para se ajustar à demanda quando detectado a necessidade.

-Elasticidade: Poder dimensionar o ambiente através de requisições. Ajustar conforme a quantidade de uso, tanto aumentar quanto diminuir.

-Confiabilidade (Resiliência): Design descentralizado para implementações em várias regiões do mundo. Caso uma região passe por instabilidade outra poderá ser acionada.

-Previsibilidade (Confiança): Well-Architected Framework;

-Segurança: Oferece ferramentas, a implementação é responsabilidade pelo cliente.

-Governança (Auditoria): Padrões de gestão corporativa, regulamentação. Modelos de regras a serem seguidas.

-Gerenciabilidade: Várias formas de implementar e gerenciar recursos. Portal com pre definições ou linhas de comandos, API.

##Tipos de Serviços de Nuvem:
(Responsabilidade Compartilhada*)

IaaS (Infrastructure as a Service): Nível mais personalizável, com maior acesso aos detalhes e gerenciamento de hardware. (maior responsabilidade, mais flexível)

PaaS (Platform as a Service): Ignora a camada inicial de infraestrutura subjacente, focando em um ambiente para a criação, teste e implementação de app de software. Gerenciamento de plataforma de responsabilidade do provedor da nuvem.

SaaS (Software as a Service): O aplicativo já existe e a partir de camadas de acesso de pagamento (licenciamento) gerenciamos como ele será usado no ambiente de serviço. (menor responsabilidade)

##Componentes de Arquitetura do Azure

-Regiões: Alta disponibilidade de regiões ao redor do globo, onde em cada região há uma comunicação entre DataCenters de alta eficiência (baixa latência) para manter o sistema operante caso algum deles dê problema. No caso de indisponibilidade completa da região podemos fazer uma Disaster Recovery acionando uma nova região (Região Par) para rodar os recursos, caso seja possível, até a restauração do serviço na região original. Existem regiões soberanas com acesso restrito, por exemplo pro governo/militar dos EUA e para a China, gerenciada pela empresa 21Vianet.

-Grupos de Recursos: Servem como um painel contendo os recursos nececssários para um projeto específico. Podemos migrar aos recursos, porém não podemos renomear o nome do grupo e não podem ser utilizados ao mesmo tempo em outros grupos de recursos. Podem estar em regiões diferentes.

##Assinaturas do Azure

Uma conta pode ter vários tipos de assinaturas, mas uma assinatura está associada somente a uma conta. Melhor organização para o pagamento da conta, referindo cada setor com sua respectiva assinatura, uma vez que é gerado boletos relacionadas a cada assinatura e também podemos dividir o permissionamento a cada setor utilizando grupos de gerenciamentos.
