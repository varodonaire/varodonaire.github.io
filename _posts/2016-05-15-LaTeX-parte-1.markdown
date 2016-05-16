---
title: LaTeX, parte 1
date: 2016-05-15 20:10
excerpt: "LaTeX en iOS, una primera aproximación"
categories: 
    - Tech
header:
  image: HeaderLaTeX1.png
---

Escribir en LaTeX es una necesidad importante, casi fundamental, para mí. Lamentablemente, hasta ahora encontrar una forma relativamente agradable de hacerlo en el iPad había sido frustrante. No sólo por las aplicaciones en sí mismas, sino que especialmente por la inflexibilidad con que fueron 

## ¿Qué es LaTeX?

LaTeX es un sistema de escritura de textos. Así como para escribir una página web, por ejemplo, se debe producir un archivo de texto con una cierta estructura y códigos, se sube a un servidor y el navegador toma el archivo y lo presenta de una forma adecuada, en LaTeX se escribe un archivo de texto con cierta estructura y código, se le entrega al programa LaTeX (o similar) el que lo lee y produce un archivo pdf. La gran gracia es que los pdfs creados son hechos como los haría un tipógrafo profesional, con una calidad excelente. Además, esto permite escribir con cierta facilidad —pasado el periodo de aprendizaje— textos que sería tremendamente difícil replicar en otros sistemas, como escritura matemática compleja.

En mi trabajo, el uso de LaTeX es tremendamente útil, porque escribo guías, textos, etc. (casi) Todos ellos tienen una buena carga de contenido matemático, además de seguir un estilo predefinido.

Técnicamente, LaTeX es un programa de línea de comando. Es decir, debería correrlo desde un terminal. Sin embargo…

## Aplicaciones en OS X

Existen varias aplicaciones en OS X diseñadas más o menos con LaTeX en mente. Una de las más antiguas, quizás simple y espartana, pero muy útil es [TeXShop.](http://pages.uoregon.edu/koch/texshop/) Una muestra de su *venerabilidad* es que todavía se promociona como binario universal. 

![TeXShop]({{base_path}}/images/LaTeX1/TeXShop.png "TeXShop"){: .align-center}

Si bien TeXShop es muy simple, debo reconocer que me gusta que mis editores de texto sean más simples, pero no por ello menos poderosos. Después de probar con el decano de los editores, BBEdit (en su versión gratis, [TextWrangler](http://www.barebones.com/products/textwrangler/)), terminé por usar un editor tremendamente sencillo de ver pero con muchísimas características, la beta de [TextMate 2.](http://macromates.com/download)

![TextMate]({{base_path}}/images/LaTeX1/TextMate.png "TextMate"){: .align-center}

La gracia de usar editores tan… desnudos para mí es que, dado que conozco bien la sintaxis de LaTeX, no necesito ventanas que me estén recordando cómo hacer tal o cual cosa. Conozco bien la organización de mis archivos, y con TextMate está, de todas formas, a una combinación de teclas de distancia.

Por supuesto, hay otras aplicaciones. No las he usado directamente, pero a algunas de ellas las he visto. Por ejemplo, [Texmaker.](http://www.xm1math.net/texmaker/) Es una aplicación en Java (sí, en 2016) pero, pese a eso, tiene algunas características que la hacen interesante, sibre todo para alguien que está partiendo. Por ejemplo, una ventana que integra el código junto con el PDF generado o también una multitud de paletas y ayudas.

Otra app interesante es [Texpad.](https://www.texpadapp.com/osx) La gran gracia que es posible mencionar de esta app es que posee un motor de sincronización con su contraparte en iOS. Esto, para mí, es en realidad su desgracia. *¿Otro motor de sincronización que mantener?* Además, la app en iOS no es nada muy fantástico tampoco (eso en un momento).

![Texpad]({{base_path}}/images/LaTeX1/Texpad.png "Texpad"){: .align-center}

### Marketing speak

Me llama la atención como, por ejemplo, Texpad promociona como features cosas como:

- Typesetting
- Auto-complete
- Document outline
- Custom typesetting
- Multi-lingual interface
- Snippets
- LaTeX/PDF synchronisation

Esas características son *absolutamente básicas* y creo que están presentes, de una forma u otra, en todos los editores. ¿Qué sentido tendría tener un editor de LaTeX que no tuviera composición de textos? O incluso, pedirle a un editor de LaTeX que dejara configurar la composición para hacerla personalizada también es una cosa bastante obvia. O, por ejemplo, la sincronización entre el archivo tex y el pdf es un proyecto aparte que, también, todas[^2] las apps usan.

[^2]: o casi todas

No es por pegarle a Texpad, de hecho casi todos los editores promocionan las mismas cosas. Pero precisamente eso hace que sea un poco inútil promocionarlas.

## Aplicaciones en iOS

Hay algunas aplicaciones dirigidas hacia escribir en LaTeX en el App Store. Sin embargo, una rápida búsqueda por "latex" nos muestra un panorama más bien deprimente.

![LaTeX en App Store]({{base_path}}/images/LaTeX1/TexAppStore.png "LaTeX en App Store"){: .align-center}

Francamente, del listado que aparece las únicas que vale la pena considerar son Texpad y TeX Writer. Otras apps son básicamente engaños (¿quién cobra US$ 9.99 por un app con la estética de iOS 6 y, sobre todo, quién los paga?) o apps "auxiliares" que muestran el código para escribir algo, pero no dejan usarlo en ninguna medida útil.

Las únicas dos apps "reales" son, como se dijo antes, Texpad y Tex Writer. Ambas son las únicas que pueden compilar el texto *en* el iPad (o iPhone). Texpad, además, tiene un servicio online para compilar.

![Tex Writer]({{base_path}}/images/LaTeX1/Texwriter.PNG "Tex Writer"){: .align-left}
![Texpad en iOS]({{base_path}}/images/LaTeX1/TexpadiOS.PNG "Texpad en iOS"){: .align-right}

¿Por qué, entonces, no me gustan estas apps? Para ser sincero, Texpad fue actualizada hace relativamente poco, un par de semanas. La aplicación ahora tiene una interfaz de usuario renovada, bastante más lógica de lo que era antes. Sin embargo, ambas tienen un par de dificultades que no me son prácticas.

Primero, ambas apps pueden conectarse a Dropbox, pero sólo a la carpeta de la aplicación. Es decir, dentro de dropbox cada una puede sincronizar sólo a una carpeta en específico. Si bien uso todavía Dropbox, estoy en proceso de abandonarlo y aunque no fuera así, es relativamente incómodo que sólo funcionen dentro de esta carpeta cuando mis proyectos (algunos de ellos relativamente grandes) están en una organización distinta. Esta restricción puede ser por una decisión de Dropbox, pero de todas formas afecta al uso que le doy a las apps.

Segundo, LaTeX en realidad es un sistema (enormemente) extensible mediante el uso de paquetes. En particular, después de más de 10 años de usar el sistema, uso algunos paquetes de manera sustancial. Si bien ambas apps pueden manejar paquetes, ninguna lo hace de un modo transparente. Tex Writer ofrece "descargar paquetes automáticamente". *Probablemente* lo haga de CTAN (el repositorio de paquetes oficial), pero no lo sé. Texpad ofrece descargar conjuntos de paquetes, pero no especifica en cuál se encuentra un paquete determinado, suponiendo que esté en alguno. En definitiva, no es un sistema tan transparente como usarlo en el escritorio.

Por otra parte, también hay algo de historia personal. Hasta hace algún tiempo, usaba Dropbox como mi modo principal de sincronizar archivos entre distintos dispositivos. Pero desde hace un año, aproximadamente, ocupé casi todo el espacio que tengo disponible. Al mismo tiempo, gracias a iCloud photo library y a la cantidad de fotos que tengo, contraté una ampliación del espacio de almacenamiento en iCloud. Después de sincronizar las fotos, me quedaba bastante espacio para usar, por lo que era razonable mover archivos de Dropbox a iCloud, salvo que los servicios online de Apple no tienen, exactamente, buena reputación.

Pero, para mi sorpresa, iCloud Drive (y photo library) funcionan bastante bien. En el tiempo que llevo usándolos no he tenido problemas con mis archivos, lo que por supuesto hizo que quisiera usarlos para más cosas. Es por esto que, en particular, si voy a usar LaTeX en el iPad, necesito usar una app que se lleve bien con iCloud. Ninguna de las dos mencionadas lo cumple. Texpad ofrece abrir archivos desde algún proveedor de documentos (como iCloud), pero no he conseguido que funcione. Tex Writer ni siquiera lo ofrece.

## Conclusiones brevísimas

En resumen, las soluciones que debieran ser fáciles no funcionan, al menos para mí. Eso me ha llevado a probar con algunas alternativas un poco más extremas. Todavía estoy probando, pero escribiré pronto acerca de estos intentos por si a alguien más le sirve.
