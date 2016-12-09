---

title: "Haciendo trampa con LaTeX en el iPad"
excerpt: "LaTeX en iOS, pero no en iOS"
categories:
  - Tech
header:
  image: images/HeaderLaTeX1.png

---

Hace algún tiempo (largo), [escribía]({{ site.baseurl }}{% post_url 2016-05-15-LaTeX-parte-1 %}
) sobre LaTeX y las aplicaciones, para mí deficientes, que hay en iOS para escribir en este formato. En resumen, nada que ver con la riqueza que hay para escribir en markdown, por ejemplo.

Durante este tiempo hice algunos experimentos para tratar de aliviar estos problemas. Por ejemplo, descubrí [Textastic](https://www.textasticapp.com), un editor de texto muy sencillo, pero útil en iOS. Bastante espartano en su interfaz, pero en realidad así es como me gustan. Además, sincroniza con iCloud Drive de manera bastante rápida.[^1]

![Textastic]({{base_path}}/images/trampaLaTeX/Textastic.png "Textastic"){: .align-center}


Sin embargo, seguía teniendo el problema de cómo componer[^2] el archivo de LaTeX remotamente. Intenté algunas aproximaciones medio exóticas, como escribir en markdown y usar [pandoc](http://pandoc.org) en el mac, pero el problema real era cómo gatillar el procesamiento del archivo.



Todo esto se hizo mucho más urgente hace poco: necesitaba escribir mi proyecto de tesis. Si bien en general hay harto que hacer para poder terminarlo, en mi caso gracias a varias situaciones accidentales en el camino, contaba con dos semanas para hacerlo. Extremadamente poco tiempo, por lo que había que aprovecharlo. Y, para mí, escribir en la casa es equivalente a distraerme. Necesitaba el iPad para poder escribir afuera, en algún café, algo donde no me distrajera tanto (a todo esto, a mi notebook ya no le funciona el teclado, así que tenía que ser en el iPad).

Finalmente, hice un hack bien sucio e inelegante, pero que funciona y es extensible. En la carpeta del proyecto creé una regla de [Hazel](https://www.noodlesoft.com)

![Hazel]({{base_path}}/images/trampaLaTeX/Hazel1.png "Hazel"){: .align-center}

cuya condición es que si el archivo tiene extensión .tex y el nombre contiene "compile"

![Regla de compilar un archivo, el del proyecto de tesis]({{base_path}}/images/trampaLaTeX/Hazel2.png "Regla de compilar un archivo, el del proyecto de tesis"){: .align-center}

borre "compile" del nombre y lo compile con [XeLaTeX](https://en.wikipedia.org/wiki/XeTeX), [Biber](http://biblatex-biber.sourceforge.net) y de nuevo XeLaTeX. Esto es para que la bibliografía quede actualizada.

Ahora, claramente el script no es lo mejor que podría ser: está fijo el archivo que compila. Es decir, podría cambiarle el nombre y agregar compile a cualquier archivo en la misma carpeta y compilaría el mismo archivo siempre. Es fácil de cambiar, sin embargo, y sólo por falta de tiempo no lo he hecho.

¿Funciona? Sí. Aunque sea un arreglo hecho a la rápida, me permitió terminar el proyecto a tiempo.

[^1]: Igual son archivos de texto, así que sería muy no si se demorara.

[^2]: Es como compilar.
