Jogo em análise: NeonShooter

Grupo: Gabriel Lima 34981 e André Rodrigues 34984

<br>

**Descrição da implementação do jogo**

O NeonShooter é um jogo 2D do tipo twin-stick shooter desenvolvido com a framework MonoGame. O objetivo é sobreviver o máximo de tempo possível, destruir inimigos e aumentar a pontuação sem perder todas as vidas. A implementação assenta numa arquitetura orientada a objetos, com separação clara entre o núcleo do jogo e as plataformas onde ele é executado.
O projeto inclui movimento do jogador, disparo em várias direções, inimigos com comportamentos diferentes, sistema de pontuação, vidas, high score, colisões, efeitos visuais, partículas e som. A lógica principal está concentrada na pasta NeonShooter.Core, enquanto as restantes pastas tratam da execução em cada plataforma.

<br>

**Decisões tomadas**

Durante a análise da implementação, destacam-se várias decisões técnicas importantes:

->Separação por responsabilidades: o jogo está dividido em classes pequenas, cada uma com uma função específica.
->Arquitetura multiplataforma: o mesmo núcleo de jogo é reutilizado em Android, iOS, DesktopGL, WindowsDX e WindowsUWP.
->Gestão centralizada de entidades: o EntityManager organiza inimigos, balas, buracos negros e outras entidades, facilitando colisões e remoção de objetos.
->Uso de efeitos visuais: o efeito bloom, as partículas e a grelha deformável reforçam o estilo visual “neon”.
->Sistema de pontuação progressivo: o PlayerStatus controla pontos, multiplicador, vidas extra e recorde guardado em ficheiro.
->Comportamentos distintos de inimigos: existem inimigos que seguem o jogador e outros que se movem de forma aleatória.
->Código reutilizável: a classe Art centraliza imagens e fontes, e a classe Sound centraliza música e efeitos sonoros.

<br>

**Instruções de jogo**

O jogo pode ser controlado através do teclado, rato ou comando, dependendo da plataforma.

->Mover a nave: W, A, S, D ou analógico esquerdo do comando;
->Mirar: rato, setas ou analógico direito do comando
->Disparar: Espaço, clique do rato ou gatilhos do comando
->Pausar o jogo: P
->Sair do jogo: Esc ou botão Back no comando

<br>

**Organização do projeto**

->NeonShooter.Core — contém a lógica principal do jogo, os conteúdos, as classes de entidades, o sistema de input, partículas, som e efeitos visuais;
->NeonShooter.DesktopGL, NeonShooter.WindowsDX, NeonShooter.Android, NeonShooter.iOS e NeonShooter.WindowsUWP — projetos de arranque para cada plataforma;
->Content — imagens, sons, shaders e fonte do jogo.

<br>

**Observações finais**

Este projeto mostra uma boa estrutura de base para um jogo 2D em MonoGame, com forte separação de responsabilidades, reutilização de código e integração de vários sistemas fundamentais como desenho, colisões, input, som e efeitos visuais.
