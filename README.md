
# Análisis Filogenético de Genes Relacionados con Funciones Esenciales en Mamíferos

Este proyecto consiste en la construcción de un árbol filogenético basado en secuencias génicas reales provenientes de diferentes especies de mamíferos. La selección de los genes se realizó considerando su relevancia biológica: *TLR4* (receptor de reconocimiento inmune), *BRCA1* (supresor tumoral relacionado con cáncer de mama) y *ACTB* (gen de la beta-actina, comúnmente utilizado como control de expresión). 

La finalidad de este trabajo es entender cómo estas secuencias evolucionaron entre diferentes organismos, utilizando herramientas bioinformáticas para el alineamiento y posterior inferencia filogenética.

Este repositorio cumple con el objetivo del curso de proporcionar un programa que:
- Reciba un archivo FASTA como entrada.
- Genere un alineamiento múltiple de secuencias.
- Construya un árbol filogenético como salida.

Todo el programa fue diseñado para correr en el supercomputador **Hoffman2**, siguiendo las buenas prácticas de estructuración de proyectos bioinformáticos.

---

## Estructura del Repositorio

```

FINALPROYECT/
├── Data/
│   └── genes.fasta               # Secuencias reales en formato FASTA
├── Scripts/
│   └── run\_pipeline.sh           # Script ejecutable en Hoffman2
├── Results/
│   └── genes\_aligned.fasta       # Alineamiento generado con MUSCLE
│   └── genes\_aligned.fasta.treefile  # Árbol filogenético generado con IQ-TREE
└── README.md                     # Documento actual con explicación del proyecto

````

---

## Requisitos

Para ejecutar el proyecto se requiere tener instaladas en el entorno de trabajo (como Hoffman2) las siguientes herramientas:

- [MUSCLE](https://www.drive5.com/muscle/) para alineamiento múltiple de secuencias.
- [IQ-TREE](http://www.iqtree.org/) para inferencia filogenética.
- Bash shell.

---

## Ejecución del Programa

Una vez dentro del directorio `FINALPROYECT`, simplemente ejecuta el script:

```bash
bash Scripts/run_pipeline.sh
````

Este comando tomará el archivo `genes.fasta` desde la carpeta `Data/`, lo alineará con MUSCLE y luego generará un árbol filogenético con IQ-TREE. Los resultados se guardarán automáticamente en la carpeta `Results/`.

---

## Justificación Biológica

Este proyecto fue desarrollado por **Carolina Pumalema** como parte de la asignatura de bioinformática. Se seleccionaron los genes *TLR4*, *BRCA1* y *ACTB* por su papel esencial en funciones inmunológicas, celulares y tumorales, respectivamente. Estas secuencias permiten inferencias evolutivas entre especies distintas y proporcionan una base sólida para comprender procesos de conservación genética y divergencia.

El análisis filogenético es una herramienta fundamental en biología evolutiva, y mediante este ejercicio se aplican conceptos teóricos a herramientas computacionales reales, permitiendo consolidar conocimientos prácticos y técnicos en bioinformática.

---

## Créditos

* **Carolina Pumalema** – estudiante responsable del desarrollo del proyecto
* Curso de Bioinformática – Pontificia Universidad Católica del Ecuador
* Profesor: Daniel Chávez

---

## Licencia

Este proyecto fue desarrollado con fines académicos y puede ser reutilizado citando la fuente.


