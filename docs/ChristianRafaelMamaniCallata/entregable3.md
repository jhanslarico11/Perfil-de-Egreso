# CE0121-CE0125 - Entregable 3: Plan de Gestión del Proyecto

## 1. Descripción
El presente entregable detalla el **Plan de Gestión del Proyecto** para **YatiqApp** bajo un enfoque híbrido de gestión. Combina las metodologías predictivas (PMI/PMBOK) para el control riguroso del alcance, cronograma y presupuesto, con prácticas ágiles (Scrum) para la ingeniería del software y la optimización de la Inteligencia Artificial (STT/TTS local y RAG offline). Se incluye el Project Charter, la WBS (EDT), el cronograma detallado, Gantt, presupuesto por rubros y plan de riesgos.

## 2. Plantilla del Producto

### Portada
* **Título del Proyecto:** YatiqApp
* **Línea de Evaluación:** CE01: Gestión de Tecnologías de Información
* **Entregable:** CE0125 - Entregable 3: Plan de Gestión del Proyecto
* **Responsable:** Christian Rafael Mamani Callata

### Resumen Ejecutivo
Este informe presenta el plan de gestión del proyecto **YatiqApp** para el desarrollo de un asistente educativo bilingüe e interactivo offline. Utilizando un enfoque híbrido, se establecen los mecanismos de control predictivo (PMI) para las restricciones del proyecto (alcance delimitado a la app Android, plazo fijo de 7 meses y presupuesto de S/. 18,500.00 autofinanciado) y metodologías ágiles (Scrum) organizadas en 4 Sprints de dos semanas para la optimización de los algoritmos de IA en el borde.

La Estructura de Desglose del Trabajo (EDT) organiza las fases clave de ingesta del corpus lingüístico, cuantización de modelos, desarrollo nativo móvil y validación en campo. El cronograma estima la entrega del Mínimo Producto Viable (MVP) y las pruebas de campo en escuelas rurales de Puno en la semana 26. El plan de costos proyecta la curva de gasto acumulado (Curva S) con picos en la fase de cuantización y hardware móvil de prueba, mientras que el plan de riesgos formula estrategias concretas de mitigación frente a fallos de procesamiento de audio en teléfonos de gama baja y alucinaciones lingüísticas.

### Secciones de Desarrollo

#### I. Project Charter (Acta de Constitución del Proyecto)

##### 1.1. Sponsor e Interesados Clave
* **Sponsor del Proyecto:** Equipo de Tesistas / Desarrolladores (Autofinanciado).
* **Asesor Metodológico/Técnico:** Docente de la Carrera de Ingeniería de Sistemas.
* **Usuarios / Beneficiarios:** Estudiantes, docentes de Instituciones Educativas EIB y especialistas de las UGELs de la región Puno.

##### 1.2. Objetivos del Proyecto
* **Objetivo Técnico:** Lograr la inferencia local de un Modelo de Lenguaje Pequeño (SLM) cuantizado a 4 bits con una latencia inferior a $2.5\text{ s}$ en un smartphone estándar de gama baja/media.
* **Objetivo de Gestión:** Entregar el producto de software (APK), el dataset bilingüe estructurado y el informe de tesis aprobado en un periodo de 7 meses, respetando el presupuesto asignado por el equipo.

##### 1.3. Alcance Preliminar
El proyecto abarca el diseño, entrenamiento por RAG, cuantización, desarrollo de la aplicación móvil Android y validación en campo de un asistente virtual offline bilingüe para educación primaria rural. Queda fuera del alcance el desarrollo para sistemas operativos iOS, la provisión física de smartphones a las escuelas y la actualización curricular de los contenidos del MINEDU.

##### 1.4. Restricciones y Supuestos
* **Restricciones:** Presupuesto limitado por autofinanciación (máximo $\text{S/. 18,500.00}$), plazo estricto de entrega por calendario académico (7 meses) y el software debe operar en hardware móvil con $\le 4\text{ GB}$ de RAM sin conexión a internet.
* **Supuestos:** Acceso oportuno a los textos escolares del MINEDU en Quechua Collao y Aymara, y viabilidad para ingresar a las comunidades piloto en Puno para las pruebas de campo.

---

#### II. Gestión del Alcance

##### 2.1. Estructura de Desglose del Trabajo (EDT / WBS)
La EDT se organiza en 5 componentes principales del ciclo de vida del proyecto:
```
1.0 ASISTENTE INTELIGENTE OFFLINE (EIB-PUNO)
   ├── 1.1 Ingesta y Gestión de Datos (Corpus)
   │     ├── 1.1.1 Recopilación de textos oficiales MINEDU (Quechua/Aymara)
   │     └── 1.1.2 Limpieza, Tokenización y Formateo de Data
   ├── 1.2 Ingeniería de IA y Optimización
   │     ├── 1.2.1 Configuración de Embeddings y Base Vectorial Local
   │     └── 1.2.2 Cuantización del SLM a 4 bits (GGUF/Nativo)
   ├── 1.3 Desarrollo de Software Móvil (Android)
   │     ├── 1.3.1 Arquitectura del Motor de Inferencia local (C++/Bindings)
   │     ├── 1.3.2 Implementación de Módulos de Voz (STT/TTS)
   │     └── 1.3.3 Diseño de Interfaz de Usuario Gamificada (UI/UX)
   ├── 1.4 Pruebas, Despliegue y Validación
   │     ├── 1.4.1 Pruebas de estrés de Hardware (RAM/Batería)
   │     └── 1.4.2 Prueba Piloto en Comunidad Rural de Puno
   └── 1.5 Gestión del Proyecto y Tesis
         ├── 1.5.1 Redacción del Perfil e Informe Final de Tesis
         └── 1.5.2 Sustentación y Aprobación
```

##### 2.2. Diccionario de Entregables Críticos
* **Paquete 1.1.2 (Dataset Estructurado):** Archivos en formato JSON/Markdown con el contenido pedagógico indexado y alineado bilingüemente.
* **Paquete 1.2.2 (Modelo SLM Optimizado):** Archivo binario del modelo cuantizado comprimido a menos de $1.8\text{ GB}$ listo para la inferencia local.
* **Paquete 1.3.3 (Aplicación Móvil - APK):** Instalable nativo de Android que empaqueta la interfaz, la base de datos vectorial y el motor de IA.

---

#### III. Gestión del Cronograma

##### 3.1. Lista de Actividades e Hitos Principales
El proyecto tiene una duración total de 28 semanas (7 meses).

| ID Actividad | Descripción de la Actividad | Predecesora | Duración (Semanas) |
| :---: | :--- | :---: | :---: |
| **A1** | Recopilación y estructuración de datos EIB | — | 4 |
| **A2** | Indexación en Base de Datos Vectorial Embebida | A1 | 3 |
| **A3** | Selección, Ajuste y Cuantización del Modelo SLM | A1 | 5 |
| **A4** | Integración del motor de inferencia nativo en App | A2, A3 | 4 |
| **A5** | Desarrollo de módulos locales de voz (STT/TTS) y UI | A4 | 5 |
| **A6** | Pruebas integrales de software y consumo de RAM | A5 | 3 |
| **A7** | Despliegue piloto en campo (Puno) y validación | A6 | 2 |
| **A8** | Redacción final de tesis y trámites académicos | A7 | 2 |

* **Hito 1 (Semana 4):** Base de conocimientos bilingüe digitalizada y validada.
* **Hito 2 (Semana 12):** Modelo de IA cuantizado corriendo localmente en entorno de pruebas.
* **Hito 3 (Semana 21):** Aplicación móvil (APK) con soporte de voz e interfaz terminada.
* **Hito 4 (Semana 26):** Pruebas de campo concluidas con éxito en la escuela rural.

##### 3.2. Diagrama de Gantt (Representación Temporal)
```
Semanas:                 |02|04|06|08|10|12|14|16|18|20|22|24|26|28|
A1: Corpus               [====]★ (Hito 1)
A2: VectDB                    [===]
A3: SLM/IA               [=====]★ (Hito 2)
A4: Motor-Inference            [====]
A5: App/STT/TTS                     [=====]★ (Hito 3)
A6: QA-RAM                                [===]
A7: Piloto                                     [==]★ (Hito 4)
A8: Tesis Final                                   [==]✔ (Fin)
```

---

#### IV. Gestión de Costos

##### 4.1. Presupuesto Detallado de TI (Financiado por el Equipo)

| Ítem | Descripción Recurso | Unidad | Cant. | Total (PEN) |
| :---: | :--- | :---: | :---: | :---: |
| **1.0** | **Hardware e Infraestructura de TI** | | | |
| 1.1 | GPU Workstation (Alquiler/Depreciación) | Global | 1 | S/. 4,500.00 |
| 1.2 | Cloud Computing (Compute Credits Fine-Tuning) | Global | 1 | S/. 2,000.00 |
| **2.0** | **Ingeniería y Trabajo de Campo** | | | |
| 2.1 | Viáticos y Movilidad Rural (Puno) | Ruta | 3 | S/. 1,500.00 |
| 2.2 | Dispositivos móviles de prueba | Unid | 2 | S/. 1,600.00 |
| **3.0** | **Gestión y Recursos Humanos** | | | |
| 3.1 | Horas de Desarrollo de Software (Valor estimado de mano de obra propia) | Meses | 7 | S/. 8,900.00 |
| **Total**| **Costo Total Estimado** | | | **S/. 18,500.00** |

##### 4.2. Línea Base de Costos (Curva S Proyectada por Mes)
El gasto acumulado planeado a lo largo de los 7 meses de ejecución del proyecto sigue la siguiente distribución financiera:
* **Mes 1 - 2 (Inicio e Ingesta de Data):** $\text{S/. 3,500.00}$ (Incurre en setup inicial y recolección).
* **Mes 3 - 4 (Ingeniería de IA y Servidores):** $\text{S/. 10,000.00}$ acumulados (Pico alto por entrenamiento, cómputo cloud y compra de móviles de testeo).
* **Mes 5 - 6 (Desarrollo Móvil y QA):** $\text{S/. 16,500.00}$ acumulados (Desarrollo intensivo del cliente Android).
* **Mes 7 (Cierre, Pruebas de Campo y Tesis):** $\text{S/. 18,500.00}$ acumulados (Validación final e impresión).

---

#### V. Gestión de Riesgos

##### 5.1. Identificación y Análisis Cualitativo
* **Riesgo 1: Alucinación Crítica del Modelo (Probabilidad: Media \| Impacto: Alto):** El modelo entrega conceptos educativos erróneos o alucina temas no cubiertos en las lecciones.
* **Riesgo 2: Cuello de botella en STT/TTS local (Probabilidad: Alta \| Impacto: Medio):** El hardware móvil de gama baja se congela o tiene altas latencias al intentar procesar el audio local.
* **Riesgo 3: Descoordinación con Comunidades Locales (Probabilidad: Baja \| Impacto: Alto):** Huelgas, bloqueos de vías o rechazo de los padres impiden el ingreso de los tesistas para realizar las pruebas de campo.

##### 5.2. Plan de Respuesta a Riesgos
* **Para Riesgo 1 (Mitigación):** Inyección forzada de contexto mediante programación determinista de la base vectorial. Si la consulta del niño no coincide con el contenido educativo indexado, el modelo ejecuta un fallback controlado: "No tengo esa información en mi base local".
* **Para Riesgo 2 (Mitigación):** Utilizar modelos Whisper optimizados en formato de bajo peso (Tiny o Base quantized) y restringir el muestreo de audio a fragmentos de máximo $5\text{ segundos}$.
* **Para Riesgo 3 (Contingencia):** Establecer nexos institucionales con directores de escuelas rurales de zonas cercanas accesibles por vías alternas como plan de respaldo para las pruebas del piloto.

---

#### VI. Gestión Ágil (Aplica para las Fases 2 y 3: Construcción de Software)
El ciclo de desarrollo core del backend de IA y de la app móvil se gestionará bajo el framework Scrum, organizando el trabajo en Sprints de 2 semanas.

##### 6.1. Product Backlog Inicial (Historias de Usuario Críticas)
* **HU01:** Como estudiante rural, quiero interactuar con el asistente usando comandos de voz en Quechua/Aymara para que la falta de escritura fluida no frene mi aprendizaje.
* **HU02:** Como docente de la escuela, quiero que la aplicación funcione en mi celular sin necesidad de conectarme a una red móvil o Wi-Fi para usarla dentro del aula aislada.
* **HU03:** Como administrador del sistema (tesista), quiero compilar el contenido del MINEDU en vectores dentro de una base local para controlar que las respuestas de la IA sean correctas.

##### 6.2. Sprint Planning y Estructura de Incrementos
* **Sprint 1 - IA Core:** Procesamiento del corpus bilingüe, generación del almacén de vectores y configuración inicial del SLM base.
* **Sprint 2 - Cuantización:** Compresión del modelo a 4 bits y validación de la inferencia matemática en la estación local.
* **Sprint 3 - App Bridge:** Configuración del proyecto móvil (Flutter/Native) y linking de las librerías nativas C++ para correr el binario del modelo.
* **Sprint 4 - Voice & UI:** Integración de los modelos Whisper Tiny / TTS locales y diseño de las pantallas interactivas para los niños.
* **Incremento de Producto Esperado (Mínimo Producto Viable - MVP):** Al finalizar el Sprint 4, el equipo dispondrá de un archivo `.apk` compilado y estable, capaz de ejecutarse en frío dentro de un dispositivo Android de pruebas, procesar una pregunta por voz en lengua originaria, buscar la respuesta semánticamente en su base local y reproducir la respuesta mediante audio, todo sin emitir un solo byte de datos a internet.

### Anexos
*(En los siguientes entregables se integrarán diagramas arquitectónicos y capturas de pantalla de la solución móvil)*

## 3. Rúbrica de Evaluación
El presente entregable ha sido elaborado considerando las siguientes competencias del perfil de egreso:
- **CE01 (Gestión de Tecnologías de Información):** Capacidad para planificar y gestionar proyectos de TI con un enfoque híbrido, estableciendo la EDT (WBS), estimando el cronograma y presupuesto mediante líneas base (Curva S) y diseñando iteraciones ágiles de software.
- **Criterios de Evaluación:** Rigurosidad en la descomposición de la EDT, consistencia lógica en el cronograma con hitos de desarrollo, planeamiento de la Curva S de costos y especificación de la estructura Scrum para la construcción del producto.