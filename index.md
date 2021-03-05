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

## Demo

<iframe width="560" height="315" src="https://www.youtube.com/embed/CHMlj9-EbrM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/uQhq9voh-fo" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/SBbq1wD8VqE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/6dg_NGRu4DU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>






## Links

* Bibliotecas gráficas
    * [OpenGL](https://www.opengl.org)
        * [go-gl](https://github.com/go-gl)
    * [GTK](https://www.gtk.org/)
        * [gotk3](https://github.com/gotk3/gotk3)
    * [Cairo](https://www.cairographics.org/)
        * [gocairo](https://github.com/evmar/gocairo)
    * [Vulkan](https://www.khronos.org/vulkan/)
        * [vulkan-go](https://github.com/vulkan-go/vulkan)
        * [vulkan-go/demos](https://github.com/vulkan-go/demos)
* Game engines
    * [Unreal](https://www.unrealengine.com)
    * [Source](https://pt.wikipedia.org/wiki/Source_(motor_de_jogo))
    * [Unity](https://unity.com)
* Golang game libraries
    * [Ebiten](https://ebiten.org/)

## Física

### Gravidade

![](<https://render.githubusercontent.com/render/math?math=F = mg>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow m \ddot x = mg>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow \ddot x = g>)

### Mola

![](<https://render.githubusercontent.com/render/math?math=F = -kx>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow m \ddot x = -kx>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow \ddot x = -(k/m)x>)

![](<https://render.githubusercontent.com/render/math?math=\Rightarrow \ddot x = -\omega^2x>)

### Equação de onda

![](<https://render.githubusercontent.com/render/math?math=\frac{d^2u}{dt^2} = c^2\frac{d^2u}{dx^2}>)

### Troca de calor

TODO: Equação da troca de calor para solução com diferenças finitas

## Papel de motores de física (engine de física)
* Colisão
* Forças (dinâmica/mecânica)
* Ray tracing
