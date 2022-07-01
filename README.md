# Protocolo Matter PT-BR

  Quatro alunos do IFRN, um orientador e um sonho. Esse projeto de TCC está sendo desenvolvido para auxiliar pesquisadores brasileiros a encontrar conteúdo em Português do protocolo Matter. Aqui iremos colocar o desenvolvimento da nossa pesquisa e traduções de conteúdos em inglês. Esperamos auxiliar o máximo de jovens pesquisadores, caso tenha algum feedback para nos dar, em breve, criaremos um e-mail para contato.

  Tentaremos ao máximo traduzir conteúdos do Inglês para o Português e qualquer linguagem para o Python.

# O que é o metter?
  
  Matter (anteriormente Project Connected Home over IP, ou Project CHIP) é um novo Grupo de Trabalho dentro da Connectivity Standards Alliance (CSA, anteriormente Zigbee Alliance). Este Grupo de Trabalho planeja desenvolver e promover a adoção de um novo padrão de conectividade livre de royalties para aumentar a compatibilidade entre os produtos domésticos inteligentes, com a segurança como um princípio fundamental de design. 
  
O objetivo do projeto Matter é simplificar o desenvolvimento para os fabricantes e aumentar a compatibilidade para os consumidores. O projeto é construído em torno de uma crença compartilhada de que os dispositivos domésticos inteligentes devem ser seguros, confiáveis e fáceis de usar. Com base no Internet Protocol (IP), o projeto visa permitir a comunicação entre dispositivos domésticos inteligentes, aplicativos móveis e serviços em nuvem e definir um conjunto específico de tecnologias de rede baseadas em IP para certificação de dispositivos.

A CSA abriu oficialmente o Matter Working Group em 17 de janeiro de 2020 e está em processo de elaboração da especificação.
Visite buildwithmatter.com para saber mais e ler as últimas notícias e atualizações sobre o projeto.

# Visão do projeto.
Objetivos de desenvolvimento

  A matéria é desenvolvida com os seguintes objetivos e princípios em mente:

  *Unifying*: Matter produzirá uma nova especificação, construída com e em cima de tecnologias existentes testadas no mercado.

  *Interoperável*: A especificação permite a comunicação entre qualquer dispositivo certificado pela Matter, sujeito à permissão dos usuários.

  *Segurança*: A especificação aproveita as práticas e protocolos de segurança modernos.

  *Controle do usuário*: O usuário final está no controle da autorização para interação com os dispositivos.

  *Federado*: Nenhuma entidade única serve como regulador ou ponto único de falha para a raiz de confiança.

  *Robusto*: O conjunto de protocolos especifica um ciclo de vida completo de um dispositivo — começando com a experiência pronta para uso, passando por protocolos     operacionais, até as especificações de gerenciamento de dispositivos e sistemas necessárias para o funcionamento adequado na presença de alterações.
  
  *Baixa sobrecarga*: os protocolos são praticamente implementáveis em dispositivos com poucos recursos de computação, como MCUs.

  *Pervasivo*: Os protocolos são amplamente implantáveis e acessíveis, graças ao uso do IP e à implementação em dispositivos de baixa capacidade.

  *Ecossistema-Flexível*: O protocolo deve ser flexível o suficiente para acomodar a implantação em ecossistemas com políticas diferentes.

  *Fácil de usar*: o protocolo deve ter como objetivo fornecer um provisionamento suave, coeso e integrado e uma experiência pronta para uso.

  *Aberto*: A concepção e os processos técnicos do Projeto devem ser abertos e transparentes para o público em geral, inclusive para não membros, sempre que possível.

# Visão da arquitetura

O Projeto, conforme ilustrado acima, define a camada de aplicação que será implantada em dispositivos e controladores, bem como as redes baseadas em IPv6 suportadas para ajudar a atingir nossa meta de arquitetura de interoperabilidade. A Matter inicialmente oferecerá suporte a Wi-Fi e Thread para comunicações operacionais principais e Bluetooth Low Energy (BLE) para simplificar o comissionamento e a configuração do dispositivo.

A camada de aplicação 
pode ser dividida em 
sete componentes principais:

1- Aplicação: Lógica de negócios de alta ordem de um dispositivo. Por exemplo, um aplicativo focado em iluminação pode conter lógica para ligar/desligar a lâmpada, bem como suas características de cor.

2- Modelo de dados: primitivas de dados que ajudam a descrever as várias funcionalidades dos dispositivos. O Aplicativo opera nessas estruturas de dados quando há intenção de interagir com o dispositivo.

3- Modelo de interação: representa um conjunto de ações que podem ser executadas nos dispositivos para interagir com ele. Por exemplo, ler ou escrever atributos em um dispositivo corresponderia a interações com os dispositivos. Essas ações operam nas estruturas definidas pelo modelo de dados.

4- Enquadramento de Ação: Uma vez que uma ação é construída usando o Modelo de Interação, ela é enquadrada em um formato binário empacotado prescritivo para permitir que seja bem representada no “fio”.

5- Segurança: Um quadro de ação codificado é então enviado para a camada de segurança para criptografar e assinar a carga para garantir que os dados sejam protegidos e autenticados pelo remetente e pelo destinatário de um pacote.

6- Message Framing & Routing: Com uma interação criptografada e assinada, a Message Layer constrói o formato da carga com campos de cabeçalho obrigatórios e opcionais; que especificam as propriedades da mensagem, bem como algumas informações de roteamento.

7- Gerenciamento de Enquadramento e Transporte de IP: Após a construção da carga útil final, ela é enviada ao protocolo de transporte subjacente para gerenciamento de IP dos dados.
