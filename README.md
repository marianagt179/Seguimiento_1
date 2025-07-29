**PUNTO 1 - DESCRIPCIÓN ARCHIVO**
----
a. Describa los campos que se encontrará en este tipo de archivos. ¿Qué información está allí contenida? Proporcione ejemplos.

De acuerdo con el link proporcionado, el formato GFF3 (General Feature Format versión 3) corresponde a un tipo de archivos utilizados para describir anotaciones de características genómicas como genes, exones o mRNAs, sobre secuencias de ADN. En este formato, cada línea (excepto los comentarios - #) representa una característica genómica (features), está dividida en 9 campos obligatorios separados por tabulación(\t). Las columnas obligatorias son:

1. seqid:identificador de la secuencia (si es cromosoma o contig). Ejemplo: chr1, NC_000001.11

2. source: fuente del dato, o el programa que generó la anotación. Ejemplo: Ensembl, RefSeq, GeneScan, maker.

3. type: tipo del feature. Tipo de característica anotada, utilizando términos del Sequence Ontology. Ejemplo: gene, mRNA, exon, CDS.

4. start: posición de inicio del feature. Ejemplo: 1050

5. end: posición final del feature. Ejemplo: 1500

6. score: puntaje del feature (por ejemplo, valor de confianza del alineamiento). Si no aplica, se usa un punto (.). Ejemplo: 960, (.).

7. strand: hebra en la que se encuentra la característica: (+) para hebra directa, (-) para hebra complementaria, (.) si no aplica.

8. phase: esta columna solo se aplica en features de tipo CDS (Coding DNA Sequence). Indica desde qué base del fragmento de CDS comienza el siguiente codón. El valor de phase puede ser 0, 1 o 2, y cada uno indica cuántas bases deben saltarse desde el inicio del fragmento actual de CDS para comenzar el siguiente codón completo. (0) indica el codón empieza en esa posición, (1)  1 base queda al final del codón anterior y (2) 2 bases quedan al final del codón anterior, también se usa (.) si no aplica.
IMPORTANTE: El campo phase es obligatorio para todas las líneas tipo CDS en un archivo GFF3.

9. attributes: campo con información adicional, en formato clave=valor, separadas por (;). 

**Ejemplo:**

chrIV	SGD	gene	5000	6500	.	+	.	ID=YDL248W;Name=COS7;gene_biotype=protein_coding

En este caso, se indica que en el cromosoma IV, desde la base número 5000 hasta la 6500 en la hebra positiva, se encuentra un gen anotado por la base de datos SGD. No tiene un score ni phase porque no es una región codificante. En la sección de atributos se especifica que el ID del gen es YDL248W, su nombre simbólico es COS7, y que es un gen codificante de proteína. 

**PUNTO 2 - DESCARGA DE ARCHIVOS DE TRABAJO**
Para descargar y descomprimir el archivo de trabajo se utilizaron los comandos especificados en el archivo con formato (.txt).
----
**PUNTO 3 - ANÁLISIS DEL ARCHIVO**
----
**a.** Proporcione una breve descripción del organismo asignado en el archivo README.

El archivo analizado corresponde al genoma de *Poecilia reticulata*, comúnmente conocido como guppy, en su versión de ensamblaje Guppy_female_1.0_MT.114. Es un pez de agua dulce muy popular en acuarios, conocido por su dimorfismo sexual, donde los machos son más pequeños y coloridos, mientras que las hembras son más grandes y de colores más apagados. Estos peces tienen un ciclo reproductivo muy rápido, son  ovovivíparos y han sido utilizados extensamente en estudios de genética, ecología y evolución por su variabilidad genética, su selección sexual y su adaptabilidad a distintos ambientes. El guppy es originario de América del Sur, aunque ha sido introducido en numerosos ecosistemas y hoy en día se encuentra en todo el mundo. 

**b.** Investigue, usando las herramientas de la línea de comandos de Unix, y conteste las siguientes preguntas:

**i. ¿Cuantos features contiene el archivo?**

Con la línea de comandos se obtuvieron **823.834 features**, lo cual significa que se han identificado y descrito 823.834 elementos genómicos individuales en el ensamblaje del genoma del guppy.

**ii. ¿Cuantas regiones de la secuencia (cromosomas) contiene el archivo?**

De acuerdo al análisis, el archivo contiene 23 regiones de secuencia correspondientes a grupos de ligamiento (LG) anotados en el genoma de *Poecilia reticulata*. 

Los grupos de ligamiento (Linkage Groups, LG) son equivalentes a cromosomas o segmentos cromosómicos que han sido definidos con base en estudios genéticos y de ensamblaje. Además, en los archivos genómicos se encuentran otras regiones que no corresponden a cromosomas.

Se tienen entonces, los contigs (secuencias pequeñas) suelen tener nombres genéricos como contig00123, NW_012345, o también pueden aparecer scaffolds, los cuales son secuencias más grandes formadas al unir contigs que pueden parecer como scaffold_567.

Las 23 regiones encontradas son coherentes con lo encontrado en la literatura para esta especie, cuyo cariotipo diploide incluye 23 pares de cromosomas (2n = 46) de acuerdo con el NIH. 

**iii. ¿Cuántos genes están listados en el organismo?**

Al analizar el archivo, se encontró la presencia de 22,871 genes anotados en el genoma de **Poecilia reticulata**. Esta cifra representa las unidades funcionales codificantes identificadas en el ensamblaje.

**iv. 4. ¿Cuál es el top 10 de tipo de features (columna 3) más anotados en el genoma?**

363572 exon

360300 CDS

34333 mRNA

22871 gene

21399 biological_region

10196 five_prime_UTR

7615 three_prime_UTR

2768 region

358 ncRNA_gene

169 snoRNA