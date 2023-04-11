---

title: "Haciendo trampa con LaTeX en el iPad, parte 2"
excerpt: "LaTeX en iOS, pero no en iOS, pero ahora en general"
categories:
  - Tech
header:
  image: images/HeaderLaTeX1.png

---

Hace mucho tiempo (que es lo que siempre digo en estos casos, porque *siempre* la última vez fue hace mucho tiempo), [escribía]({{ site.baseurl }}{% post_url 2016-12-08-trampa-latex %}) acerca de como compilaba LaTeX en el mac desde el iPad haciendo algunos trucos medio cochinos, además de prometer que actualizaría el método a algo más decente.

Finalmente, después de nunca acordarme, lo hice. Para esta solución sigo usando [Hazel](https://www.noodlesoft.com) y un script de línea de comandos, pero además estoy usando una solución que no conocía, [latexmk,](https://www.ctan.org/pkg/latexmk?lang=en) que me permite automatizar todas las distintas compilaciones que LaTeX debe hacer (varias pasadas de [XeLaTeX](http://xetex.sourceforge.net), [biber](http://biblatex-biber.sourceforge.net) y quizás qué más).

Las condiciones que debe cumplir el archivo .tex siguen siendo las mismas, tener la extensión .tex y que el nombre incluya "compile".

![Condiciones]({{base_path}}/images/trampaLaTeX2/Condiciones.png "Condiciones del script"){: .align-center}

Sin embargo, ahora el script realmente compila el archivo que cumpla las características definidas antes en vez de siempre el mismo archivo *hardcodeado.*

![Script]({{base_path}}/images/trampaLaTeX2/Script.png "Script"){: .align-center}

	foldername=$(dirname "$1")
	export foldername
	filename=$(basename "$1")
	filesimple=${filename%.*}
	cd $foldername
	latexmk "$filesimple"

Básicamente, lo que el código hace es tomar el path del archivo, dejarlo disponible para después, tomar el nombre del archivo, sacarle la extensión, moverse a la carpeta donde está y correr latexmk sobre el archivo.

Ahora, la maravillosa acción de Hazel "Reglas en subcarpetas" es de mucha utilidad…