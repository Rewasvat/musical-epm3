MAC337 - Computação Musical - EP3
Fernando Omar Aluani #USP: 6797226

PATCH PRINCIPAL: instrumento.pd

O propósito do meu trabalho é emular um intrumento de cordar, de tal forma que o usuário
possa tocá-lo usando o teclado.

O teclado simula 3 cordas. Cada linha de teclas (de A a Z) do teclado é uma corda,
onde cada tecla representa uma casa dessa corda, da esquerda para a direita.
As teclas 1, 2 e 3 tocam as respectivas cordas. Assim como num instrumento de corda
normal, a casa ligada mais à direita que afeta a nota tocada da corda.
Ou seja, temos:

corda 1 : q w e r t y u i o p
corda 2 : a s d f g h j k l
corda 3 : z x c v b n m

É possível também mudar os seguintes parâmetros para cada corda:
Width: comprimento do noise dado inicialmente para o Karplus-Strong quando é tocado.
Delay: atenuação do feedback do algoritmo
Cutoff: intensidade do filtro do feedback
Nota inicial: a nota midi da corda quando ela é tocada sem nenhuma casa apertada.
	cada casa, da esquerda para a direita, aumenta a nota em 1.


O patch também mostra o espectro de magnitude e a forma de onda do som gerado
(a composição das 3 cordas juntas).

É possível também usar um equalizador e setar um espacializador (assim como no
EP anterior).

Finalmente, é possível também carregar um arquivo de texto que define uma música
como uma sequência de notas definidas pela corda, casa e delay,
pelo patch loadMusic.pd (a interface dele está presente no instrumento.pd).
Cada linha desse arquivo deverá ser da forma

C I D

onde:
C = corda a ser tocada (1, 2 ou 3)
I = indice da casa dessa corda a ser apertada (0 para nenhuma casa, e lembre-se do numero de casas em cada linha/corda)
D = delay, em milisegundos, para tocar a próxima nota.

Ao carregar um arquivo, a interface visual mostra quais cordas estão sendo tocadas
e quais casas estão ligadas, como se você tivesse tocando.
Mandei junto com o EP um arquivo de musica de exemplo, que simplesmente toca cada nota
das 3 cordas em sequência.


SOBRE OS PATCHES:
Os patches karpluc~.pd e stringInstance.pd foram pegos do site http://blog.loomer.co.uk/2010/02/karplus-strong-guitar-string-synthesis.html
O stringInstance.pd na verdade eu que fiz, mas fortemente baseado na demonstração do karpluc desse site.

Os outros patches nesse EP eu que fiz, alguns deles nos EP anteriores.
E desses que eu reaproveitei de EPs anteriores, teve alguns que eu alterei um pouco.
