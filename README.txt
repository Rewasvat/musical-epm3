MAC337 - Computa��o Musical - EP3
Fernando Omar Aluani #USP: 6797226

PATCH PRINCIPAL: instrumento.pd

O prop�sito do meu trabalho � emular um intrumento de cordar, de tal forma que o usu�rio
possa toc�-lo usando o teclado.

O teclado simula 3 cordas. Cada linha de teclas (de A a Z) do teclado � uma corda,
onde cada tecla representa uma casa dessa corda, da esquerda para a direita.
As teclas 1, 2 e 3 tocam as respectivas cordas. Assim como num instrumento de corda
normal, a casa ligada mais � direita que afeta a nota tocada da corda.
Ou seja, temos:

corda 1 : q w e r t y u i o p
corda 2 : a s d f g h j k l
corda 3 : z x c v b n m

� poss�vel tamb�m mudar os seguintes par�metros para cada corda:
Width: comprimento do noise dado inicialmente para o Karplus-Strong quando � tocado.
Delay: atenua��o do feedback do algoritmo
Cutoff: intensidade do filtro do feedback
Nota inicial: a nota midi da corda quando ela � tocada sem nenhuma casa apertada.
	cada casa, da esquerda para a direita, aumenta a nota em 1.


O patch tamb�m mostra o espectro de magnitude e a forma de onda do som gerado
(a composi��o das 3 cordas juntas).

� poss�vel tamb�m usar um equalizador e setar um espacializador (assim como no
EP anterior).

Finalmente, � poss�vel tamb�m carregar um arquivo de texto que define uma m�sica
como uma sequ�ncia de notas definidas pela corda, casa e delay,
pelo patch loadMusic.pd (a interface dele est� presente no instrumento.pd).
Cada linha desse arquivo dever� ser da forma

C I D

onde:
C = corda a ser tocada (1, 2 ou 3)
I = indice da casa dessa corda a ser apertada (0 para nenhuma casa, e lembre-se do numero de casas em cada linha/corda)
D = delay, em milisegundos, para tocar a pr�xima nota.

Ao carregar um arquivo, a interface visual mostra quais cordas est�o sendo tocadas
e quais casas est�o ligadas, como se voc� tivesse tocando.
Mandei junto com o EP um arquivo de musica de exemplo, que simplesmente toca cada nota
das 3 cordas em sequ�ncia.


SOBRE OS PATCHES:
Os patches karpluc~.pd e stringInstance.pd foram pegos do site http://blog.loomer.co.uk/2010/02/karplus-strong-guitar-string-synthesis.html
O stringInstance.pd na verdade eu que fiz, mas fortemente baseado na demonstra��o do karpluc desse site.

Os outros patches nesse EP eu que fiz, alguns deles nos EP anteriores.
E desses que eu reaproveitei de EPs anteriores, teve alguns que eu alterei um pouco.
