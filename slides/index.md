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

### Data Extraction
<div style="text-align: justify; text-align: center;">Datos extraidos</div>
<p><img src="images/correctPublicationsSource.png" alt=""></p>

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
#### Modelo de datos

<div style="font-size: 80%;">El modelo de datos basado en la ontología BIBO.</div>

<div style="width:80%;height:75%;margin: auto;">
<p><img src="images/dataModelCommon.png" alt=""></p>
</div>

---

### Data Enrichment
#### Mapeo del modelo de datos

<div style="font-size: 80%;">El modelo de datos de cada fuente es diferente, por lo cual se realiza un mapeo de la fuente al modelo de datos común y se almacena en el repositorio central.</div>


<div style="width:80%;height:60%;margin: auto;">
<p><img src="images/grafos.png" alt=""></p>
</div>

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


### Data Enrichment
#### Desambiguación de información.
<div style="font-size: 80%;">Indice de similaridad entre recursos bibliográfico.</div>
<div style="width:120%;height:150%;">
<p><img src="images/similaridad.png" alt=""></p>
</div>

---

### Pattern Detection
#### Proceso para la extracción de conocimiento

![](images/pdetection.png)

*Find groups* detectar patrones de los datos almacenados en el repositorio central.

*Knowledge Discovery* asociar patrones a un formato legible por un humano. Se descubre redes de colaboracón y áreas de
conocimiento.

*Label Groups* Se encuentra una etiqueta para cada cluster, ayuda a acelerar consultar y mantener la información
organizada en el repositorio.

---

### Pattern Detection
#### Extracto de resultados obtenidos

![](images/redes.png)

e debe tener en cuenta que para mejorar la calidad de los resultados, se debe mejorar la calidad de los datos de las diferentes **bases bibliográficas** para obtener aún mejores resultados.

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

__¿Mas información?__

[http://redi.cedia.org.ec/](http://redi.cedia.org.ec/)

***

![](images/cedia.png)

Agradecemos a **CEDIA** por el apoyo brindado durante el transcurso de está investigación.

***

# ¿PREGUNTAS?
