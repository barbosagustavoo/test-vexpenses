# test-vexpenses
Tarefas a Serem Realizadas
1. Análise Técnica do Código Terraform
○ Leitura do Arquivo: Estude o conteúdo do arquivo main.tf fornecido.
Descrição técnica sobre o codigo terraform "main.tf":
Resposta: Inicialmente ele carrega os providers da aws, e em seguida ele cria uma instancia com uma imagem debian, associa um ip publico a ela, cria uma chave, define um nome na instancia e adiciona ao security group e a uma vpc. em seguida é criado um internet gateway, que é um componente que permite a conexão entre a internet e as instâncias de uma vpc, é um roteador virtual. Em seguida cria um par de chaves para conexões externas via ssh. Depois é criado uma tabela de rotas e logo em seguida é feita a associação da tabela de rotas para a subnet. Logo após é criado um security group com permissão de saída que permite a saida de qualquer tráfego e de entrada que permite ssh de qualquer lugar, esse security group é vinculado a vpc tambem. No próximo passo uma subnet é criada, definindo a zona de disponibilidade o bloco cidr somente com o protocolo ipv4. Depois cria a vpc principal passando o bloco cidr tambem de protocolo ipv4 e vinculando tabela de roteamento e security group. E por ultimo cria uma chave tls rsa que fica junto com a chave ec2. E ao final de tudo o terraform no exibe o ip publico da instancia e a chave privada para acessar a instancia

2. Modificação e Melhoria do Código Terraform
○ Aplicação de melhorias de segurança: Realize alterações no código
fornecido de modo a implementar medidas que aumentem a segurança do
ambiente criado.
Resposta: Conforme estou estudando sobre System manager acredito que neste quesito eu optaria pela implementação do acesso as instancias somente pelo session manager que é uma ferramenta da aws que gerencia maquinas locais e instancias ec2 através do aws cli ao invés de liberar o tráfego para todas as conexões ssh. E tambem configuraria para ter acesso somente depois de uma autenticação MFA. Acredito que dessa forma ficaria mais seguro. Mas isso é feito na console da aws dentro do IAM.

○ Automação da Instalação do Nginx: Configure a instância EC2 para
instalar e iniciar o servidor Nginx automaticamente após a criação da
instância.
○ Descrição Técnica: Redija uma descrição detalhada e técnica do que a sua
alteração faz e os resultados esperados.
Resposta: No codigo eu inseri dentro da criação da instancia um bloco de codigo aonde ele atuliza os repositorios do sistema operacional, e instala e ativa o serviço de servidor web Nginx.

○ Outras Melhorias: Sinta-se à vontade para implementar outras melhorias de
código que considerar pertinentes, e não esqueça de descrevê-las
adequadamente.
Resposta: O tempo de 48h foi curto para fazer o que eu gostaria, na minha visao colocaria o terraform pra trabalhar juntamente com ansible para gerenciar as instancias e instalar os softwares necessarios com mais facilidade. Pois como estou estudando ansible tambem, ja vi que essa combinação funciona na automação e facilita o serviço.
