# CE0111-CE0115 - Entregable 1: Diagnóstico Organizacional y Alineamiento Estratégico
## 1. Descripción
El presente entregable establece el **Diagnóstico Organizacional y el Alineamiento Estratégico** para el proyecto **YatiqApp**, un asistente inteligente offline diseñado para dar soporte al proceso pedagógico en el ámbito de la Educación Intercultural Bilingüe (EIB) en la región de Puno. El propósito fundamental es diagnosticar las limitaciones severas de infraestructura tecnológica (conectividad intermitente o nula y hardware móvil de gama baja) de las escuelas rurales y plantear la justificación técnica de una solución de Inteligencia Artificial On-Device. Asimismo, se define la coherencia del proyecto con los objetivos estratégicos y normativas de desarrollo local, nacional e internacional, y se presenta un análisis preliminar de riesgos y presupuesto.

## 2. Plantilla del Producto

### Portada
* **Título del Proyecto:** YatiqApp
* **Línea de Evaluación:** CE01: Gestión de Tecnologías de Información
* **Entregable:** CE0115 - Entregable 1: Diagnóstico Organizacional y Alineamiento Estratégico
* **Responsable:** Christian Rafael Mamani Callata

### Resumen Ejecutivo
Este informe presenta el análisis situacional y el alineamiento estratégico del proyecto **YatiqApp** en la Educación Intercultural Bilingüe (EIB) de la región Puno. Al identificar restricciones severas de conectividad a internet (banda ancha ausente o inestable) y limitaciones de hardware final (dispositivos de gama baja/media con RAM $\le$ 4 GB), se sustenta técnicamente la inviabilidad de arquitecturas cliente-servidor tradicionales dependientes de APIs en la nube.

En respuesta, se propone una arquitectura de Inteligencia Artificial en el borde (On-Device AI) mediante la optimización y cuantización a 4 bits de Modelos de Lenguaje Pequeños (SLMs) como Gemma-2B o Phi-3-mini, integrados con un sistema RAG (Generación Aumentada por Recuperación) embebido en una base de datos SQLite vectorial local, además de interfaces de voz locales (STT/TTS).

El proyecto demuestra un claro alineamiento estratégico con el ODS 4 (Educación de Calidad), la Política Nacional de Transformación Digital (PCM), el Plan Nacional de EIB (MINEDU) y el Plan de Desarrollo Regional Concertado (PDRC) Puno. Con una inversión inicial estimada de S/. 18,500.00 en fase de investigación y desarrollo, la propuesta se proyecta como una disrupción tecnológica que anula costos operativos recurrentes de conectividad e infraestructura cloud, asegurando la inclusión y la continuidad pedagógica en entornos de conectividad nula.

### Secciones de Desarrollo

#### I. Diagnóstico Organizacional

##### 1.1. Identificación de la Organización y Ámbito de Intervención
El presente proyecto se circunscribe en el ámbito de la Educación Intercultural Bilingüe (EIB) de la región Puno, bajo la supervisión de las Unidades de Gestión Educativa Local (UGEL), impactando directamente en las Instituciones Educativas (EE.II.) de zonas rurales de habla Quechua (variante Collao) y Aymara. Estas instituciones operan como organizaciones prestadoras de servicios educativos públicos, cuyo objetivo es garantizar el desarrollo de competencias cognitivas y lingüísticas en los estudiantes de entornos rurales dispersos.

##### 1.2. Análisis de la Infraestructura Tecnológica Actual (Línea Base)
Desde la perspectiva de la Ingeniería de Sistemas, la infraestructura tecnológica de la organización presenta restricciones críticas que definen los requerimientos no funcionales del sistema propuesto:
* **Infraestructura de Red y Conectividad:** Inexistencia o alta intermitencia de servicios de red de banda ancha (3G/4G/5G o fibra óptica) en los nodos periféricos (comunidades rurales). Esto inhabilita el despliegue de arquitecturas cliente-servidor tradicionales dependientes de APIs en la nube (Cloud-based AI).
* **Capacidad de Cómputo (Hardware Endpoint):** El parque informático de las instituciones es limitado o inexistente. El dispositivo objetivo principal es el teléfono inteligente (smartphone) de los docentes o padres de familia. El perfil de hardware predominante corresponde a dispositivos de gama baja/media con restricciones severas de memoria RAM ($\le \text{4 GB}$) y almacenamiento interno limitado.
* **Disponibilidad Energética:** Suministro eléctrico inestable en las instituciones rurales, lo que exige soluciones de software con alta eficiencia en el consumo de recursos de hardware para prolongar la autonomía de la batería de los terminales móviles.

##### 1.3. Diagnóstico de Procesos Pedagógicos y Limitaciones Lingüísticas
* **Asimetría en Recursos Digitales:** Los sistemas de gestión de aprendizaje (LMS) y los recursos interactivos disponibles están diseñados centralizadamente en idioma castellano. Existe un déficit de herramientas de procesamiento de lenguaje natural (PLN) adaptadas a la sintaxis y fonética del Quechua y Aymara.
* **Barrera de Interacción:** Los métodos actuales de autoaprendizaje digital requieren altos niveles de alfabetización funcional y tecnológica, omitiendo la naturaleza mayoritariamente oral de las lenguas originarias de la región.

##### 1.4. Matriz FODA Tecnológica y Operacional

| | Aspectos Internos (Controlables) | Aspectos Externos (No Controlables) |
| :--- | :--- | :--- |
| **Factores Positivos (Favorables)** | **Fortalezas (F):**<br>• Personal docente con competencias metodológicas en Educación Intercultural Bilingüe (EIB).<br>• Disponibilidad de dispositivos móviles inteligentes a nivel de usuario final (infraestructura distribuida).<br>• Contenidos curriculares base validados por el Ministerio de Educación. | **Oportunidades (O):**<br>• Emergencia de Modelos de Lenguaje Pequeños (SLMs) y frameworks de optimización (cuantización a 4 bits).<br>• Existencia de entornos de ejecución nativos para Inteligencia Artificial On-Device (MediaPipe, LLaMA.cpp/Ollama).<br>• Políticas gubernamentales y académicas orientadas a la reducción de la brecha digital rural. |
| **Factores Negativos (Desfavorables)** | **Debilidades (D):**<br>• Ausencia de plataformas de Inteligencia Artificial adaptadas a las variantes lingüísticas locales (Quechua Collao/Aymara).<br>• Limitación de hardware en los dispositivos locales para procesar modelos computacionales pesados.<br>• Falta de herramientas multimedia interactivas offline. | **Amenazas (A):**<br>• Brecha de infraestructura de telecomunicaciones persistente en las zonas altoandinas.<br>• Obsolescencia tecnológica rápida de los dispositivos móviles de los usuarios finales.<br>• Resistencia inicial al uso de asistentes virtuales interactivos por parte de la comunidad. |

##### 1.5. Conclusión del Diagnóstico y Justificación de la Solución
El diagnóstico organizacional demuestra que la arquitectura del sistema no puede depender de servicios cloud. La brecha de conectividad (Amenaza) y la limitada capacidad de los dispositivos (Debilidad) justifican técnicamente la investigación e implementación de un asistente inteligente basado en Edge Computing (On-Device AI).

Para viabilizar la solución en este entorno restrictivo, se requiere la selección de un Modelo de Lenguaje Pequeño (SLM) optimizado mediante técnicas de cuantización y compresión, complementado con una base de conocimientos local empleando una arquitectura RAG (Retrieval-Augmented Generation) embebida, resolviendo así el problema de la falta de herramientas adaptadas sin requerir acceso a internet.

---

#### II. Alineamiento Estratégico
El desarrollo e implementación del Asistente Inteligente Offline en Lenguas Originarias se encuentra estrictamente alineado con las políticas, planes estratégicos y normativas a nivel internacional, nacional y regional, demostrando su viabilidad, pertinencia e impacto en el desarrollo del país.

##### 2.1. Alineamiento Internacional: Objetivos de Desarrollo Sostenible (ODS - Agenda 2030)
El proyecto contribuye directamente al cumplimiento de los siguientes objetivos globales de la Organización de las Naciones Unidas (ONU):
* **ODS 4: Educación de Calidad:** Al democratizar el acceso a herramientas de Inteligencia Artificial adaptadas a la realidad lingüística y técnica de zonas rurales aisladas, se promueven oportunidades de aprendizaje equitativas e inclusivas.
* **ODS 10: Reducción de las Desigualdades:** Reduce la brecha cognitiva y digital de las poblaciones vulnerables altoandinas, integrando tecnologías de vanguardia (Procesamiento de Lenguaje Natural) en comunidades quechuas y aymaras tradicionalmente excluidas de la transformación tecnológica.

##### 2.2. Alineamiento Nacional: Política Nacional de Transformación Digital y Educación
El sistema propuesto se fundamenta en los ejes estratégicos del Estado Peruano:
* **Política Nacional de Transformación Digital (PCM):** Responde directamente al eje de Inclusión Digital, el cual busca garantizar que la tecnología sea accesible para todos los ciudadanos, priorizando soluciones innovadoras que superen las limitaciones de infraestructura de conectividad mediante arquitecturas de cómputo en el borde (Edge Computing).
* **Proyecto Educativo Nacional (PEN al 2036):** Se alinea con la visión de una educación ciudadana que reconozca y valore la diversidad cultural y lingüística del país. El asistente actúa como una herramienta de soporte que operativiza la inclusión de las lenguas originarias en entornos digitales de autoaprendizaje.
* **Plan Nacional de Educación Intercultural Bilingüe (MINEDU):** El proyecto ataca el déficit de materiales y recursos didácticos interactivos en lenguas nativas, ofreciendo una solución tecnológica que respeta y promueve el uso del Quechua Collao y el Aymara como lenguas de instrucción pedagógica.

##### 2.3. Alineamiento Regional: Plan de Desarrollo Regional Concertado (PDRC) Puno
A nivel subnacional, el proyecto se articula con los objetivos estratégicos de la región Puno:
* **Objetivo Estratégico Regional - Desarrollo Social y Humano:** El plan regional prioriza la mejora de los logros de aprendizaje en educación básica regular en las zonas rurales y de frontera de Puno. El asistente inteligente offline se inserta como un recurso tecnológico de alto impacto para mitigar las deficiencias metodológicas y de infraestructura reportadas por la Dirección Regional de Educación (DRE) Puno y las UGELs locales.
* **Preservación de la Identidad Cultural:** Respalda las iniciativas regionales de salvaguarda, revalorización y uso público de las lenguas quechua y aymara en los sistemas de información y servicios públicos (en este caso, el servicio educativo).

##### 2.4. Matriz de Consistencia Estratégica
Esta tabla resume visualmente cómo los componentes técnicos del proyecto resuelven los lineamientos estratégicos analizados:

| Lineamiento Estratégico | Meta / Objetivo Institucional | Componente Tecnológico del Proyecto (Solución) |
| :--- | :--- | :--- |
| **ODS 4 / MINEDU** | Garantizar educación inclusiva, equitativa y bilingüe en zonas rurales. | **Dataset en Quechua/Aymara + Sistema RAG Local:** Provisión de contenidos educativos interactivos y validados en la lengua materna del estudiante. |
| **PCM (Inclusión Digital)** | Superar la brecha de conectividad e infraestructura en telecomunicaciones. | **Arquitectura On-Device AI (SLM Cuantizado):** Ejecución local del modelo de IA en el dispositivo móvil sin dependencia de internet o redes 4G/5G. |
| **PDRC Puno** | Elevar los niveles de compresión y razonamiento en las escuelas de la región. | **Interfaz de Voz Local (STT/TTS):** Interacción oral automatizada para guiar al estudiante de manera intuitiva y personalizada, superando barreras de alfabetización digital. |

---

#### III. Caso de Negocio

##### 3.1. Justificación del Problema y Oportunidad de Inversión
El Estado peruano invierte anualmente millones de soles en la impresión y distribución de material educativo bilingüe físico, el cual tiene un ciclo de vida limitado, sufre de problemas logísticos de distribución en zonas altoandinas y carece de interactividad dinámica. Por otro lado, los proyectos de conectividad rural (redes dorsales, internet satelital) representan inversiones masivas a largo plazo con un despliegue lento en la periferia de Puno.

El desarrollo de este asistente inteligente offline representa una disrupción de costos y de infraestructura: aprovecha el hardware ya existente en la comunidad (los terminales móviles de los usuarios) y traslada la capacidad de cómputo al borde (Edge Computing), eliminando el costo recurrente más crítico: el consumo de datos de internet y el despliegue de infraestructura de red en zonas rurales dispersas.

##### 3.2. Análisis de Viabilidad
* **A. Viabilidad Técnica:**
  * **Factibilidad de Software:** El uso de frameworks de código abierto (como Apache TVM, MediaPipe LLM Inference API, LLaMA.cpp o MobileBERT/Gemma-2B) permite la compilación, optimización y cuantización de modelos a 4 bits, haciendo viable su ejecución en procesadores ARM de arquitectura móvil estándar.
  * **Factibilidad de Datos:** La implementación de bases de datos vectoriales locales embebidas (como SQLite con soporte vectorial o encapsulada en la app) permite estructurar un sistema RAG offline, garantizando respuestas precisas sin desborde de memoria.
* **B. Viabilidad Operativa:**
  * **Usabilidad y Curva de Aprendizaje:** Al integrar interfaces de voz (procesamiento de audio local para Quechua y Aymara), se reduce drásticamente la barrera de alfabetización digital. Tanto docentes como alumnos pueden interactuar con el sistema mediante lenguaje natural hablado.
  * **Mantenimiento y Despliegue:** El empaquetado del software en formato ejecutable nativo (como una APK de Android) facilita su distribución inicial mediante canales offline (redes locales locales, transmisión vía Bluetooth/ShareIt o carga física mediante memorias MicroSD en las UGELs).

##### 3.3. Estimación de Costos de Implementación y Operación (Presupuesto Base)
*Nota: Para el perfil se proyectan los costos simulados de investigación, desarrollo e infraestructura básica.*

| Concepto / Rubro | Costo (PEN) | Recurso |
| :--- | :---: | :--- |
| **1. Fase de Investigación y Recolección de Datos** (Validación de corpus lingüístico/EIB) | S/. 2,500.00 | Propios |
| **2. Infraestructura de Cómputo de Desarrollo** (GPU local / Cloud Credits para Fine-Tune) | S/. 6,500.00 | Propios |
| **3. Ingeniería de Software y Entrenamiento** (Desarrollo de App, Cuantización y RAG) | S/. 8,000.00 | Tesista |
| **4. Pruebas de Campo y Validación Piloto** (Despliegue experimental en escuelas Puno) | S/. 1,500.00 | Propios |
| **Total Inversión Estimada** | **S/. 18,500.00** | |

##### 3.4. Beneficios Esperados y Retorno Social de la Inversión (SROI)
* **Beneficios Tangibles (Reducción de Costos Operativos):**
  * **Costo de Conectividad S/. 0.00:** Al ser un sistema 100% offline, el costo recurrente en planes de datos para las instituciones o familias de los estudiantes es nulo.
  * **Costo de Infraestructura de Servidores S/. 0.00:** No requiere el mantenimiento, escalabilidad ni pago de servicios Cloud (como AWS o Azure) para la inferencia del modelo de IA, ya que el procesamiento es absorbido por el hardware del cliente móvil (On-Device).
* **Beneficios Intangibles (Impacto Pedagógico y Social):**
  * **Inclusión Lingüística:** Democratización de los beneficios de la Inteligencia Artificial Generativa para hablantes de Quechua y Aymara.
  * **Disponibilidad 24/7:** El aprendizaje no se detiene ante cortes de señal o falta de cobertura telefónica en áreas rurales aisladas.
  * **Personalización Educativa:** El asistente proporciona una retroalimentación inmediata al ritmo de aprendizaje del estudiante, mitigando la tasa de rezago escolar.

---

#### IV. Roadmap de Tecnología (Hoja de Ruta)
El desarrollo del asistente inteligente se ejecutará de manera secuencial e iterativa, asegurando que las restricciones de hardware y las particularidades lingüísticas sean validadas de forma incremental.

```
Fase 1: Curación e Ingesta ──> Fase 2: Optimización e IA ──> Fase 3: Arquitectura Móvil ──> Fase 4: Piloto y Validación
     (Mes 1 - 2)                   (Mes 3 - 4)                 (Mes 5 - 6)                   (Mes 7)
```

* **Fase 1: Curación de Datos e Ingesta del Conocimiento (Mes 1 - Mes 2)**
  El enfoque está en la recopilación y estructuración del corpus de conocimiento pedagógico bilingüe.
  * **Hito 1:** Recopilación y digitalización del material educativo oficial de Educación Intercultural Bilingüe (EIB) del MINEDU en variantes Quechua Collao y Aymara.
  * **Hito 2:** Procesamiento y limpieza del texto: tokenización adaptada, eliminación de ruido gramatical y alineación bilingüe (Castellano-Quechua/Castellano-Aymara).
  * **Hito 3:** Diseño y poblamiento de la base de datos de conocimiento en formato estructurado (JSON/Markdown) para la posterior ingesta en el sistema de recuperación.
* **Fase 2: Ingeniería de IA, Cuantización y RAG Local (Mes 3 - Mes 4)**
  Fase puramente de backend y optimización de modelos de lenguaje pequeños (SLMs).
  * **Hito 1:** Selección y evaluación comparativa en entorno de desarrollo (GPU local) de Modelos de Lenguaje Pequeños de código abierto (ej. Gemma-2B, Phi-3-mini o Llama-3-8B).
  * **Hito 2:** Aplicación de técnicas de cuantización de post-entrenamiento (PTQ) a 4 bits (utilizando formatos como GGUF o AWQ) para reducir el peso del modelo y su consumo de memoria RAM a límites tolerables por un smartphone ($\le \text{1.5 GB}$ en ejecución).
  * **Hito 3:** Configuración del motor de generación aumentada por recuperación (RAG Offline) empleando una biblioteca de embeddings ligera y una base de datos vectorial local (ej. SQLite Vector Extension o empaquetada nativamente).
* **Fase 3: Arquitectura y Desarrollo de la Aplicación Móvil (Mes 5 - Mes 6)**
  Integración del motor de IA optimizado dentro del entorno de ejecución móvil sin conectividad.
  * **Hito 1:** Configuración del entorno de desarrollo móvil (Flutter o React Native) e integración de la API de inferencia local (ej. MediaPipe LLM Inference API o integración nativa con LLaMA.cpp vía C++ JNI).
  * **Hito 2:** Desarrollo de los módulos locales de Procesamiento de Voz (STT y TTS) optimizados para arquitecturas ARM, permitiendo la traducción local de audio a texto y viceversa en lenguas originarias.
  * **Hito 3:** Diseño e implementación de la interfaz de usuario (UI/UX) gamificada, adaptada a niños y optimizada para pantallas de baja resolución.
* **Fase 4: Pruebas de Sistema, Despliegue Piloto y Validación (Mes 7)**
  Aseguramiento de la calidad del software en condiciones reales de aislamiento técnico.
  * **Hito 1:** Pruebas de estrés y perfilado de hardware (profiling): Monitoreo de consumo de batería, temperatura del CPU del móvil, tasa de uso de memoria RAM y latencia de respuesta (búsqueda de un Time-to-First-Token $\le \text{2 segundos}$).
  * **Hito 2:** Despliegue del paquete de instalación (.apk) de forma offline (vía MicroSD / Bluetooth) en un grupo de control de smartphones de gama baja/media.
  * **Hito 3:** Validación pedagógica y operativa en una escuela rural piloto de la región Puno para medir la precisión de las respuestas del asistente y la usabilidad por parte de estudiantes y docentes.

##### Matriz Tecnológica del Proyecto
Esta tabla resume el stack tecnológico (tecnologías seleccionadas) que se defenderá en el perfil:

| Capa de Arquitectura | Tecnología Seleccionada | Justificación Técnica para el Proyecto |
| :--- | :--- | :--- |
| **Modelamiento de IA (SLM)** | Gemma 2B / Phi-3-mini (Cuantizados) | Modelos compactos con excelente rendimiento académico que pueden operar en local ocupando poca RAM. |
| **Inferencia Móvil (Engine)** | MediaPipe LLM Inference / LLaMA.cpp | Frameworks de bajo nivel optimizados para ejecutar modelos binarios directamente sobre CPUs/GPUs móviles (ARM). |
| **Base de Datos Vectorial (RAG)** | SQLite con soporte vectorial embebido | Permite realizar búsquedas semánticas de las lecciones escolares de forma 100% offline dentro de la misma app. |
| **Procesamiento de Voz (STT/TTS)** | Whisper (Tiny/Base quantized) / Piper TTS | Modelos optimizados para transcripción y síntesis de voz ejecutables localmente en hardware móvil restringido. |
| **Desarrollo Frontend Móvil** | Flutter o React Native | Desarrollo multiplataforma eficiente que permite bindings nativos de C++ para el motor de IA. |

---

#### V. Matriz de Riesgos Estratégicos
Para garantizar la viabilidad y el éxito del proyecto, se ha realizado un análisis de riesgos estratégicos categorizados según su naturaleza técnica, operativa y social, evaluando su nivel de impacto y probabilidad de ocurrencia mediante una escala matricial (Baja, Media, Alta).

##### 5.1. Definición y Clasificación de Riesgos
* **Riesgo Técnico (RT):** Asociado a las limitaciones de hardware, rendimiento del modelo y degradación por optimización.
* **Riesgo de Datos (RD):** Relacionado con la precisión, disponibilidad y sesgo del corpus lingüístico en lenguas originarias.
* **Riesgo Operativo y de Adopción (RO):** Enfocado en la usabilidad, resistencia al cambio y canales de distribución sin internet.

##### 5.2. Matriz de Evaluación y Mitigación de Riesgos

| ID | Descripción del Riesgo | Probabilidad | Impacto | Nivel de Riesgo | Estrategia de Mitigación (Enfoque de Ingeniería) |
| :---: | :--- | :---: | :---: | :---: | :--- |
| **RT-01** | **Desbordamiento de Memoria (OOM):** El modelo de IA (SLM) satura la memoria RAM ($\le \text{4 GB}$) en teléfonos de gama baja, provocando el cierre de la app. | Alta | Alta | **Crítico** | Aplicar cuantización agresiva de post-entrenamiento (PTQ a 4 bits o menos) y configurar técnicas de sharding o descarga en caché de capas del modelo para balancear el uso de CPU/GPU móvil. |
| **RT-02** | **Latencia Excesiva de Respuesta:** El procesador móvil tarde demasiado en procesar el texto/voz (Time-to-First-Token mayor a 10 segundos), frustrando al usuario. | Media | Alta | **Alto** | Optimizar el motor de inferencia usando bindings de bajo nivel en C++ (vía LLaMA.cpp o MediaPipe) aprovechando la aceleración por hardware (NPU/GPU) nativa del procesador ARM. |
| **RD-01** | **Alucinación de Datos y Sesgo Lingüístico:** El asistente responde con datos falsos o mezcla variantes dialectales no usadas en Puno (ej. Quechua Chanka en vez de Collao). | Media | Alta | **Alto** | Implementar una arquitectura RAG (Retrieval-Augmented Generation) offline estricta, forzando al modelo mediante prompt engineering a responder únicamente utilizando los documentos pedagógicos locales indexados en la base de datos vectorial embebida. |
| **RD-02** | **Baja Precisión en el Reconocimiento de Voz (STT):** Los modelos de audio fallan al procesar la fonética o el ruido de fondo de las aulas rurales. | Alta | Media | **Medio** | Realizar un ajuste fino (Fine-Tuning) o filtrado previo de las muestras de audio locales mediante algoritmos ligeros de cancelación de ruido digital antes de pasar el input al motor Whisper cuantizado. |
| **RO-01** | **Brecha de Distribución del Software:** Imposibilidad de actualizar o instalar la aplicación debido a la falta absoluta de internet en la comunidad. | Alta | Media | **Medio** | Diseñar un protocolo de despliegue descentralizado mediante las UGELs usando redes locales inalámbricas temporales (Routers locales), distribución física en memorias MicroSD o transferencia local P2P (Peer-to-Peer) mediante protocolos como Wi-Fi Direct. |
| **RO-02** | **Resistencia a la Adopción por Barrera Cultural:** Los docentes o estudiantes rechazan el uso de la IA por considerarla ajena a sus costumbres. | Baja | Alta | **Medio** | Diseñar una interfaz de usuario interactiva y gamificada que incluya avatares con trajes y elementos iconográficos propios de la cultura local, además de involucrar activamente a especialistas de la UGEL en la validación pedagógica inicial. |

##### 5.3. Conclusión del Análisis de Riesgos
El análisis estratégico evidencia que el mayor cuello de botella es de carácter técnico (rendimiento en hardware restrictivo). Al mitigar el riesgo RT-01 y RT-02 mediante ingeniería de optimización avanzada (cuantización y ejecución nativa en el borde), se viabiliza la arquitectura offline, lo que a su vez minimiza los riesgos de costos y dependencia externa analizados en el Caso de Negocio.

### Anexos
*(En los siguientes entregables se integrarán diagramas arquitectónicos y capturas de pantalla de la solución móvil)*

## 3. Rúbrica de Evaluación
El presente entregable ha sido elaborado considerando las siguientes competencias del perfil de egreso:
- **CE01 (Gestión de Tecnologías de Información):** Capacidad para proponer soluciones TIC que se alineen estratégicamente con los objetivos de la organización, evalúen la viabilidad técnica/operativa y estimen costos de implementación.
- **Criterios de Evaluación:** Diagnóstico situacional sustentado en datos de infraestructura, consistencia de la matriz estratégica (ODS, PCM, PDRC Puno), viabilidad en el Caso de Negocio y rigurosidad en la matriz de mitigación de riesgos.