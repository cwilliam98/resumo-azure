# Resumo Azure

Resumo sobre a cloud da Azure para a certificação az-900

# Introdução

Existem três modelos de nuvem.

- Nuvem privada - ambiente onpremise
- Nuvem pública - entrega de serviços para os clientes por meio de um único provider
- Nuvem híbrida - É a junção das duas outras nuvens.

## Modelos de cobrança

Despesas de capital (CapEx) - ambientes físicos

- Gasto inicial de dinheiro em infraestrutura física.
- As despesas do CapEx têm um valor que se reduz com o tempo.

Despesas operacionais (OpEx)

- Gastar com produtos e serviços conforme necessário, pagamento conforme o uso.
- Seja cobrado imediatamente.

Baseado em consumo

- Usado pelos serviços em nuvem, os usuários pagam somente pelos recursos que usam.

## Benefícios da nuvem

- Alta disponibilidade - Se refere a quanto tempo o serviço irá ficar disponível por dia/mês/ano e caso não seja cumprido esse valor será incluído um crédito na sua conta por essa indisponibilidade.
- Escalibidade - Se refere à capacidade de ajustar recursos para atender à demanda, ou seja, pode adicionar mais recursos.
- Elasticidade - Se refere a expansão dos recursos implantados ao receber um salto repentino e acentuado na demanda, ou se houver uma queda significativa na demandas os recursos serão reduzidos.
  - Por exemplo: adicionar máquinas virtuais ou contêineres.
- Confiabilidade - Se refere a possuir um design descentralizado, ou seja, posso ter recursos implantados em várias regiões do mundo. Dessa forma mesmo que ocorra um evento catastrófico em uma determinada região, outras regiões permaneceram operando.
- Previsibilidade - Se refere a confiança na nuvem, seja por desempenho ou no custo.
- Segurança - A microsoft dispoem de vários recursos de segurança, mas cabe ao administrador da nuvem implantar e gerenciar esses recursos conforme a necessidade.
- Governança - (Auditoria) Auxilia a sinalizar qualquer recurso que esteja fora de conformidade com seus padrões corporativos e fornece estratégias de solução. - Por exemplo: patches de software e atualizações podem ser aplicados automaticamente.
- Gerenciabilidade - Se refere a ter várias formas de gerenciar recursos na azure, navegador, linha de comando, APIs, e etc.

## Tipos de Serviços de Nuvem

### IaaS - Infraestrutura como serviço

São exemplos de infraestrutura comom serviço, servidores e armazenamento, firewalls, planta física. Temos mais acesso no contexto de personalização desse recurso.

- É mais flexível

### PaaS - Plataforma como serviço

São exemplos de Plataforma como serviço, Sistemas operacionais, ferramentas para desenvolvedores, analise de negócios de gerenciamento de database. Fornece um ambiente para a criação, o teste e a implantação de aplicativos de software, sem focar no gerenciamento da infraestrutura subjacente.

- Focado no desenvolvimento de aplicativos.

### SaaS - Software como serviço

São exemplos de Software como serviço, aplicativos/apps hospedados. Os usuários se conectam e usam aplicativos com base em nuvem pela internet, por exemplo, Microsoft Office 365, email, calendários.

- Modelo de preço de pagamento conforme o uso, modelo de assinatura.

Visão geral de cada tipo de serviço:

![image](https://github.com/user-attachments/assets/53432929-2775-4347-a5b3-8725e9399bb5)

## Modelo de responsabilidade compartilhada

![image](https://github.com/user-attachments/assets/6e23b83b-e837-499d-ac99-d3a8be51c2d5)

## Infraestrutura

A infraestrutura física da Azure são iguais aos grandes datacenters corporativos, instalações com recursos organizados em racks com energia, refrigeração e infraestrutura de rede dedicadas.
A Azure possui datacenters em todo o mundo, no entanto esses datacenters individuais não são acessíveis diretamente. Eles são agrupados em Regiões do Azure ou em Zonas de Disponibilidade do Azure projetadas para ajudá-lo a obter resiliência e confiabilidade para suas cargas de trabalho críticas para os negócios.

### Regiões

Uma região é uma área geográfica do planeta que contém pelo menos um data center e está conectado a uma rede de baixa latência.

- As regiões são compostas por um ou mais datacenters muito próximos
- Fornecem flexibilidade e escala para reduzir a latência do cliente
- As regiões preservam a residência dos dados com uma oferta abrangente de conformidade. No entanto, nem todas as Regiões do Azure atualmente dão suporte a zonas de disponibilidade.

### Zonas de disponibilidade

São os datacenters separados fisicamente e ficam dentro das regiôes.

- Fornece proteção contra tempo de inatividade devido a falha no datacenter.
- Para garantir resiliência, no mínimo três zonas de disponibilidade separadas estão presentes em todas as regiões habilitadas.
- Permitem executar aplicativos críticos com alta disponibilidade.
- Recursos de computação, armazenamento, rede e dados podem ser replicados entre zonas.
- Pode haver custos adicionais para duplicação de serviços e transferência de dados.
- **Serviços em zonas:** Recurso fixado a uma zona específica (Ex.: VMs, discos gerenciados, IPs).
- **Serviços com redundância de zona:** Replicação automática entre zonas (Ex.: Armazenamento com redundância de zona, Banco de Dados SQL).
- **Serviços não regionais:** Sempre disponíveis em múltiplas geografias do Azure, resistentes a falhas de zona e região.

  ![image](https://github.com/user-attachments/assets/b884b094-b585-41aa-9d22-4e021fcd6335)
  Fonte: Microsoft

### Pares de Regiões

Existe uma região par para cada região original, possui replicação automática para alguns serviços.

- Ficam localizadas a pelo menos 300 milhas ou 480km de distância uma da outra.
- Isso reduz a probabilidade de interrupções devido a desastres naturais, conflitos civis, quedas de energia ou interrupções de rede física.

![image](https://github.com/user-attachments/assets/9a108c33-635e-4895-97bd-00b76bff098e)

### Regiões Soberanas

Hoje existem duas regiões soberanas, a do exército dos EUA e a da China, ambas são somente acessíveis para esse EUA e China respectivamente.

- US DoD Central, US Gov – Virgínia, US Gov Iowa, entre outros: essas regiões são instâncias lógicas e físicas do Azure isoladas da rede, destinadas a parceiros e órgãos do governo dos EUA. Esses datacenters são operados por cidadãos selecionados dos EUA e incluem certificações de conformidade adicionais.
- Leste da China, Norte da China, entre outros: essas regiões estão disponíveis por meio de uma parceria exclusiva entre a Microsoft e a 21Vianet, segundo a qual a Microsoft não mantém diretamente os data centers.

## Grupos de recursos

São locais onde ficam organizados os recursos que são criados, são para manter a organização dessa forma ficam mais fáceis de serem encontrados.

- Os recursos podem existir em apenas um grupo de recursos.
- Podem existir em diferentes regiões.
- Os aplicativos pode utilizar vários grupos de recursos.
- Quando você aplicar uma ação a um grupo de recursos, ela será aplicada a todos os recursos dentro do grupo.
- Se excluir um grupo de recursos, todos os recursos serão excluidos.
- Se você conceder ou negar acesso a um grupo de recursos, vai conceder ou negar acesso a todos os recursos dentro do grupo de recursos.

## Assinaturas do Azure

São uma unidade de gerenciamento, cobrança e escala. São um modo de organizar logicamente os recursos, as assinaturas permitem organizar logicamente seus grupos de recursos e facilitar a cobrança.
![image](https://github.com/user-attachments/assets/2546a9d0-7849-42b4-b36c-709add1e2d8d)

- Uma conta pode ter várias assinaturas, mas uma assinatura está associada a apenas uma conta.
- Cada grupo de trabalho pode ter a sua assinatura, dessa forma fica mais fácil separar os custos.

As assinaturas do Azure podem ser usadas para definir limites em relação a produtos, serviços e recursos do Azure. Existem dois tipos de limites de assinatura.

**Limite de cobrança:** Esse tipo de assinatura determina como uma conta do Azure é cobrada pelo uso do Azure. Você pode criar várias assinaturas para atender a diferentes tipos de requisitos de cobrança. O Azure gera relatórios de cobrança e faturas separados para cada assinatura, para que você possa organizar e gerenciar os custos.
**Limite de controle de acesso:** O Azure aplica políticas de gerenciamento de acesso no nível da assinatura, e você pode criar assinaturas separadas para refletir diferentes estruturas organizacionais. Um exemplo disso é que, em um negócio, você tem diferentes departamentos aos quais aplica políticas de assinatura do Azure distintas. Esse modelo de cobrança permite gerenciar e controlar o acesso aos recursos que os usuários provisionam com assinaturas específicas.

## Grupos de gerenciamento

Os grupos de gerenciamento do Azure fornecem um nível de escopo acima das assinaturas. Você organiza as assinaturas em contêineres chamados grupos de gerenciamento e aplica as condições de governança a esses grupos.

- Podem incluir várias assinaturas do Azure
- As assinaturas herdam as condições aplicadas ao grupo de gerenciamento

      ![image](https://github.com/user-attachments/assets/2556ff2b-8de8-455d-8bcf-b37df4f526ba)
      Fonte: Microsoft

  Fatos importantes sobre os grupos de gerenciamento:

- 10.000 grupos de gerenciamento podem ter suporte em um único diretório.
- Uma árvore do grupo de gerenciamento pode dar suporte a até seis níveis de profundidade. Esse limite não inclui o nível raiz nem o nível da assinatura.
- Cada grupo de gerenciamento e assinatura podem dar suporte a somente um pai.

## Serviços de computação do Azure

A Computação do Azure é um serviço sob demanda que fornece recursos de computação, como discos, processadores, memória, rede e sistemas operacionais.

### Máquinas virtuais do Azure

- As máquinas virtuais do Azure são emulações de software de computadores físicos. As VMs fornecem IaaS (infraestrutura como serviço) na forma de um servidor virtualizado e podem ser usadas de várias maneiras.
  As VMs são uma opção ideal quando você precisa de:

- Controle total sobre o SO (sistema operacional).
- Capacidade para executar um software personalizado.
- Usar configurações personalizadas de hospedagem.

O Azure também pode gerenciar o agrupamento de VMs para você com recursos como conjuntos de dimensionamento e conjuntos de disponibilidade.

### Conjuntos de disponibilidade de VM

São usados para mitigar problemas de indisponibilidade das máquinas, geralmente são separados em 3 domínios de falha onde são replicadas as máquinas.

#### Conjuntos de escala de máquina virtual

Permitem criar e gerenciar um grupo de VMs idênticas e com balanceamento de carga. Os conjuntos de dimensionamento permitem que você gerencie, configure e atualize centralmente um grande número de VMs em minutos.

#### Conjuntos de disponibilidade da máquina virtual

Os conjuntos de disponibilidade de máquinas virtuais são outra ferramenta para ajudá-lo a criar um ambiente mais resiliente e altamente disponível.
A disponibilidade atinge esses objetivos agrupando VMs de duas maneiras: atualizar domínio e domínio de falha.

**Domínio de atualização:** as VMs de grupos de domínio de atualização que podem ser reinicializadas ao mesmo tempo. Essa configuração permite aplicar atualizações sabendo que apenas um agrupamento de domínio de atualização está offline por vez.
**Domínio de falha:** o domínio de falha agrupa suas VMs por origem de energia comum e comutador de rede. Por padrão, um conjunto de disponibilidade divide suas VMs em até três domínios de falha.

### Área de trabalho virtual do azure

É uma virtualização de área de trabalho e aplicativo executada na nuvem.

- Reduz o risco de que o recurso seja deixado para trás.
- Implantações reais de várias sessões.

### Serviços de contêineres do Azure

Fornecem um ambiente leve e virtualizado que não exige o gerenciamento dos sistema operacional e pode responder a alteraçoes sob demanda.

- Ambiente de virtualização leve e ágil.
- Permitem rodar múltiplas instâncias de aplicativos em um único host físico ou virtual.
- Diferente das VMs, não exigem gerenciamento do sistema operacional.
- Rápidos para iniciar, escalar e reiniciar após falhas.
- Docker é um dos mecanismos de contêiner mais populares, e o Azure oferece suporte a ele.

#### Soluções de Contêiner no Azure

- Instâncias de Contêiner do Azure (ACI)
  - PaaS que permite executar contêineres rapidamente, sem gerenciar VMs.
- Aplicativos de Contêiner do Azure
  - Similar ao ACI, mas inclui balanceamento de carga e escalabilidade automática.
- Serviço de Kubernetes do Azure (AKS)
  - Orquestração de contêineres para gerenciar frotas de contêineres de forma eficiente.

### Azure Functions

O Código baseado em eventos é executado quando chamado, sem exigir uma infraestrutura de servidor durante períodos inativos.

Principais Benefícios:

- Escalabilidade automática conforme a demanda.
- Cobrança baseada no uso (somente pelo tempo de CPU consumido).
- Execução sob demanda e desalocação automática de recursos.

Tipos de Funções:

- Sem estado (Stateless): Reiniciadas a cada execução.
- Com estado (Durable Functions): Mantêm o contexto entre execuções.

Flexibilidade e Uso:

- Parte essencial da arquitetura serverless.
- Suporta execução de qualquer tipo de código.
- Pode ser migrado para um ambiente tradicional (com servidor) caso necessário.

### Serviços de rede do Azure

- Permite que os recursos do Azure se comuniquem uns com os outros, com a Internet e com as rede locais.
- Pontos de extremidade públicos ou privados.
  As redes virtuais do Azure oferecem as seguintes funcionalidades de rede essenciais:

- Isolamento e segmentação
- Comunicação pela Internet
- Comunicação entre recursos do Azure
- Comunicação com os recursos locais
- Rotear tráfego de rede
- Filtrar tráfego de rede
- Conectar redes virtuais

#### Gateway de VPN

É usado para enviar tráfego criptografado entre uma rede virtual do Azure e uma no local pela internet pública e permitem a seguinte conectividade:

- Conecte datacenters locais a redes virtuais por meio de uma conexão site a site.
- Conecte dispositivos individuais a redes virtuais por meio de uma conexão ponto a site.
- Conecte redes virtuais a outras redes virtuais por meio de uma conexão rede a rede.

É possível implantar apenas un gateway de VPN em cada rede virtual, mas você pode usar um gateway para se conectar a vários locais, incluindo outras redes virtuais ou datacenters locais.

- Gateways de VPN baseados em política especificam estaticamente o endereço IP dos pacotes que devem ser criptografados por meio de cada túnel.
- Em gateways baseados em rota, os túneis IPSec são modelados como um adaptador de rede ou uma interface de túnel virtual.

Use um gateway de VPN baseado em rota se precisar de qualquer um dos seguintes tipos de conectividade:

- Conexões entre redes virtuais
- Conexões ponto a site
- Conexões multissite
- Coexistência com um gateway do Azure ExpressRoute

### Azure ExpressRoute

O Azure ExpressRoute permite que você estenda suas redes locais para a nuvem da Microsoft em uma conexão privada com a ajuda de um provedor de conectividade.

Há vários benefícios de usar o ExpressRoute como o serviço de conexão entre o Azure e as redes locais.

- Conectividade com os serviços de nuvem da Microsoft em todas as regiões da região geopolítica.
- Conectividade global com os serviços da Microsoft em todas as regiões com o Alcance Global do ExpressRoute.
- Roteamento dinâmico entre sua rede e a Microsoft por meio do BGP (Border Gateway Protocol).
- Redundância interna em cada local de emparelhamento para proporcionar maior confiabilidade.

### DNS do Azure

- Confiabilidade e desempenho aproveitando uma rede global de servidores de nome DNS usando a rede Anycast.
  O DNS do Azure usa o escopo e a escala do Microsoft Azure para proporcionar inúmeros benefícios, incluindo:

- Confiabilidade e desempenho
- Segurança
- Facilidade de uso
- Personalizar redes virtuais
- Registros de alias

## Identidade, Acesso e Segurança

### Microsoft Entra ID

É o serviço de gerenciamento de identidades e acesso baseado em nuvem do Microsoft Azure

- Autenticação (os funcionários entram para acessar os recursos).​
- Logon único (SSO)​
- Gerenciamento de aplicativos.​
- Negócios para Negócios (B2B).​
- Gerenciamento de dispositivos.​

### Microsoft Entra Domain Services

- Obtenha os benefícios dos serviços de domínio baseados em nuvem sem gerenciar os controladores de domínio.​
- Execute aplicativos herdados (que não podem utilizar os padrões de autenticação modernos) na nuvem.​
- Sincronizar automaticamente a partir do Microsoft Entra ID.​

### Acesso Condicional​

É uma ferramenta usada para permitir ou bloquear o acesso com base e alguns itens, por exemplo:

- Associação de usuário ou grupo​
- Local do IP​
- Dispositivo​
- Aplicativo​
- Detecção de risco​

### Confiança zero

Parte do princípio que toda camada de segurança pode ter alguma falha e por isso sempre é indicado incluir várias formas de validações e segurança.
