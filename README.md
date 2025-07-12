# Análisis Filogenético de Genes Relacionados con Funciones Esenciales en Mamíferos

Este proyecto consiste en la construcción de un árbol filogenético a partir de secuencias génicas reales provenientes de diferentes especies de mamíferos. Se seleccionaron cuatro genes con funciones esenciales y complementarias:  
- *ACTB* (actina beta, marcador estructural y de referencia en expresión génica),  
- *BRCA1* (supresor tumoral involucrado en el cáncer de mama),  
- *GAPDH* (enzima clave en la glicólisis, comúnmente usada como gen de referencia),  
- *TLR4* (receptor tipo Toll, implicado en la respuesta inmune innata).  

Además, se añadió una secuencia de chimpancé para uno de los genes, con el fin de comparar su divergencia y analizar la relación evolutiva entre ambos primates.

El propósito de este análisis es explorar la evolución molecular de estos genes en humanos y su comparación con otra especie cercana, usando herramientas bioinformáticas para su alineamiento múltiple y posterior inferencia filogenética.

Este repositorio cumple con los objetivos del curso de proporcionar un pipeline que:
- Reciba múltiples archivos en formato FASTA como entrada.
- Genere un alineamiento múltiple de secuencias.
- Construya un árbol filogenético como resultado.

Todo el proyecto fue desarrollado para ejecutarse en el supercomputador **Hoffman2**, respetando las buenas prácticas de estructuración en proyectos bioinformáticos.

---

## Estructura del Repositorio

```
FINALPROYECT/
├── Data/
│   ├── ACTB.fasta
│   ├── BRCA1.fasta
│   ├── GAPDH.fasta
│   ├── TLR4.fasta
│   ├── BRCA1_Pan_troglodytes.fasta   # BRCA1 de chimpancé
│   └── genes.fasta                   # Archivo combinado
├── Results/
│   ├── genes_aligned.fasta           # Alineamiento generado con MUSCLE
│   ├── genes_aligned.fasta.treefile # Árbol filogenético generado con IQ-TREE
│   └── ...                           # Otros archivos auxiliares
├── Scripts/
│   └── pipeline_filogenia.sh         # Script principal
├── muscle3.8.31_i86linux64           # Binario de MUSCLE
└── README.md                         # Este documento
```

---

## Requisitos

Para ejecutar el pipeline en un entorno como Hoffman2 se requiere tener instalados:

- [MUSCLE](https://www.drive5.com/muscle/) – Para alineamiento múltiple de secuencias.
- [IQ-TREE](http://www.iqtree.org/) – Para inferencia filogenética.
- Bash shell (Linux).

---

## Ejecución del Pipeline

Desde el directorio raíz `FINALPROYECT`, ejecutar:

```bash
bash Scripts/pipeline_filogenia.sh
```

El script realiza los siguientes pasos:

1. Concatena los archivos `.fasta` de la carpeta `Data/` en uno solo (`genes.fasta`).
2. Ejecuta MUSCLE para obtener el alineamiento múltiple.
3. Corre IQ-TREE para inferir el árbol filogenético.
4. Mueve los resultados generados a la carpeta `Results/`.

---

## Resultados

El alineamiento múltiple evidencia regiones altamente conservadas entre las secuencias de los genes seleccionados. Esto es especialmente evidente en genes como *ACTB* y *GAPDH*, que tienen funciones celulares esenciales y por tanto están bajo fuerte presión evolutiva para mantener su estructura y función.

En contraste, *TLR4*, que participa en la detección de patógenos por parte del sistema inmune, presenta regiones con mayor variabilidad. Esta diferencia refleja su necesidad de adaptarse a una diversidad de amenazas biológicas, lo que genera una evolución más rápida en ciertas regiones del gen.

El árbol filogenético generado por IQ-TREE muestra cómo las secuencias humanas agrupan de manera esperada, y destaca la posición diferenciada del gen *BRCA1* del chimpancé. Este patrón filogenético refleja la cercanía evolutiva entre ambas especies, pero también permite observar la divergencia acumulada a lo largo del tiempo evolutivo en genes específicos.

### Interpretación biológica del árbol:

- **Ramas cortas** entre secuencias humanas sugieren alta similitud genética, lo cual es esperable ya que todas provienen de la misma especie.
- **Una rama separada** para la secuencia de chimpancé indica una divergencia que, aunque pequeña, es medible y relevante para análisis evolutivos.
- **Soportes de rama (bootstrap)** generados por IQ-TREE ayudan a validar la solidez de cada agrupación. Valores altos indican confianza en la relación representada.

Este tipo de análisis puede ser útil para:
- Inferir relaciones evolutivas entre especies.
- Estudiar la conservación funcional de genes esenciales.
- Identificar posibles regiones sujetas a selección positiva o negativa.

Ejemplo del árbol generado:

![genes_tree treefile](https://github.com/user-attachments/assets/5a9ab8f8-d65c-4db7-971b-850a6bb5b9f6)

---

## Justificación Biológica

Este trabajo fue desarrollado por **Carolina Pumalema** como parte del curso de Bioinformática. La elección de *ACTB*, *BRCA1*, *GAPDH* y *TLR4* responde a su rol esencial en procesos celulares clave como estructura, metabolismo, reparación de ADN y defensa inmunitaria. Analizar su evolución permite comprender patrones de conservación y divergencia entre especies, aportando a estudios comparativos y evolutivos.

Mediante esta actividad, se integran habilidades en análisis de secuencias, manejo de herramientas bioinformáticas, scripting y estructuración de proyectos reproducibles.

---

## Autora

* **Carolina Pumalema** – Estudiante responsable del desarrollo del proyecto  
* Curso de Bioinformática – Pontificia Universidad Católica del Ecuador  
* Profesor: **Daniel Chávez**

---

## Licencia

Este proyecto fue desarrollado con fines académicos. Su uso está permitido con el debido reconocimiento.
