Os dados podem ser de qualquer tipo de **texto ou binário**. São três recursos para guardar e gerenciar os dados:

Account -> Container -> Blob

- Um Blob tem que estar dentro de um Container
- Um Container pode ter um número ilimitado de Blobs
- Uma Account pode ter um número ilimitado de Container

## Tipos de Blob

- **Block blobs:** é tratado como um conjunto de blocos. Cada bloco pode variar em tamanho, até 100 MB. Um blob de blocos pode conter até 50 mil blocos, fornecendo um tamanho máximo de mais de 4,7 TB. O bloco é a menor quantidade de dados que podem ser lidos ou gravados como uma unidade individual. São mais bem usados para armazenar objetos binários, grandes e discretos que são alterados com pouca frequência.

- **Page blobs:**  é organizado como uma coleção de páginas de tamanho fixo de 512 bytes. Otimizado para dar suporte a operações de leitura e gravação aleatórias; você pode buscar e armazenar dados para uma página, se necessário. Pode conter até 8 TB de dados. A Azure usa  para implementar o armazenamento em disco virtual para máquinas virtuais.

- **Append blobs**. é um block blob otimizado para dar suporte a operações de acréscimo. Você só pode adicionar blocos ao final; não há suporte à atualização ou à exclusão de blocos existentes. Cada bloco pode variar em tamanho, até 4 MB. O tamanho máximo de um blob é de mais de 195 GB.

## Container

O Container possui nível de acesso público configurável:

- **Private (privado):** não permite acesso anônimo.
- **Blob:** permite acesso anônimo somente leitura aos blobs.
- **Container:** permite acesso anônimo somente leitura aos blobs e a listar o container como um todo.

E também diferentes tiers (camadas):

- **Hot:** otimizado para leitura e escrita frequente. Menor custo de acesso porém maior custo de armazenamento.
- **Cool:** otimizado para armazenar grande quantidade de dados de acesso não frequente.
- **Archive:** otimizado para dados que podem tolerar horas de latência ao ser recuperado. Menor custo de armazenamento e maior custo de acesso.

O lifecycle dos blobs também podem ser configurados (por exemplo excluir depois de um certo tempo).

## Segurança

- **Criptografia**. Todos os dados gravados no Armazenamento do Azure são criptografados automaticamente.

- **Autenticação**. O Azure AD (Azure Active Directory) e o RBAC têm suporte em relação a operações de gerenciamento de recursos e operações de dados.

- **Dados em trânsito**. Os dados podem ser protegidos em trânsito, entre um aplicativo e o Azure usando a Criptografia do cliente, HTTPs ou SMB 3.0.

- **Criptografia de disco**. Os discos do sistema operacional e os discos de dados usados pelas Máquinas Virtuais do Azure podem ser criptografados usando o Azure Disk Encryption.

- **Assinaturas de acesso compartilhado**. O acesso pode ser permitido usando uma SAS (assinatura de acesso compartilhado). Ela pode ser restringida por tempo, IPs, protocolos e a nível de conta e serviço. Os parâmetros são enviados através da URI.

- **Autorização**. Todas as solicitações feitas em um recurso seguro no Armazenamento de Blobs, Arquivos do Azure, Armazenamento de Filas ou Azure Cosmos DB (Armazenamento de Tabelas do Azure) devem ser autorizadas.


