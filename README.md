Grupo:
Gabriel Lima 34981
André 34984


Analise jogo 2D 

 

Introdução  

Este trabalho tem o objetivo de analisar a implementação de um jogo 2D escolhido nos repositórios Git. O jogo que escolhemos foi o NeonShooter , desenvolvido com a framework XNA/MonoGame. Neste trabalho vamos analisar a organização das pastas do projeto e o funcionamento das principais classes. 

 

Organização das Pastas 

 

O repositório Contém as Pastas: 

NeonShooter.Android  

NeonShooter.iOS  

NeonShooter.DesktopGL  

NeonShooter.WindowsDX  

NeonShooter.WindowsUWP  

NeonShooter.Core 

 

 

Importância das pastas: 

NeonShooter.Core: Contem os ficheiros da lógica do jogo como movimento, colisões, pontuação e as entidades player, inimigos, tiros. 

Também contem outra pasta responsável por armazenar as artes e os áudios do jogo. 

 

As seguintes pastas são responsáveis para: 

Android  

iOS  

DesktopGL  

WindowsDX  

WindowsUWP  

 

 

Iniciar o jogo naquela plataforma  

Configurar gráficos, input e execução 

Assim o jogo pode funcionar em diversas plataformas  

 


Analise Código disponível  

 

Classe Art 

A classe Art é responsável por carregar e guardar todas as imagens e fontes usadas no jogo. Inclui elementos como o jogador, inimigos, tiros e efeitos visuais. O método Load usa o ContentManager para carregar esses recursos a partir da pasta do projeto. A classe é estática, o que permite aceder facilmente aos recursos em qualquer parte do código. Também é criado um pixel branco de 1x1, usado para desenhar formas simples no jogo. Esta organização facilita a gestão e reutilização dos elementos gráficos. 


 

Classe BlackHole 

A classe BlackHole representa um elemento do jogo que atrai ou afasta outros objetos. Os inimigos e o jogador são puxados para o buraco negro, enquanto os tiros são repelidos. Este objeto tem pontos de vida e pode ser destruído pelo jogador. Quando isso acontece, são geradas partículas visuais e o jogador ganha pontos. 

O buraco negro também cria efeitos visuais contínuos, como partículas em movimento e uma animação de pulsação. Além disso, aplica forças no ambiente à sua volta, influenciando o comportamento de outros elementos do jogo. 


 

Classe BloomComponent 

A classe BloomComponent é responsável por aplicar um efeito visual chamado bloom, que cria um brilho nas partes mais luminosas do jogo. Este efeito melhora a aparência gráfica, tornando o jogo mais atrativo. 

O processo funciona em várias etapas: primeiro é capturada a imagem do jogo, depois são selecionadas as partes mais brilhantes, aplicando-se um efeito de desfoque (blur). Por fim, essa imagem é combinada com a original, criando o efeito de brilho. 

A classe utiliza shaders e técnicas de pós-processamento para realizar estes cálculos, mostrando uma abordagem mais avançada no tratamento gráfico do jogo. 


 

Classe BloomSettings 

A classe BloomSettings define as configurações do efeito de brilho (bloom) do jogo. Permite ajustar vários parâmetros, como a intensidade do brilho, o nível de desfoque e a saturação das cores. 

Esta classe também inclui vários modos pré-definidos (presets), como “Default”, “Soft” e “Blurry”, que facilitam a escolha de diferentes estilos visuais sem necessidade de configurar tudo manualmente. 

Esta abordagem permite personalizar facilmente os efeitos gráficos do jogo. 


 

Classe Bullet 

A classe Bullet representa os tiros disparados no jogo. Cada bala tem uma posição, velocidade e direção, sendo atualizada constantemente durante o jogo. 

As balas movem-se pelo ecrã e aplicam um pequeno efeito visual no ambiente à sua volta. Quando saem da área visível, são removidas e são geradas partículas para criar um efeito visual. 

Esta classe é responsável pelo comportamento e ciclo de vida dos projéteis no jogo. 


 

Classe ColorUtil 

A classe ColorUtil é responsável por converter cores entre diferentes formatos. Permite transformar cores do formato RGB para HSV e vice-versa. 

Estas conversões são úteis para criar efeitos visuais mais avançados, como mudanças de cor, brilho e animações. 

Esta classe ajuda a melhorar os efeitos gráficos do jogo, tornando-os mais dinâmicos e personalizados. 


 

Classe Enemy 

A classe Enemy representa os inimigos do jogo. Cada inimigo tem posição, movimento e um valor de pontos associado. Existem diferentes tipos de inimigos, como os que seguem o jogador (Seeker) e os que se movem aleatoriamente (Wanderer). 

Os inimigos possuem comportamentos definidos, que controlam a forma como se movimentam no jogo. Também têm um pequeno efeito visual ao aparecer no ecrã. 

Quando são destruídos, desaparecem, dão pontos ao jogador e geram efeitos visuais com partículas. 

Esta classe é responsável pelo comportamento, movimento e interação dos inimigos no jogo. 


 

Classe EnemySpawner 

A classe EnemySpawner é responsável por gerar inimigos e outros elementos durante o jogo. Os inimigos aparecem de forma aleatória no ecrã, mas sempre a uma certa distância do jogador. 

Existem diferentes tipos de inimigos que podem ser criados, bem como buracos negros em menor quantidade. A frequência com que os inimigos aparecem aumenta ao longo do tempo, tornando o jogo mais difícil. 

Esta classe controla o ritmo do jogo e a dificuldade, garantindo uma experiência progressiva para o jogador. 


 

Classe PlayerShip 

A classe PlayerShip representa o jogador no jogo. Controla o movimento, os disparos e o estado do jogador (vivo ou morto). 

O jogador pode mover-se pelo ecrã e disparar tiros em direção ao alvo, com um pequeno intervalo entre disparos. Também são criados efeitos visuais, como o rasto da nave durante o movimento. 

Quando o jogador perde uma vida, ocorre uma explosão com partículas e, após algum tempo, o jogador reaparece. 

Esta classe é responsável pelo controlo principal do jogador e pela sua interação com o jogo. 

 


Classe PlayerStatus 

A classe PlayerStatus é responsável por gerir o estado do jogador, incluindo pontuação, vidas, multiplicador e pontuação máxima. 

O sistema de multiplicador aumenta os pontos ganhos quando o jogador tem bom desempenho, mas volta ao normal após algum tempo sem ação. O jogador também pode ganhar vidas extra ao atingir certos valores de pontuação. 

A pontuação máxima é guardada num ficheiro, permitindo manter o recorde entre diferentes sessões de jogo. 

Esta classe controla a progressão do jogador e o sistema de pontuação do jogo. 


 

Conclusão 

Conclui-se que o projeto analisado apresenta uma estrutura bem organizada, com separações entre a parte principal do jogo a pasta Core e as diferentes plataformas onde pode ser executado. 

A Divisão do código foi feita em várias classes, cada uma com funções específicas, como o controlo do jogador, inimigos, efeitos visuais e sistema de pontuação. 

Esta análise permitiu compreender melhor como organizar e como desenvolver um jogo 2D. 
