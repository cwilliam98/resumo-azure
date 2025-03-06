# AZ-204

## Implementar o Azure Key Vault

É um serviço de nuvem para armazenar e acessar segredos com segurança. Um segredo é tudo o que você deseja controlar firmemente o acesso, como chaves de API, senhas, certificados ou chaves criptográficas.
O Azure Key Vault dá suporte a dois tipos de contêineres: **cofres e pools de HSM(Módulo de segurança de hardware)**. Os cofres oferecem suporte ao armazenamento de chaves, segredos e certificados apoiados por software e HSM e os pools de HSm gerenciados oferecem suporte apenas a chaves apoiadas por HSM.

o Azure Key Vault ajuda a resolver os problemas a seguir:

- **Gerenciamento de segredos**: Pode ser usado para armazenar com segurança e controlar firmemente o acesso a tokens, senhas, certificados, chaves de API e outros segredos.
- **Gerenciamento de chaves**: Pode ser usados para criar e controlar as chaves de criptografia usadas para criptografar seus dados.
- **Gerenciamento de certificados**: Permite provisionar, gerenciar e implantar certificados de protocolo SSL/TLS públicos e provados para uso com o Azure e seus recursos internos conectados com facilidade.

O Azure Key Vault tem duas camadas de serviço: **Standard**, que faz a criptografia com uma chave de software, e uma camada **Premium**, que inclui chaves protegidas por HSM (módulo de segurança de hardware).

## Principais benefícios de usar o Azure Key Vault

- **Segredos centralizados do aplicativo**: O Azure Key Vault permite armazenar segredos do aplicativo de forma segura e centralizada, evitando que informações sensíveis, como cadeias de conexão, fiquem no código. Os aplicativos acessam os segredos por meio de URIs, garantindo segurança e controle sobre diferentes versões.

- **Armazene segredos e chaves com segurança**: O acesso ao Key Vault exige autenticação via Microsoft Entra ID e autorização por RBAC do Azure ou política de acesso do Key Vault. Ele pode ser protegido por software ou, na camada Premium, por hardware (HSMs), garantindo maior segurança para chaves e segredos.

- **Monitorar o acesso e o uso**: O Key Vault permite ativar logs para monitorar atividades e restringir o acesso a eles. Os registros podem ser armazenados em contas de armazenamento, transmitidos para hubs de eventos ou enviados para o Azure Monitor, facilitando auditoria e segurança.

- **Administração simplificada de segredos do aplicativo**: O Key Vault facilita a proteção e a disponibilidade de informações de segurança ao eliminar a necessidade de conhecimento sobre HSMs, escalar rapidamente, replicar dados entre regiões e fornecer ferramentas de administração via portal, CLI e PowerShell. Além disso, automatiza a renovação de certificados de autoridades certificadoras públicas.

## Práticas recomendadas do Azure Key Vault

- **Usar cofres de chaves separados**: É recomendado usar um cofre de chaves por aplicativo por ambiente (Desenvolvimento, Pré-Produção e Produção). Esse padrão ajuda você a não compartilhar segredos entre ambientes e também reduz a ameaça se houver uma violação.

- **Controlar o acesso ao cofre**: dados do Key Vault são confidenciais e comercialmente críticos, você precisa proteger o acesso aos cofres de chaves permitindo apenas aplicativos e usuários autorizados.

- **Backup**: Criar backups regulares do cofre na criação/atualização/exclusão de objetos em um cofre.

- **Logging**: Certifique-se de ativar o log e os alertas.

- **Opções de recuperação**: Ativar exclusão suave e proteção contra a purga se quiser se proteger contra a exclusão forçada do segredo.

### Autenticação

- **Identidades gerenciadas para recursos do Azure**: Ao implantar um aplicativo em uma máquina virtual no Azure, você pode atribuir uma identidade à sua máquina virtual que tenha acesso ao Key Vault. O benefício dessa abordagem é que o aplicativo ou serviço não está gerenciando a rotação do primeiro segredo. O Azure gira automáticamente. Essa é uma abordagem recomendada.

- **Entidade de Serviço e Certificado**: Você pode usar uma Entidade de Serviço e um certificado associado que tenha acesso ao Key Vault. Não recomendamos essa abordagem porque o proprietário do aplicativo ou desenvolvedor deve rotacionar o certificado.

- **Principal de serviço e segredo**: embora você possa usar um principal de serviço e um segredo para autenticar-se no Key Vault, não o recomendamos. É difícil girar automaticamente o segredo de inicialização usado para autenticar no Key Vault.

### Criptografia de dados em trânsito

O Azure Key Vault impõe o protocolo TLS (Transport Layer Security) para proteger os dados quando ele estiver viajando entre o Azure Key Vault e os clientes. Os clientes negociam uma conexão TLS com o Azure Key Vault.
O PFS (Perfect Forward Secrecy) protege as conexões entre os sistemas cliente dos clientes e os serviços de nuvem da Microsoft por chaves exclusivas. As conexões também usam comprimentos de chave de criptografia de 2.048 bits baseados em RSA.
