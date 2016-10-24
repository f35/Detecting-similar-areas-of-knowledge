- title : Detecting similar areas of knowledge using Semantic and Data Mining technologies
- description : Thesis presentation in order to obtain the degree of Computer Scientist from the University of Cuenca.
- author : Xavier Sumba
- theme : white
- transition : default

***

### Detecting similar areas of knowledge using Semantic and Data Mining technologies
<div style="font-size:11pt;"><i>Detección de areas similares de conocimiento usando tecnologías semánticas y minería de datos.</i></div>
<br><hr><br>
##### <div style="font-size:18pt;"><a style="color: black;" href="http://cuent.tk">Xavier Sumba</a> / <a style="color: black;" href="https://www.facebook.com/FERNANDO2654?fref=ts">Freddy Sumba</a></div>


<div style="font-size:15pt;"><i>Universidad de Cuenca, Departamento de Ciencias de la Computación, Cuenca, Ecuador.</i></div>


![](images/uc.png)

***

### Introducción

- ¿Quién trabaja en líneas de investigación parecidas?
- ¿Cómo se puede crear una red de investigadores de un área en común, cuando no conocemos si estas existen?
- Obtener sus artículos, conocer revistas en las que fueron aceptados, entre otros.

***

### Problemas comunes

![an alternative text](images/problema.png)

***

### Arquitectura General

![an alternative text](images/platformDiagram.png)

---

### Data Sources

![an alternative text](images/sources.png)

#### Fuentes de datos bibliográficas

<div style="text-align: justify;">Las fuentes utilizadas, contienen información de investigadores y publicaciones científicas. Abarcan diferentes dominios de estudio, por lo que la estructura de los datos varían por cada fuente. Algunas fuentes proveen APIs que permiten la extracción de datos, sin embargo se tienen limitaciones de cuota.</div>

---

### Data Extraction

<div style="text-align: justify;">El modulo de extracción de datos se encarga de obtener y describir datos bibliográficos desde varias fuentes, utilizando tecnologías semánticas y principios de Linked Data.</div>

<div style="text-align: justify;">El modelo de datos de la fuente es mapeado a un modelo común basado en la ontología BIBO.</div>

---

- class : withbackground

**Ejemplo de diferencia entre atributos de DBLP y el modelo de datos común.**

<table style="font-size: large;">
<thead>
<tr class="header">
<th><p>DBLP fields</p></th>
<th><p>Common model fields</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dblp:primaryElectronicEdition</p></td>
<td><p>bibo:uri</p></td>
</tr>
<tr class="even">
<td><p>dblp:publishedAsPartOf</p></td>
<td><p>dc:isPartOf</p></td>
</tr>
<tr class="odd">
<td><p>dblp:publishedInBook</p></td>
<td><p>dc:publisher</p></td>
</tr>
<tr class="even">
<td><p>dblp:authoredBy</p></td>
<td><p>dc:contributor</p></td>
</tr>
<tr class="odd">
<td><p>dblp:title</p></td>
<td><p>dc:title</p></td>
</tr>
<tr class="even">
<td><p>dblp:pageNumbers</p></td>
<td><p>bibo:numPages</p></td>
</tr>
</tbody>
</table>

' | DBLP fields                   | Common model fields |
' |-------------------------------|---------------------|
' | dblp:primaryElectronicEdition | bibo:uri            |
' | dblp:publishedAsPartOf        | dc:isPartOf         |
' | dblp:publishedInBook          | dc:publisher        |
' | dblp:authoredBy               | dc:contributor      |
' | dblp:title                    | dc:title            |
' | dblp:pageNumbers              | bibo:numPages       |

---

### Data Enrichment
#### Mapeo del modelo de datos

<div style="font-size: 80%;">El modelo de datos de cada fuente es diferente, por lo cual se realiza un mapeo de la fuente al modelo de datos común y se almacena en el repositorio central.</div>

<p><img src="images/grafos.png" alt=""></p>

---

### Data Enrichment
#### Desambiguación de información.

<div style="font-size: 80%;">Debido a que se obtiene datos de diferentes fuentes bibliogríficas se tiene datos incoherentes o duplicados. Por lo que es necesario utilizar técnicas de desambiguación, en autores y publicaciones.</div>

<p><img src="images/desamibiguacion_a.png" alt=""></p>

---

### Data Enrichment
#### Desambiguación de información.

<p><img src="images/desamibiguacion_b.png" alt=""></p>

---

### Pattern Detection
#### Proceso para detección de areas y redes de colaboración

![](images/pdetection.png)


<div style="font-size: 80%; text-align: justify;">
<span style="color: red;">Find groups</span> detectar patrones de los datos almacenados en el repositorio central.

<div class="fragment">
<span style="color: red;">Knowledge Discovery</span> asociar patrones a un formato legible por un humano. Se descubre redes de colaboración y áreas de
conocimiento.
</div>

<div class="fragment">
<span style="color: red;">Label Groups</span> Se encuentra una etiqueta a cada cluster, ayuda a acelerar consultar y mantener la información
organizada en el repositorio.
</div>
<div>

---

### Find Groups

![](images/findgroups.png)

---

### Knowledge Discovery

<table style="width:100%">
  <tr>
    <th style="width: 30%; vertical-align: middle;"><img src="images/fgroups_files.png" alt=""></th>
    <th class="fragment" style="width: 70%"><img src="images/find_groups_process.png" alt=""></th>
  </tr>
</table>

---

# Topic Model + WordNet

<div class="fragment">
# =
# Label
</div>

---
### Topic Model
![](images/lda.png)

[Imagen de *David M. Blei* - Probabilistic Topic Models ](http://www.cs.princeton.edu/~blei/kdd-tutorial.pdf)

' Frecuencia Distribución de palabras/topicos
' Numero de topicos
' Varios documentos a varios topicos

---

### Label Groups

![](images/etiqueta.png)

---

### Datos listos para ser explotados

![](images/export.png)

---

### Resultados

![](images/redes.png)

---

<script type="text/javascript" src="https://www.google.com/jsapi"></script>
<script type="text/javascript">
    google.load("visualization", "1", {packages:["corechart"]})
    google.setOnLoadCallback(drawChart);
function drawChart() {
    var data = new google.visualization.DataTable({"cols": [{"type": "string" ,"id": "Column 1" ,"label": "Column 1" }, {"type": "number" ,"id": "Column 2" ,"label": "Publicaciones" }], "rows" : [{"c" : [{"v": "Carvallo Vega, Juan Pablo"}, {"v": 24}]}, {"c" : [{"v": "Solano Quinde, Lizandro Damián"}, {"v": 9}]}, {"c" : [{"v": "Vanegas Peña, Paúl Fernando"}, {"v": 9}]}, {"c" : [{"v": "Espinoza Molina, Daniela"}, {"v": 8}]}, {"c" : [{"v": "Baquero Larriva, Andrés Orlando"}, {"v": 7}]}, {"c" : [{"v": "Saquicela Galarza, Víctor Hugo"}, {"v": 5}]}, {"c" : [{"v": "Abril Pozo, Daniel Andrés"}, {"v": 5}]}]});
    var options = {"hAxis":{"title":"Número de publicaciones","viewWindowMode":"explicit","viewWindow":{"min":0}},"legend":{"position":"none"},"title":"Investigadores Relevantes","width":1000,"height":600}
    var chart = new google.visualization.BarChart(document.getElementById('d58646cc-a055-47d1-8d4f-d9a17025c2d1'));
    chart.draw(data, options);
}
</script>
<div id="d58646cc-a055-47d1-8d4f-d9a17025c2d1" style="width: 800px; height: 600px;"></div>

---

<table style="width:100%">
  <tr>
    <th style="width: 35%; vertical-align: middle;">
      <h4 style="text-align: center">Areas Relevantes</h4>
      <img src="images/wordcloud.png" alt="">
    </th>
    <th class="fragment" style="width: 65%">
      <h4>Areas de colaboración</h4>
      <img src="images/colaboracion.png" alt="">
    </th>
  </tr>
</table>

---


# __¿Más?__


[![](images/redi.png)](http://redi.cedia.org.ec/)

***

### Conclusiones

- Resultados están acorde a lo esperado, sin embargo, procesos como el de desambiguación y etiquetado necesitan un trabajo mas exhaustivo, debido a que aun se tienen ciertas inconsistencias en los resultados.
- Considerar que incluso para una persona es complicado determinar cierta información sobre un investigador o varios investigadores que pueden trabajar en conjunto. Por lo que aun es un reto a nivel computacional.
- Además como resultado se cuenta con un repositorio centralizado y se provee el uso de estos datos a cualquier persona.


***

### Trabajos Futuros

- Incluir el abstract para analizar redes de colaboración.
- Mejorar el proceso de etiquetado.
- Analizar nuevos algoritmos de clustering o otras técnicas para encontrar agrupaciones.

***

# CLEI 2016

![](images/clei.png)

***

![](images/cedia.png)

Agradecemos a **CEDIA** por el apoyo brindado durante el transcurso de está investigación.

***

# ¿PREGUNTAS?
