# Análisis Filogenético de Genes Relacionados con Funciones Esenciales en Mamíferos

Este proyecto consiste en la construcción de un árbol filogenético a partir de secuencias génicas reales provenientes de diferentes especies de mamíferos. Se seleccionaron cuatro genes con funciones esenciales y complementarias:  
- *ACTB* (actina beta, marcador estructural y de referencia en expresión génica),  
- *BRCA1* (supresor tumoral involucrado en el cáncer de mama),  
- *GAPDH* (enzima clave en la glicólisis, comúnmente usada como gen de referencia),  
- *TLR4* (receptor tipo Toll, implicado en la respuesta inmune innata).  

El propósito de este análisis es explorar la evolución molecular de estos genes entre especies, usando herramientas bioinformáticas para su alineamiento múltiple y posterior inferencia filogenética.

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
│   └── genes.fasta                  # Archivo combinado de todos los genes
├── Results/
│   ├── genes\_aligned.fasta         # Alineamiento generado con MUSCLE
│   ├── genes\_aligned.fasta.treefile # Árbol filogenético generado con IQ-TREE
│   └── ...                         # Otros archivos auxiliares de IQ-TREE
├── Scripts/
│   └── pipeline\_filogenia.sh       # Script ejecutable en Hoffman2
├── muscle3.8.31\_i86linux64         # Binario de MUSCLE
└── README.md                       # Este documento

````

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
````

El script realiza los siguientes pasos:

1. Concatena los archivos `.fasta` de la carpeta `Data/` en uno solo (`genes.fasta`).
2. Ejecuta MUSCLE para obtener el alineamiento múltiple.
3. Corre IQ-TREE para inferir el árbol filogenético.
4. Mueve los resultados generados a la carpeta `Results/`.

Ejemplo de filogenia que se obtiene mediante el script:

![Captura de pantalla 2025-07-09 174703](https://github.com/user-attachments/assets/59907f67-452c-47a0-ab43-a4cc00a7fdf6)

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

```

--- 

Si necesitas que el `README.md` se guarde como archivo y lo subamos directamente a GitHub o por consola, dime y te ayudo con eso también.
```



