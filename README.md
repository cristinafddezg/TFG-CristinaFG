# Análisis y Predicción del Desempeño en la ITV mediante Modelos de Aprendizaje Automático

Este Trabajo de Fin de Grado desarrolla un sistema de análisis y predicción del resultado de la Inspección Técnica de Vehículos (ITV) usando técnicas de Machine Learning. Emplea algoritmos supervisados (Árboles de Decisión, Random Forest) y no supervisados (K-Means, PCA), junto con un completo proceso de ingeniería del dato, para anticipar fallos y optimizar recursos en estaciones de ITV, talleres, fabricantes y gestores de flotas.

---

## Índice

- [Estructura del Repositorio](#estructura-del-repositorio)
- [Requisitos](#requisitos)
- [Instalación](#instalación)
- [Uso](#uso)
- [Metodología](#metodología)
- [Datos](#datos)
- [Contribuciones](#contribuciones)
- [Licencia](#licencia)
- [Contacto](#contacto)

---

## Estructura del Repositorio

```text
│── data/  
│    └── dataset_vehiculos_limpio.csv    # CSV original y limpio  
│  
│── notebooks/  
│    ├── 01_preprocesamiento.ipynb  
│    ├── 02_modelado.ipynb  
│    └── 03_visualización.ipynb  
│  
│── src/  
│    ├── preprocessing.py                # Limpieza e ingeniería del dato  
│    ├── modeling.py                     # Entrenamiento de árboles y Random Forest  
│    └── clustering.py                   # K-Means y PCA  
│  
│── README.md  
│── requirements.txt  
│── LICENSE  
```

---

## Requisitos

- Python 3.8+
- Paquetes (pip):
  - pandas
  - numpy
  - scikit-learn
  - matplotlib
  - seaborn
  - jupyter

---

## Instalación

```bash
git clone https://github.com/THEARCHERY/TFG-CristinaFG.git
cd TFG-CristinaFG
python -m venv venv
# En Windows:
venv\Scripts\activate
# En Mac/Linux:
# source venv/bin/activate
pip install -r requirements.txt
```

---

## Uso

1. **Preprocesar datos**
   ```bash
   python src/preprocessing.py --input data/dataset_vehiculos_limpio.csv --output data/processed.csv
   ```
2. **Entrenar modelos**
   ```bash
   python src/modeling.py --data data/processed.csv --model-dir models/
   ```
3. **Realizar clustering y visualizar**
   ```bash
   python src/clustering.py --data data/processed.csv --output figures/
   jupyter notebook notebooks/03_visualización.ipynb
   ```

---

## Metodología

1. **Ingeniería del dato**:

   - Limpieza de duplicados y tratamiento de valores nulos.
   - Codificación ordinal/binaria de defectos y variables categóricas.
   - Cálculo de antigüedad, total\_defectos y creación de variable objetivo `target`.

2. **Modelado supervisado**:

   - Árbol de Decisión y Random Forest para predecir resultado ITV (favorable, desfavorable, negativa).
   - Evaluación con precisión, recall y F1‐score.
   - Análisis de importancia de variables.

3. **Análisis no supervisado**:

   - K-Means sobre las variables más influyentes.
   - Reducción de dimensionalidad con PCA para visualización de clústeres.

4. **Visualización**:

   - Histogramas, boxplots, matrices de confusión, mapas de calor.

---

## Datos

- El CSV original y limpio se encuentra en `data/dataset_vehiculos_limpio.csv`.
- Fuente: Portal Dades Obertes Generalitat Valenciana (ITV 2023).

---

## Contribuciones

Las aportaciones son bienvenidas: abre un issue o realiza un pull request con mejoras en el preprocesamiento, nuevos modelos o visualizaciones.

---

## Licencia

Este proyecto usa la licencia MIT. Consulta el archivo [LICENSE](LICENSE) para detalles.

---

## Contacto

- **Autora**: Cristina Fernández Gomariz
- **Email**: [9100791@alumnos.ufv.es](mailto:9100791@alumnos.ufv.es)
- **GitHub**: [cristinafddezg](https://github.com/cristinafddezg)

