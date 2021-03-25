## Introdução

Você sempre foi louco pra saber como os games simulam de forma tão espetacular as leis da física do nosso universo?! Ou então como aplicações de engenharia são capazes de calcular respostas valiosas para processos físicos extremamente complexos?!

Nessa talk veremos como construir uma engine de física rudimentar "do zero". E, de brinde, uma visão geral sobre como simular equações diferenciais diversas, como propagação de ondas e troca de calor.

Se você já conhece alguns dos assuntos abaixo, ótimo! E se não conhece, vai conhecer (um pouco)!

* Colisões
* Método Runge-Kutta
* Geometria analítica
* Equações diferenciais
* Método das diferenças finitas
* Método dos elementos finitos

## Apresentação #TheDevConf2021

### Slides
[https://docs.google.com/presentation/d/1tYFk4HBiNBm055w3Q6BlqgSmC449U-YSfpjitAAE3_A/edit?usp=sharing](https://docs.google.com/presentation/d/1tYFk4HBiNBm055w3Q6BlqgSmC449U-YSfpjitAAE3_A/edit?usp=sharing)

### Code samples demonstrados na apresentação
Foco em didática, não em estrutura de projeto.
[https://github.com/rpagliuca/code-samples-da-inercia-ao-build](https://github.com/rpagliuca/code-samples-da-inercia-ao-build)

### Indo além
Projetos melhor estruturados, quebrados em múltiplos packages, tipos e comandos:
* Engine de física um pouco mais refinada, incluindo renderização com OpenGL e Ebiten: [https://github.com/rpagliuca/go-physics](https://github.com/rpagliuca/go-physics)

* Helpers para OpenGL e go-gl: [https://github.com/rpagliuca/go-gl-helpers](https://github.com/rpagliuca/go-gl-helpers)

### Vídeo (ensaio)
<iframe width="560" height="315" src="https://www.youtube.com/embed/O6HPnl_UE48" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## Renderização de algumas simulações demonstradas utilizando OpenGL e Ebiten.

<iframe width="560" height="315" src="https://www.youtube.com/embed/CHMlj9-EbrM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/uQhq9voh-fo" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/SBbq1wD8VqE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/6dg_NGRu4DU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## Vídeo do salto do paraquedista Felix Baumgartner a partir de 39km de altura

<iframe width="560" height="315" src="https://www.youtube.com/embed/dOoHArAzdug" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Artigo de Fernando Lang da Silveira, do Instituto de Física da Universidade Federal do Rio Grande do Sul, descrevendo a física do salto: [https://www.scielo.br/pdf/rbef/v37n2/0102-4744-rbef-37-02-2306.pdf](https://www.scielo.br/pdf/rbef/v37n2/0102-4744-rbef-37-02-2306.pdf)

## Fenômenos físicos comuns

### Gravidade (força gravitacional constante na Terra)

![](<https://render.githubusercontent.com/render/math?math=F = mg>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow m \ddot x = mg>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow \ddot x = g>)

#### Para obter a gravidade em grandes altitudes ao redor da Terra:
Lei da gravitação universal de Newton:

![](<https://render.githubusercontent.com/render/math?math=F = G\frac{Mm}{r^2}>)

### Mola (força elástica)

OBS - Esse fenômeno não foi demonstrado na apresentação, mas é bastante valioso para modelagem de sistemas de colisões e acoplamento entre objetos.

![](<https://render.githubusercontent.com/render/math?math=F = -kx>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow m \ddot x = -kx>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow \ddot x = -(k/m)x>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow \ddot x = -\omega^2x>)

### Equação de onda

Descreve a propagação de uma onda (mecânica, acústica, etc) em um dado meio. Para simulá-la, utilizamos método das diferenças finitas discretizando o tempo e o espaço (em 1 ou mais dimensões de espaço).

![](<https://render.githubusercontent.com/render/math?math=\frac{d^2u}{dt^2} = c^2\frac{d^2u}{dx^2}>)

### Equação de calor

Descreve o fenômeno de difusão de calor em um sólido. Para simulá-lo, utilizamos método das diferenças finitas discretizando o tempo e o espaço (em 1 ou mais dimensões de espaço).

![](<https://render.githubusercontent.com/render/math?math=\frac{du}{dt} = c^2\frac{d^2u}{dx^2}>)

## Papel de motores de física (engine de física)
* Colisão
* Forças (dinâmica/mecânica)
* Ray tracing

OBS - Por razões de otimização performance, às vezes são confundidas as responsabilidades de uma engine de física e de uma biblioteca de renderização.

## Links

* Bibliotecas gráficas em Go
    * [OpenGL](https://www.opengl.org)
        * [go-gl](https://github.com/go-gl)
    * [GoGraphics - fogleman/gg](https://github.com/fogleman/gg)
        * [Portfólio do Fogleman (diversas bibliotecas gráficas incríveis em várias linguagens)](https://www.michaelfogleman.com/)
    * [GTK](https://www.gtk.org/)
        * [gotk3](https://github.com/gotk3/gotk3)
    * [Cairo](https://www.cairographics.org/)
        * [gocairo](https://github.com/evmar/gocairo)
    * [Vulkan](https://www.khronos.org/vulkan/)
        * [vulkan-go](https://github.com/vulkan-go/vulkan)
        * [vulkan-go/demos](https://github.com/vulkan-go/demos)
* Golang game libraries
    * [Ebiten](https://ebiten.org/)
* Game engines (links extras, não diretamente relacionados com Go, nem simulação de física)
    * [Unreal](https://www.unrealengine.com)
    * [Source](https://pt.wikipedia.org/wiki/Source_(motor_de_jogo))
    * [Unity](https://unity.com)

