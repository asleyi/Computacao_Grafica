# **RATERIZAÇÃO**
<p>
O seguinte trabalho teve como objetivo desenvolver três funções (definidas abaixo), a fim de usá-las na implementação dos algoritmos para rasteirização de pontos e linhas, no intuito de construir (desenhar) um triângulo. 
	- PutPixel: Rasteriza um ponto na memória de vídeo, recebendo os parâmetros da posição do pixel (x,y) e da sua cor (RGBA);
	- DrawLine: Rasteriza uma linha na tela usando o algoritmo de Bresenham, recebendo como parâmetros seus vértices (inicial e final, representados respectivamente pelas coordenadas (x0,y0) e (x1,y1)) e suas respectivas cores (no formato RGBA). Ao longo da linha rasterizada as cores dos pixels interpolam-se lineramente;
	- DrawTriangle: Desenha um triângulo na tela recebendo como parâmetros as posições dos três vértices (xa, ya), (xb, yb), (xc, yc), e as cores (RGBA) de cada um desses vértices. 
</p>

##**RASTERIZAÇÃO DE UM PONTO (PUT PIXEL)**
<p>
  Os parâmetros de posição “x,y” variam, o x aumenta da esquerda para a direita e o y de cima para baixo. Esses parâmetros começam do zero e vão até o fim da janela menos um, ou seja, se for até a n-ésima posição, o limite será até n-1.
  O RGBA representa o padrão de cores em inglês: red (vermelho), green (verde), blue (azul) e alpha (transparência). O valor do “r,g,b,a” varia de 0 a 255. Neste trabalho, foi criado uma classe chamada xyRGBA que possui esses atributos.
	Para implementação dessa função foi criada uma classe com a posição “x,y” e a cor “RGBA”.
	Para saber em que posição de memória foi gravado o pixel, deve-se entender o cálculo do offset: um píxel possui 4 bytes e em cada byte desses define-se uma cor.
  O ponto a seguir, por exemplo, está na posição (256,256) e RGBA (255,255,255,255).
  </>
  ![putPixel][img/putPixel.png]
</p>
