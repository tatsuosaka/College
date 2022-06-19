# Boas Práticas em Segurança da Informação

Coomprender o que são boas praticas e segurança da informação e importância de sua aplicação no cotidiano organizacional.

**Segurança da informação**: Um conjunto de medidas que visa a garantir a confidenciabalidade, a integridade e a disponibilidade das informações de uma organização ou de um usuario.

***

## **Módulo 1 - Reconhecer as boas praticas em segurança da informação referentes ao gerenciamento de senhas, treinamento e mecanismos de proteção**

**Gerenciamento de senhas**

As senhas devem conter pelo menos oito caracteres, ser alterada com frequencia, não utilizar apenas letras ou numeros, não conter nomes de usuario nem nome da empresa, não utilizar a mesma senha, nunca informar para terceiros;

**Treinamento**

A **ISO/IEC 27002 - Código de prática para a gestão de segurança da informação** essa norma tem o objetivo de dar suporte para a implantação, manutenção e a melhoria continua dos controles de segurança da informação, padronizando diretrizes e procedimentos para auxiliar sua gestão.

A norma **ISO 27002** possui 133 controles, dividimos em 11 seções:

1. **Politica da segurança da informação**: Prover orientação e apoio com as leis e regulamentações pertinentes
2. **Organizando a segurança da informação**: Estrutura de gerenciamento para iniciar e controlar a implementação da segurança da informação na organização
3. **Gestão de ativos**: Alcançar e manter a proteção adequada dos ativos da organização
4. **Segurança em recursos humanos**: Assegurar que os funcionarios entendam suas responsabilidades e estejam de acordo com seus papeis
5. **Segurança física e do ambiente**: Previnir acesso físico não autorizado, danos e interferencia com as instalações e informação da organização
6. **Gestão das operações e comunicações**: Garantir a operação segura e correta dos recursos e processamento da informação
7. **Controle de acesso**: Controlar o acesso da informação com base nos requisitos de negocio e segurança da informação
8. **Aquisição, desenvolvimento e manutenção de sistema da informação**: Garantir que a segurança seja parte integrante de sistema da informação
9. **Gestão de incidentes de segurança da informação**: Assegurar fragilidades e eventos da segurança da informação sejam comunicados permitindo a tomada de ação a tempo
10. **Gestão da continuidade do negócio**: Não permitir a interrupção das atividades e proteger os processos contra falhas ou desastres
11. **Conformidade**: Adequar os requisitos de segurança para não permitir a vioação de regulamentações ou leis estabelecidas

***

## **Módulo 2 - Identificar os recursos protegidos pelos sistemas de controle de acesso e os aspectos relacionados à política de vírus e ao gerenciamento de backups**

**Controles de acesso**: Uma maneira de limitar a abordagem a um sistema o controle de acesso é um modo pelo qual usuários recebem acesso e certos privilegios a sistemas, recursos ou informações.

***

**Existem três tipos de controle de acesso:**

- **Discretionary access control (DAC)**: O sistema responsabiliza o proprietário da empresa por decidir quais pessoas são permitidas em um local específico, físico ou digitalmente
- **Mandatory access control (MAC)**: Acrescenta rótulos ou categorias adicionais a todos objetos do sistema de arquivos. Usuarios e processos devem ter acesso apropriado a essas categorias antes de interagir com os objetos
- **Role-Base access control (RBAC)**: Concede acesso com bases em funções de negocios definidas e naão  na identidade do usuario

***

**Procedimento de logon eficiente deve:**

- Informar que o sistema só deve ser acessado por pessoas autorizadas
- Não apresentar informações sobre o sistema
- Não fornecer mensagens de ajuda
- Validar os dados de entrada após a conclusão do processo de logon
- Limitar a quantidade de tentativas
- Guardar as tentativas de acesso inválidos
- Forçar um tempo de espera antes de permitir novas tentativas
- Terminar as conexões 
- Limitar o tempo para o logon

***

**Politica contra vírus** 

- **Vírus de arquivo**: Infecta o sistema anexando-se ao final de um arquivo e altera o inicio do programa para controlar o inicio do codigo
- **Vírus de boot**: Executado durante a inicialização do sistema, infecta discos rigidos
- **Vírus de macro**: Acionado quando um programa executa macro
- **Codigo fonte vírus**: Modifica o codigo fonte para incluir vírus e ajudar a espalha-lo
- **Mutante**: Vírus programado para dificultar a detecção por anti-vírus
- **Polimorfico**: Similar ao mutante
- **Cavalo de troia (TROJAN)**: Programas inofencivos que trazem malwares
- **Vírus multipartite**: Infecta varias partes do sistema, inicialização, memoria e arquivos
- **Vírus stealth**: Altera o codigo usado para detectalo assim sua detecção se torna muito dificil
- **Vírus de encapsulamento**: Tenta ignorar a detecção pelo anti-vírus instalando-se na cadeia do maipulador de interações
- **Vírus criptografado**: O vírus se descriptografa e depois executa
- **Vírus blindado**: Codificado para dificultar a identificação e o entendimento do anti-vírus

**Orientações:**

1. Todos os computadores devem ter anti-vírus e executado em intervalos regulares
2. Computadores configurados para agendar atualizações regulares
3. Todos os arquivos devem ser verificados
4. Dispositivos de armazenamento verificados
5. Computadores e servidores não devem ser inicializados em dispositivos externos

**Sistema de backup**

- **Backup completo**: Faz copia de todos os dados
- **Backup incremental**: Grava somente arquivos alterados desde o ultimo backup
- **Backup diferencial**: É a copia dos dados criados e modificados desde o ultimo backup

## **Módulo 3 - Identificar os tipos de criptografia de dados e os itens presentes em um certificado digital**

***

**Criptografia**: Consiste no ato de codificar dados para que apenas pessoas autorizadas consigam ter acesso às informações 

- **Criptografia de chave simétrica**: Também conhecida por **criptografia de chave privada ou secreta**. O receptor da informação e o remetente usam uma única chave para criptografar e descriptografar a mensagem.

- **Criptografia de chave assimétrica**: Também denominada como **criptografia de chave pública**. Usando duas chaves, Uma chave privada é armazenada com cada pessoa e a chave pública é compartilhda na rede para que uma mensagem possa ser transmitida através de chaves públicas.

- **Função HASH**: Usa uma função matemática para criptografar irreversivelmente as informações, fornecendo uma impressão digital delas.

**Por que existem tantos tipos diferentes de criptografia? Por que não é possível fazer tudo o que é necessário com apenas um?**

Por que cada esquema é **otimizado para aplicações criptográficas específicas**

- **Você quer garantir a integridade dos dados?** Use as **funções de hash**
- **Você quer garantir a privacidade e confidencialidade?** Use a **criptografia de chave simétrica**
- **Você quer realizar a troca de chaves?** Use a **criptografia de chave assimétrica**

**Quais são as principais diferenças?**

|                                **Chave simétrica**                                	|                     **Chave assimétrica**                     	|                 **Função HASH**                 	|
|:---------------------------------------------------------------------------------:	|:-------------------------------------------------------------:	|:-----------------------------------------------:	|
|      Usa **chave única** para<br>criptografar/descriptografar<br> a mensagem      	|                    Usa um **par de chaves**                   	|           **Não requer nenhuma chave**          	|
|                 É **mais rápida**, porém é <br>**menos confiável**                	|          **Menos rápida** porém<br>**mais confiável**         	|   **Menos rápida** porém<br>**mais confiável**  	|
|                 Execta rapidamente<br>**processos criptográficos**                	| Introduzida para **superar<br> o problema a troca de chaves** 	| Introduzida para fornecer<br>**mais segurança** 	|
| Se a chave estiver comprometida<br>**haverá perda no remetente e<br>no receptor** 	|              Há **perda apenas do proprietário**              	|          Não há chave para comprometer          	|
|                                É **menos complexa**                               	|                      É **mais complexa**                      	|          Possui **média complexidade**          	|

***

**Certificado digital**

Um **documento eletrônico** que **identifica pessoas e instituições**, Também usados para assinar documentos digitalmente. Destinado a qualquer pessoa **física** ou **jurídica**, sendo emitido por uma **Autoridade Certificadora (AC)**. Com ele, pode-se anexar a chave pública (*Public Key Infrastructure/PKI*).

**Um certificado digital deve conter:**

- Nome do sujeito
- A chave publica do sujeito
- Um número de série
- Uma data de validade
- A assinatura digital da autoridade emissora
- Qualquer outra informação relevante

Tomou impulso a partir de 2001 quando o governo federal criou a _**Infraestrutura de Chaves Públicas Brasileiras (ICP-Brasil)**_

**Os certificados são utlizados em diversas aplicações como:**

- Automatização de prestação de informações fiscais á Receita Federal do Brasil
- Nota fiscal eletrônica
- Informatização do Poder Judiciário
- Informatização de serviços cartoriais
- Informatização de processo de abertura de empresas
- Informatização de prontuários médicos-odontológicos
- Compras governamentais por meio de pregão eletrônico