# Camadas de Aplicação e Transporte

Compreender a influência de uma arquitetura no desenvolvimento de aplicações para redes de computadores, bem como os impactos dos diferentes serviços oferecidos pela camada de transporte no funcionamento delas.

***

## **Módulo 1 - Reconhecer as arquiteturas de aplicações**

O software de aplicação, também conhecido como software aplicativo, é nossa interface com o sistema (e, por consequência, com toda a rede de comunicação que suporta essa operação). Portanto, sempre que houver um serviço na rede.

**Arquiteturas de aplicações**

**Cliente-servidor**

Nesta arquitetura, há pelo menos duas entidades: um cliente e um servidor. O servidor executa operações continuamente aguardando por requisições do cliente.

**Quando chega uma solicitação, o servidor pode:**

- Atender imediatamente caso esteja ocioso;
- Gerar um processo-filho para o atendimento da solicitação;
- Enfileirar a solicitação para ser atendida mais tarde;
- Criar uma thread para esse atendimento.

**Quem utiliza este tipo de arquitetura é a aplicação web.**

O servidor web fica aguardando conexões dos clientes, quando você clica no link, seu browser envia uma mensagem ao servidor ele faz o processamento e devolve ao browser o resultado.

Mas esse processo nem sempre é simples. Afinal, a aplicação que executa no servidor web pode precisar de uma informação de um banco de dados externo. para obtê-la o servidor deve enviar uma solicitação ao servidor do banco de dados solicitando o que necessita. Neste caso ele atua como cliente do servidor de banco de dados.

**Peer-to-peer**

Quase todos os participantes (senão todos) são provenientes de usuários comuns executando seus programas em desktops e notebooks.

O **BITorrent** por exemplo, um sistema que seus usuários compartilhem sem haver necessidade de eles estarem armazenados em um servidor.

***

## **Módulo 2 - Identificar os principais serviços oferecidos pela camada de aplicação**

**Protocolos da camada de aplicação**

Um protocolo de camada de aplicação define como processos de uma aplicação, que funcionam em sistemas finais diferentes, passam mensagens entre si. Em particular, um protocolo de camada de aplicação define:

- Os tipos de mensagens trocadas, por exemplo, de requisição e de resposta.
- A sintaxe dos vários tipos de mensagens, tais como os campos da mensagem e como os campos são delineados.
- A semântica dos campos, isto é, o significado da informação nos campos.
- Regras para determinar quando e como um processo envia e responde mensagens.

**HTTP (Serviço web)**

Para solicitar uma pagina web utilizando o protocolo HTTP o browser estabelece uma conexão TCP com o servidor web e lhe envia a seguinte solicitação: 

![http](/Fundamentos%20de%20Redes%20de%20Computadores/Tema%203%20-%20Camadas%20de%20Aplica%C3%A7%C3%A3o%20e%20Transporte/img/http.png)

**Correio eletrônico (E-Mail)**

Protocolos SMTP, POP3 e IMAP

- **SMTP**: O protocolo responsavel pela transferência da mensagem até seu destino, definido pelo RFC 5321.
- **POP3**: Tem a finalidade de fazer o download das mensagens que encontram no mailbox do usuário para o sistema local.
- **IMAP**: Consegue permitir sua leitura diretamente no servidor dispensando a transferencia para o sistema local.

**DNS**

A comunicação entre hospedeiros na internet ocorre por meio de endereços binários de rede. Afinal, para se comunicar com um destino, o hospedeiro precisa conhecer seu endereço.

Entretanto, é bem mais fácil trabalhar com nomes de hospedeiros do que com seus endereços de rede. Além de ser muito difícil conhecer todos os endereços dos hospedeiros com os quais precisamos trabalhar, precisaríamos ser notificados toda vez que algum deles mudasse de endereço.

Para resolver esse problema, foi desenvolvido o domain name system (DNS). Sua finalidade é a criação de um sistema de nomes de forma hierárquica e baseada em domínios. Para acessar um hospedeiro, portanto, basta conhecer seu nome de domínio e fazer uma consulta ao servidor DNS, que é responsável por descobrir seu endereço.

Além do **mapeamento de nomes de hospedeiros em endereços IP**, o DNS ainda provê:

- Identificação de servidores de correios eletrônicos.
- Apelidos para hospedeiros.
- Distribuição de carga.
- Descoberta de nomes de hospedeiros (mapeamento reverso).

***

## **Módulo 3 - Localizar os elementos da camada de transporte**

As aplicações precisam de um modelo de rede no qual haja a entrega de uma mensagem (ou um fluxo de dados) tanto em um ponto de rede quanto em sua aplicação par no hospedeiro destino.

O objetivo da camada de transporte é, independentemente das redes físicas em uso, promover a confiabilidade na transferência de dados entre os hospedeiros origem e destino.

**Endereçamento**

Quando seu programa solicita algo a um servidor, o sistema envia uma mensagem para ser entregue à aplicação que executa em um hospedeiro remoto. Mas podem existir várias aplicações nele.

**Multiplexação e demultiplexação**

Fornecem um serviço de entrega processo a processo para aplicações executadas nos hospedeiros.

No hospedeiro destino, a camada de transporte recebe segmentos de dados da camada de rede, tendo a responsabilidade de entregá-los ao processo de aplicação correto.

Um processo pode ter um ou mais endereços de transporte (conhecidos como portas na arquitetura TCP/IP) pelos quais dados passam da rede para o processo – e vice-versa.

Desse modo, a camada de transporte do hospedeiro destino os entrega diretamente a uma porta.

**Como o hospedeiro destino direciona à porta correta um segmento que chega?**

Para essa finalidade, cada segmento da camada de transporte tem um conjunto de campos de endereçamento no cabeçalho. No receptor, a camada de transporte examina esses campos para identificar a porta receptora e direcionar o segmento a ela. A tarefa de entregar os dados contidos em um segmento para a porta correta é denominada demultiplexação.

Já a **multiplexação** consiste no trabalho de, no hospedeiro origem:

- Reunir porções de dados provenientes de diferentes portas
- Encapsular cada porção de dados com as informações de cabeçalho (as quais, mais tarde, serão usadas na demultiplexação) para criar segmentos
- Passar os segmentos para a camada de rede.

**Como o TCP sabe quem é quem?**

Para fazer uso dele, um processo deve se registrar em uma porta (endereço de transporte) do protocolo TCP. Servidores possuem portas conhecidas, mas programas clientes se registram nas aleatórias.

Vamos supor que os programas de Eduardo se registraram nas seguintes portas:

- Browser web = 11278
- Cliente de e-mail = 25786
- Transferência de arquivos = 3709

- **Multiplexação**: Ao receber mensagens das aplicações para envio, o protocolo de transporte as identifica por seus respectivos números de porta, permitindo, assim, que várias aplicações possam utilizá-los ao mesmo tempo.
- **Demultiplexação**: Quando recebe as mensagens do hospedeiro remoto para entregá-las em cada aplicação, o protocolo de transporte verifica o número da porta destino que a mensagem carrega e a entrega para o processo registrado nela.

## **Módulo 4 - Comparar os serviços oferecidos pela camada de transporte**

**Protocolos de transporte da internet**

**UDP**

O protocolo de transporte mais simples que poderia existir seria aquele que, no envio, se limitasse a receber mensagens da camada de aplicação e as entregasse diretamente na de rede. Na recepção, ele, por outro lado, receberia os pacotes da camada de rede e os entregaria na de aplicação. Este tipo de protocolo, em suma, não efetua nenhum trabalho para garantir a entrega das mensagens. Felizmente, o UDP não se limita a isso.

Um processo pode ter um ou mais endereços de transporte (conhecidos como portas na arquitetura TCP/IP) pelos quais dados passam da rede para o processo.

![CabecalhoUDP](/Fundamentos%20de%20Redes%20de%20Computadores/Tema%203%20-%20Camadas%20de%20Aplica%C3%A7%C3%A3o%20e%20Transporte/img/cabecalhoudp.png)

Os campos **porta origem e porta destino** têm a função de identificar os processos nas máquinas origem e destino. Quando uma aplicação A deseja enviar dados para uma B, o UDP coloca o número da porta da aplicação origem (A) no campo “porta origem” e o de porta da aplicação (B) em “porta destino”.

O campo **tamanho** especifica o tamanho do segmento, incluindo o cabeçalho. Como se trata de um campo de 16 bits, isso significa que o maior segmento UDP será de:

216 = 65.536 bytes (64 KBytes)

O campo **soma de verificaçã**o tem a função de garantir que a mensagem chegue ao destino livre de erros. Para tanto, o UDP calcula o CRC dela e o envia neste campo. No destino, o CRC é novamente calculado e comparado. Se ambos forem iguais, a mensagem é considerada livre de erros e entregue na aplicação destino.

Protocolos de aplicações que utilizam o UDP são **DNS**, **SNMP**, **TFTP**, **RPC**.

**TCP**

O TCP é um orientado à conexão, sendo indicado para aplicações que precisam trocar uma grande quantidade de dados por meio de uma rede com múltiplos roteadores.

O TCP deve oferecer a confiabilidade que o IP não oferece.

Os três aspectos fundamentais da TCP são o modelo de serviço tcp, cabeçalho de segmento tcp, gerenciamento de conexão tcp.

**Modelo de serviço TCP**

O serviço TCP é obtido quando tanto o transmissor quanto o receptor criam pontos terminais, denominados **portas**.

Todas as conexões TCP são:

- **Full-duplex**: Dados podem ser enviados e recebidos por ela simultaneamente, uma linha telefonica por exemplo.

- **Ponto a ponto**: Interliga diretamente dois hospedeiros, não permitindo a participação de um terceiro na conversão, como quando conecectamos o celular no PC via USB.

**Uma conexão TCP é um fluxo de dados, e não de mensagens.**

As entidades TCP transmissoras e receptoras trocam dados na forma de segmentos. Um segmento consiste em um cabeçalho fixo de 20 bytes mais uma parte opcional, seguido de zero ou mais bytes de dados. O software TCP decide qual deve ser o tamanho dos segmentos, podendo:

- Acumular dados de várias escritas em um único segmento.
- Dividir os dados de uma única escrita em vários segmentos.

O protocolo básico utilizado pelas entidades TCP é o de janela deslizante. Quando envia um segmento, o transmissor dispara um temporizador. Assim que ele chega ao destino, a entidade TCP receptora retorna um segmento (com ou sem dados segundo as circunstâncias) com um número de confirmação igual ao próximo número de sequência que ela espera receber. Se o temporizador do transmissor expirar antes de a confirmação ser recebida, o segmento será retransmitido.

**Cabeçalho de segmento TCP**

![CabecalhoTCP](/Fundamentos%20de%20Redes%20de%20Computadores/Tema%203%20-%20Camadas%20de%20Aplica%C3%A7%C3%A3o%20e%20Transporte/img/cabecalhotcp.png)

**Gerenciamento de conexão TCP**

As conexões estabelecidas no TCP utilizam um esquema conhecido como three way handshake. Para estabelecer uma conexão, um lado aguarda passivamente, enquanto o outro solicita uma especificando o endereço de rede (endereço IP) e a porta com a qual deseja se conectar.