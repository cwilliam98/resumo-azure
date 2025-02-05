# Resumo Azure
Resumo sobre a cloud da Azure

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
- Governança - (Auditoria) Auxilia a sinalizar qualquer recurso que esteja fora de conformidade com seus padrões corporativos e fornece estratégias de solução.
      - Por exemplo: patches de software e atualizações podem ser aplicados automaticamente.
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

## Regiões
- As regiões são compostas por um ou mais datacenters muito próximos
- Fornecem flexibilidade e escala para reduzir a latência do cliente
- As regiões preservam a residência dos dados com uma oferta abrangente de conformidade

## Zonas de disponibilidade
São os datacenters e ficam dentro das regiôes.
- Fornece proteção contra tempo de inatividade devido a falha no datacenter.

## Pares de Regiões

Existe uma região par para cada região original, possui replicação automática para alguns serviços.

![image](https://github.com/user-attachments/assets/9a108c33-635e-4895-97bd-00b76bff098e)

## Regiões Soberanas
Hoje existem duas regiões soberanas, a do exército dos EUA e a da China, ambas são somente acessíveis para esse EUA e China respectivamente.

## Grupos de recursos
São locais onde ficam organizados os recursos que são criados, são para manter a organização dessa forma ficam mais fáceis de serem encontrados. 
- Os recursos podem existir em apenas um grupo de recursos.
- Podem existir em diferentes regiões.
- Os aplicativos pode utilizar vários grupos de recursos.

## Assinaturas do Azure
![image](https://github.com/user-attachments/assets/2546a9d0-7849-42b4-b36c-709add1e2d8d)

Uma conta pode ter várias assinaturas, mas uma assinatura está associada a apenas uma conta.
Cada grupo de trabalho pode ter a sua assinatura, dessa forma fica mais fácil separar os custos.

## Grupos de gerenciamento
- Podem incluir várias assinaturas do Azure
- As assinaturas herdam as condições aplicadas ao grupo de gerenciamento

## Serviços de computação do Azure
A Computação do Azure é um serviço sob demanda que fornece recursos de computação, como discos, processadores, memória, rede e sistemas operacionais.

### Máquinas virtuais do Azure
- As máquinas virtuais do Azure são emulações de software de computadores físicos.

### Conjuntos de disponibilidade de VM
São usados para mitigar problemas de indisponibilidade das máquinas, geralmente são separados em 3 domínios de falha onde são replicadas as máquinas.

### Área de trabalho virtual do azure
É uma virtualização de área de trabalho e aplicativo executada na nuvem.
- Reduz o risco de que o recurso seja deixado para trás.
- Implantações reais de várias sessões.

### Serviços de contêineres do Azure
Fornecem um ambiente leve e virtualizado que não exige o gerenciamento dos sistema operacional e pode responder a alteraçoes sob demanda.

### Azure Functions
O Código baseado em eventos é executado quando chamado, sem exigir uma infraestrutura de servidor durante períodos inativos.

### Serviços de rede do Azure
- Permite que os recursos do Azure se comuniquem uns com os outros, com a Internet e com as rede locais.
- Pontos de extremidade públicos ou privados.
#### Gateway de VPN
- é usado para enviar tráfego criptografado entre uma rede virtual do Azure e uma no local pela internet pública.

### DNS do Azure
- Confiabilidade e desempenho aproveitando uma rede global de servidores de nome DNS usando a rede Anycast.

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


