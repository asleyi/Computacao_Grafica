# **RATERIZAÇÃO**
<p>
O seguinte trabalho teve como objetivo desenvolver três funções (definidas abaixo), a fim de usá-las na implementação dos algoritmos para rasteirização de pontos e linhas, no intuito de construir (desenhar) um triângulo. </p>
<p>
	<ul>
	- PutPixel: Rasteriza um ponto na memória de vídeo, recebendo os parâmetros da posição do pixel (x,y) e da sua cor (RGBA);
	</ul>
	<ul>
	- DrawLine: Rasteriza uma linha na tela usando o algoritmo de Bresenham, recebendo como parâmetros seus vértices (inicial e final, representados respectivamente pelas coordenadas (x0,y0) e (x1,y1)) e suas respectivas cores (no formato RGBA). Ao longo da linha rasterizada as cores dos pixels interpolam-se lineramente;
	</ul>
	<ul>
	- DrawTriangle: Desenha um triângulo na tela recebendo como parâmetros as posições dos três vértices (xa, ya), (xb, yb), (xc, yc), e as cores (RGBA) de cada um desses vértices. 
	</ul>
</p>

**RASTERIZAÇÃO DE UM PONTO (PUT PIXEL)**
<p>
  Os parâmetros de posição “x,y” variam, o x aumenta da esquerda para a direita e o y de cima para baixo. Esses parâmetros começam do zero e vão até o fim da janela menos um, ou seja, se for até a n-ésima posição, o limite será até n-1.
</p>
<p>
  O RGBA representa o padrão de cores em inglês: red (vermelho), green (verde), blue (azul) e alpha (transparência). O valor do “r,g,b,a” varia de 0 a 255. Neste trabalho, foi criado uma classe chamada xyRGBA que possui esses atributos.
</p>
<p>
Para implementação dessa função foi criada uma classe com a posição “x,y” e a cor “RGBA”.
</p>
<p>
Para saber em que posição de memória foi gravado o pixel, deve-se entender o cálculo do offset: um píxel possui 4 bytes e em cada byte desses define-se uma cor.
</p>
<p>
  O ponto a seguir, por exemplo, está na posição (256,256) e RGBA (255,255,255,255).
</p>

![putPixel](https://github.com/asleyi/Computacao_Grafica/blob/master/putPixel.PNG)


**RATERIZAÇÃO DE LINHAS (DRAW LINE)

<p>
	A rasterirização da linha é feita através do algoritmo de Bresenham, conhecido também como algoritmo do ponto médio. Nele, os píxels que possuem a reta devem ser contínuos. No entanto, esse algoritmo é aplicado apenas para um octante (se calculam os pontos de 0º a 45º), por isso, é necessário modificá-lo para os outros octantes.
</p>

<p>
	A função DrawLine() propõe a união de dois pontos por uma reta, calculando sempre entre os próximos pixels E e NE. Para tal, foi reutilizada a função putPixel repetidamente. Se caso esses pontos tivessem cores diferentes, uma interpolação dessas cores teria de ser realizada. Para teste colocou-se um pixel central (256, 256) e o restante dos pontos que abrangem todos os octantes do centro a borda.
</p>


	


