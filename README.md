# **Use of spaCy**
Este es un primer acercamiento a la librería spaCy. 
He explorado algunas de sus funcionalidades: POS y lema. 
## 🧾 Conclusiones para este Anexo 15
- Sustantivos más repetidos: proceso, validación, producto, equipo, calidad, producción, limpieza, cualificación, lote, instalación. 
- Verbos más repetidos: deber, ser, poder, estar, haber, utilizar, confirmar, incluir, considerar, cumplir. 
- Adjetivos más repetidos: documentado, utilizado, aprobado, justificado, definido, apropiado, continuo, siguiente, tradicional, necesario.
  
A falta de un análisis más preciso, aparentemente el número de sustantivos en el documento es considerablemente superior al de verbos y adjetivos. 
## 💡 Aprendizajes e intentos
### 🌱 Decidir si trabajar con el texto completo o por fragmentos (epígrafes)
Finalmente he optado por trabajar con el texto completo al no encontrar diferencias significativas en los resultados y para preservar mejor el contexto.
La división por epígrafes no ha sido del todo satisfactoria a pesar de usar regex para afinar el filtro.
### 🌱 NER (Named Entity Recognition): reconocimiento de entidades con nombre
El reconocimiento de entidades con nombre en el Anexo 15 ha sido limitado, probablemente porque el modelo está pensado para lenguaje general y no específicamente para textos técnicos.
Valoro la posibilidad de encontrar un modelo en Hugging Face que se adapte mejor a este tipo de documentos.
El modelo parece más afinado cuando se aplica sobre el texto completo que sobre fragmentos como los epígrafes.
### 🌱 Análisis del texto por palabras:
He observado que es preferible trabajar con el texto completo en lugar de fragmentado, ya que así se conserva mejor el contexto y las relaciones entre palabras.
La lematización depende de qué POS se le haya asignado a cada palabra y para un correcto etiquetaje de POS es necesario el contexto.
### 🌱 Selección del modelo de spaCy:
He usado el modelo en español es_core_news_lg al ser más completo que los modelos sm y md.
### 🌱 Separar el df por tipo de palabra
La aplicación de POS tagging no ha sido del todo precisa, hay números que se etiquetan como NOUN.
### 🌱 Simplificación del análisis
Inicialmente establecí funciones para filtrar por tipos de palabras (VERB, NOUN, ADJ, ADV) y analizar cada categoría por separado.
Finalmente me he decantado por un análisis más sencillo, mediante máscaras booleanas como filtros en lugar de funciones.
