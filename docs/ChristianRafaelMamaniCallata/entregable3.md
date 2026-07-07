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
Este informe presenta el plan de gestión del proyecto **YatiqApp** para el desarrollo de un prototipo educativo bilingüe e interactivo offline. Utilizando un enfoque híbrido, se establecen mecanismos de control predictivo para el alcance, cronograma y presupuesto, junto con prácticas ágiles organizadas en 4 iteraciones de dos semanas para construir, probar y ajustar la solución en condiciones rurales.

La Estructura de Desglose del Trabajo (EDT) organiza las fases clave de curación del corpus lingüístico, configuración RAG local, desarrollo móvil y validación en campo. El cronograma estima la entrega del Mínimo Producto Viable (MVP) en la semana 8. El plan de costos proyecta una inversión máxima de S/. 3,500.00, coherente con un proyecto rural autofinanciado que reutiliza celulares, herramientas libres y recursos educativos existentes.

### Secciones de Desarrollo

#### I. Project Charter (Acta de Constitución del Proyecto)

##### 1.1. Sponsor e Interesados Clave
* **Sponsor del Proyecto:** Equipo de Tesistas / Desarrolladores (Autofinanciado).
* **Asesor Metodológico/Técnico:** Docente de la Carrera de Ingeniería de Sistemas.
* **Usuarios / Beneficiarios:** Estudiantes, docentes de Instituciones Educativas EIB y especialistas de las UGELs de la región Puno.

##### 1.2. Objetivos del Proyecto
* **Objetivo Técnico:** Lograr la inferencia local de un Modelo de Lenguaje Pequeño (SLM) cuantizado a 4 bits con una latencia inferior a 2.5 s en un smartphone estándar de gama baja/media.
* **Objetivo de Gestión:** Entregar el prototipo de software (APK), el dataset bilingüe estructurado y el informe técnico en un periodo de 2 meses, respetando el presupuesto asignado por el equipo.

##### 1.3. Alcance Preliminar
El proyecto abarca el diseño, entrenamiento por RAG, cuantización, desarrollo de la aplicación móvil Android y validación en campo de un asistente virtual offline bilingüe para educación primaria rural. Queda fuera del alcance el desarrollo para sistemas operativos iOS, la provisión física de smartphones a las escuelas y la actualización curricular de los contenidos del MINEDU.

##### 1.4. Restricciones y Supuestos
* **Restricciones:** Presupuesto limitado por autofinanciación (máximo S/. 3,500.00), plazo estricto de entrega por calendario académico (2 meses) y el software debe operar en hardware móvil con <= 4 GB de RAM sin conexión a internet.
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
* **Paquete 1.2.2 (Modelo SLM Optimizado):** Archivo binario del modelo cuantizado comprimido a menos de 1.8 GB listo para la inferencia local.
* **Paquete 1.3.3 (Aplicación Móvil - APK):** Instalable nativo de Android que empaqueta la interfaz, la base de datos vectorial y el motor de IA.

---

#### III. Gestión del Cronograma

##### 3.1. Lista de Actividades e Hitos Principales
El proyecto tiene una duración total de 8 semanas (2 meses).

| ID Actividad | Descripción de la Actividad | Predecesora | Duración (Semanas) |
| :---: | :--- | :---: | :---: |
| **A1** | Curación y estructuración de contenidos EIB | — | 2 |
| **A2** | Configuración de base local y recuperación RAG | A1 | 2 |
| **A3** | Selección de modelo liviano y pruebas de respuesta | A1 | 2 |
| **A4** | Desarrollo del prototipo móvil Android | A2, A3 | 2 |
| **A5** | Pruebas de rendimiento en celulares de gama baja | A4 | 2 |
| **A6** | Piloto rural básico y ajustes finales | A5 | 2 |
| **A7** | Documentación técnica y presentación académica | A6 | 1 |

* **Hito 1 (Semana 2):** Base de conocimientos bilingüe organizada y validada.
* **Hito 2 (Semana 4):** Motor RAG local funcionando con consultas básicas.
* **Hito 3 (Semana 6):** Aplicación móvil (APK) instalada en celulares de prueba.
* **Hito 4 (Semana 8):** Piloto rural básico concluido y versión final documentada.

##### 3.2. Diagrama de Gantt (Representación Temporal)
| Actividad | S1 | S2 | S3 | S4 | S5 | S6 | S7 | S8 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| A1: Contenidos EIB | X | X |  |  |  |  |  |  |
| A2: Base local/RAG |  | X | X | X |  |  |  |  |
| A3: Modelo liviano |  |  | X | X |  |  |  |  |
| A4: Prototipo móvil |  |  |  | X | X | X |  |  |
| A5: Pruebas en celulares |  |  |  |  | X | X | X |  |
| A6: Piloto rural |  |  |  |  |  |  | X | X |
| A7: Documentación final |  |  |  |  |  |  |  | X |

---

#### IV. Gestión de Costos

##### 4.1. Presupuesto Detallado de TI (Financiado por el Equipo)

| Ítem | Descripción Recurso | Unidad | Cant. | Total (PEN) |
| :---: | :--- | :---: | :---: | :---: |
| **1.0** | **Hardware e Infraestructura de TI** | | | |
| 1.1 | Uso de laptop/equipo propio y herramientas libres | Global | 1 | S/. 0.00 |
| 1.2 | Almacenamiento, energía y conectividad puntual para descargas | Global | 1 | S/. 450.00 |
| **2.0** | **Ingeniería y Trabajo de Campo** | | | |
| 2.1 | Curación de contenidos y validación con docentes | Global | 1 | S/. 600.00 |
| 2.2 | Accesorios y pruebas en celulares disponibles | Global | 1 | S/. 850.00 |
| 2.3 | Viáticos y movilidad rural local | Ruta | 2 | S/. 600.00 |
| **3.0** | **Gestión y Recursos Humanos** | | | |
| 3.1 | Desarrollo de software y documentación (valor estimado de mano de obra propia) | Meses | 2 | S/. 1,000.00 |
| **Total**| **Costo Total Estimado** | | | **S/. 3,500.00** |

##### 4.2. Línea Base de Costos (Curva S Proyectada por Mes)
El gasto acumulado planeado a lo largo de los 2 meses de ejecución del proyecto sigue la siguiente distribución financiera:
* **Mes 1 (Curación, base local y configuración RAG):** S/. 1,450.00 acumulados.
* **Mes 2 (Prototipo móvil, piloto rural y documentación):** S/. 3,500.00 acumulados.

---

#### V. Gestión de Riesgos

##### 5.1. Identificación y Análisis Cualitativo
* **Riesgo 1: Alucinación Crítica del Modelo (Probabilidad: Media \| Impacto: Alto):** El modelo entrega conceptos educativos erróneos o alucina temas no cubiertos en las lecciones.
* **Riesgo 2: Cuello de botella en STT/TTS local (Probabilidad: Alta \| Impacto: Medio):** El hardware móvil de gama baja se congela o tiene altas latencias al intentar procesar el audio local.
* **Riesgo 3: Descoordinación con Comunidades Locales (Probabilidad: Baja \| Impacto: Alto):** Huelgas, bloqueos de vías o rechazo de los padres impiden el ingreso de los tesistas para realizar las pruebas de campo.

##### 5.2. Plan de Respuesta a Riesgos
* **Para Riesgo 1 (Mitigación):** Inyección forzada de contexto mediante programación determinista de la base vectorial. Si la consulta del niño no coincide con el contenido educativo indexado, el modelo ejecuta un fallback controlado: "No tengo esa información en mi base local".
* **Para Riesgo 2 (Mitigación):** Utilizar modelos Whisper optimizados en formato de bajo peso (Tiny o Base quantized) y restringir el muestreo de audio a fragmentos de máximo 5 segundos.
* **Para Riesgo 3 (Contingencia):** Establecer nexos institucionales con directores de escuelas rurales de zonas cercanas accesibles por vías alternas como plan de respaldo para las pruebas del piloto.

---

#### VI. Gestión Ágil (Aplica para las Fases 2 y 3: Construcción de Software)
El ciclo de desarrollo core del backend de IA y de la app móvil se gestionará bajo un enfoque ágil, organizando el trabajo en 4 iteraciones de 2 semanas.

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
