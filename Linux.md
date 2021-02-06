---
title: Linux
author: Arthur P. Braga
---

#### Understanding Linux

- **Kernel ->** é o núcleo do sistema operacional, responsável por fazer as interações de hardware e software;   
- **Gnome ->** Uma das (GUI) Graphical user interface and set of computer desktop applications for users of the Linux; 
- **Shell ->** Interpretador de linhas de comando;

---

#### File Manipulation

- .rar -> unrar x (nome do arquivo) ;
- .zip -> unzip (nome do arquivo) ;
- .tar.xz -> tar -Jxf (nome do arquivo) ;    
- .tar.gz -> tar -xvzf (nome do arquivo) ;
- .deb -> dpkg -i (nome do arquivo)

---------------------------------------------------------------------------------------------------------------------------

#### Basic Commands

- pwd -> Exibe o diretório atual;

- mkdir -> criar diretório;

- touch (nome do arquivo)-> criar arquivo;

- autoremove -> remove programas obsoletos;

- autoclean -> limpa o cache do apt;

- cat (nome do arquivo) -> mostra o conteúdo do arquivo de texto no terminal;

- nano (nome do arquivo) -> edita um arquivo de texto no terminal;

- rm -rf (nome do arquivo) -> Remove diretório;

- rm (nome do arquivo) -> Remove arquivo;

- cp -> Copia o conteúdo do arquivo

- mv (arquivos_origem) (local_destino) -> move arquivos de um diretório para outro 

- free -> uso do hd

- df -> Uso da memóra ram

---

### Maratona Linux

##### Estrutura (diretórios)

**/boot ->** Tudo relacionado ao boot do sistema;

**/bin ->** Binários do sistema. Todos os path de ambiente...

**/etc ->** Todos os arquivos de configuração do sistema (host e hostname, por exemplo);

**/dev ->** Representa todos os dispositivos conectados ao pc, pendrive, hd... contém arquivos essenciais para tais dispositivos;

**/home ->** Arquivos pessoais, documentos, fotos, vídeos...

**/lib ->** Contém as bibliotecas do sistema;

**/lost+found ->** "Achados e perdidos", qualquer arquivo corrompido encontrado será enviado para esse diretório;

**/media ->** Mídias removíveis;

**/mnt ->** Montagem de sistemas temporários;

**/opt ->** Pacotes opcionais. Pacotes que não são padrões do SO. Ex: Google Chrome;

**/proc ->** Contém info do Kernel e processos que estão rodando;

**/root ->** Diretório home para o super usuário;

**/run ->** Arquivos temp de aplicativos;

**/srv ->** Serviços de dados

**/tmp ->** Arquivos temporários;

**/usr ->** Arquivos e aplicativos usados pelo usuário;

**/var ->** Arquivos de dados variáveis. Arquivos de log;