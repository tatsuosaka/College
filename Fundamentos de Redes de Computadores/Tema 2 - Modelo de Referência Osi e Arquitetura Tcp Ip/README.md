# Modelo de Referência Osi e Arquitetura Tcp/ip

Reconhecer como as redes de computadores estão organizadas e estruturadas para definir as ferramentas adequadas ao processo de troca de dados entre todos os dispositivos.

***

## **Módulo 1 - Identificar o objetivo da divisão da estrutura das redes em camadas**

**Modelo em camadas**

A internet é um conjunto de redes de computadores que permite a troca de informações entre dispositivos computacionais.

Para que essa troca seja realizada de forma eficiente, devem ser estabelecidas regras de comunicação.

Essas regras são os protocolos de rede, que devem garantir que a comunicação ocorra de forma confiável, segura, eficaz, no momento certo e para a pessoa certa.

Mas o processo de troca de dados é uma tarefa extremamente complexa e assim os engenheiros e projetistas de redes utiliza um principio basico de resolução a técnica de dividir para conquistar

**Dividir para conquistar**

Nesta técnica, os projetistas dividem o problema em problemas menores e resolvem cada um de forma isolada. Se cada pequeno problema for resolvido, o grande problema será resolvido.

**Elementos da camada**

- **Serviço**: O serviço diz o que a camada faz e não como ela faz
- **Protocolo**: Responsavel como a camada faz
- **Interface**: Para a comunicação das camdadas é necessario que haja um ponto entre ambas chamada interface, podendo utilizar serviço de outra, passando as informações para a camada vizinha

**Onde, exatamente, tudo isso é implementado no computador?**

O que está implementado são os protocolos e interfaces, que podem estar desenvolvidos em um hardware, como uma placa de rede, ou em um software, como no sistema operacional da máquina.

**Comunicação horizontal e vertical**

- **Vertical**: Na origem, o dado a ser transmitido desce pelas camadas até o nível mais baixo. No destino, o processo ocorrerá de modo contrário, pois o dado sobe pelas camadas até o nível mais alto da arquitetura. Conforme o dado passa por determinada camada, o hardware ou o software, responsável por implementar o protocolo, irá preparar esse dado para que a regra (para a qual ele foi projetado) possa ser executada.

- **Horizontal**: Se a camada 2 é responsável pela verificação de erro, o dado será preparado na origem por essa camada para que, ao passar pela camada 2 do destino, seja verificado se houve erro ou não.

**Encapsulamento**

Cada camada adicionará um novo cabeçalho ao dado que será enviado, e esse processo é chamado de encapsulamento.

Esse procedimento acontece, repetidamente, até alcançar a camada 1 e a informação ser transmitida ao destino, onde ocorrerá o processo inverso. A informação subirá, desencapsulando as informações, da camada 1 até o usuário do serviço.

***

## **Módulo 2 - Identificar as camadas do Modelo OSI e suas funcionalidades**

**Modelo OSI**

Na década de 1970, a International Organization for Standardization (ISO), um  órgão que desenvolve padrões internacionais, criou um modelo de referência de camadas denominado OSI

O que utilizamos hoje do modelo OSI é a referência para as funções das camadas, então, quando ouvimos falar que determinado protocolo é da camada X (1, 2, 3, ...). Esse X refere-se ao OSI, tanto que é encontrada, em diversos livros e artigos, a expressão modelo de referência OSI (RM-OSI em inglês).

Possui sete camadas, de cima para baixo: aplicação, apresentação, sessão, transporte, rede, enlace e física.

Por mais que tenham sido especificados protocolos para cada camada, na prática, eles não são utilizados.

- As três camadas mais altas (**Aplicação, apresentação e sessão**) relacionadas a funções que dão suporte para que usuarios possam acessar os serviços de rede.

- As três camadas inferiores (**Rede, enlace e física**) relacionadas as opereções ligadas aos aspectos da movimentação dos dados de um dispositivo para outro.

- A camada **Transporte** faz a interligação entre suporte ao usuario e vai permitir que os dados das camadas mais baixas estejam em condições de serem utilizadas pelas camadas mais altas.

As camadas da 3 a 7 são praticamente implementadas em software por meios de protocolos

As camadas 1 e 2 podem ser associadas à placa de rede. A camada 2 ainda integra um pouco de software como os drivers de rede, mas a camada 1 é praticamente toda implementada em hardware.

- **Aplicação**: É mais proxima de ós aplicações oferecidas commo: web, email transferencia e streaming
- **Apresentação**: Responsavel que idependentemente do dispositivo (pc, cel, tv, carro etc) e operacional (linux, windows etc) seja possivel acessar
- **Sessão**: Organiza a comunicação entre os dispositivos
- **Transporte**: Garante a entrega de processo a processo de todos os dados enviados pelo usuário
- **Rede**: Determina o caminho da origem até o destino
- **Enlace**: Responsavel da entrega dos dados para a maquina de destino
- **Física**: Transmite os dados pelo meio de transmissão, codificando corretamente para que sejam enviados

***

## **Módulo 3 - Identificar as camadas da Arquitetura TCP/IP e suas funcionalidades**

**Arquitetura TCP/IP**

Batizada por TCP/IP por causa dos seus dois principais protocolos: Transmission Control Protocol (TCP) e Internet Protocol (IP). Ela foi apresentada pela primeira vez em 1974 (CERF, 1974) com o objetivo de criar uma arquitetura que permitisse a interligação de diversas redes de comunicação, sendo posteriormente adotada como padrão.

**Evolução do protocolo TCP/IP**

A arquitetura foi criada utilizando quatro camadas aplicação, transporte, internet e acesso à rede.

As funções das camadas de apresentação e sessão serão acumuladas pela camada de aplicação e a funções das camadas de enlace e física serão executadas pela camada de acesso à rede. Observe a relação entre os dois modelos a seguir.

| **MODELO TCP/IP** 	| **MODELO OSI** 	|
|:-----------------:	|:--------------:	|
|                   	|    Aplicação   	|
|     Aplicação     	|  Apresentação  	|
|                   	|     Sessão     	|
|     Transporte    	|   Transporte   	|
|      Internet     	|      Rede      	|
|   Acesso à rede   	|     Enlace     	|
|                   	|     Física     	|

- **Modelo OSI**: É baseado, principalmente, nas funcionalidades das camadas.

- **Arquitetura TCP/IP**: Não ficou presa apenas nas funcionalidades, mas, sim, no desenvolvimento de protocolos relativamente independentes e hierárquicos. A hierarquia baseia-se em um protocolo de nível superior que é suportado pelos protocolos de nível inferior.

**Camadas funções e principais protocolos**

**Aplicação**

A camada de aplicação da arquitetura TCP/IP nos permite acessar uma infinidade de serviços na internet. Desde os que são utilizados de forma direta pelos usuários, como o serviço Web, serviço de correio eletrônico, entre outros, bem como os que funcionam dando suporte à operação da rede, como o serviço de nomes (DNS). 

|             **Serviço**             	|   **Protocolo**  	|
|:-----------------------------------:	|:----------------:	|
|                 Web                 	|     https://     	|
|                E-mail               	| SMTP, POP e IMAP 	|
|                Nomes                	|        DNS       	|
|      Transferência de arquivos      	|     FTP, TFTP    	|
|     Áudio e video em tempo real     	|        RTP       	|
| Configuração automática de estações 	|       DHCP       	|

- **Cliente Servidor**: O cliente é executado por um usuário que requisita um serviço no servidor
- **Peer-to-peer**: Pensada no emprego minimo de servidores. a ideia é que usuários possam trocar informações diretas, como um chat por exemplo

**Transporte**

Tem a mesma funcionalidade no modelo **OSI**, **garantir a entrega de processo a processo de todos os dados enviados pelo usuário**. Porem, na arquitetura TCP/IP temos dois protocolos principais:

- **TCP**: Efetivamente confere confiabilidade. É adequado para aplicações de rede que precisam de confiabilidade na troca de mensagens entre processos.
- **UDP**: O protocolo não confere confiabilidade. Existe apenas para permitir que a mensagem seja encapsulada em um datagrama e entregue para o processo de destino correto.

**Então por que usamos o UDP?**

Ele é importante para as aplicações que demandam tempo de resposta baixo na comunicação, como em um áudio ou uma videoconferência, e nas aplicações que podem funcionar tolerando algum tipo de perda.

**Internet**

A camada internet ou, simplesmente, camada de rede tem por objetivo permitir que os dados injetados na rede pela máquina de origem possam alcançar o destino.

O principal protocolo da camada de rede é o IP, ele é encontrado em duas versões principais o **IPV4** e o **IPV6**.

- **Objetivo**: Os dois protocolos têm por objetivo definir o endereço lógico, conhecido como endereço IP.
- **Diferença**: Está no tamanho do endereço lógico 32 bits para IPV4 e 128 bits para IPV6.
- **Semelhança**: Não orientados a conexão e não tem confiabilidade, não realizam trantamento de errros e os datagramas são enviados de forma independente.

**Dizemos que o serviço da camada internet é de melhor esforço.**

Será feito o maior esforço de entregar as informações, mas não será garantida a entrega, nem a ordem, nem a ausência de erro. Qualquer problema deverá ser corrigido pelas camadas superiores.

**Acesso à rede**

Apesar de não fazer parte da arquitetura TCP/IP, a arquitetura desenvolvida pelo Instituto de Engenheiros Eletricistas e Eletrônicos (Institute of Electrical and Electronics Engineers – IEEE), denominada IEEE 802, é largamente utilizada na camada de acesso à rede.

Ela define diversos padrões utilizados nas redes locais e metropolitanas, como o padrão Ethernet e o famoso WiFi.