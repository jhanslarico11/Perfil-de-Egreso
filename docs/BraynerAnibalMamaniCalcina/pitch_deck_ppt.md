# 📊 Pitch Deck: YatiqApp (Sustentación Final)

Este documento contiene todo el contenido detallado, diapositiva por diapositiva, para que puedas copiarlo directamente a tu software de presentaciones (PowerPoint, Canva, Google Slides). Además, incluye las **notas del orador (Guión)** para que sepas exactamente qué decir en cada momento.

---

## 🎴 Diapositiva 1: Portada
**Título Central:** YatiqApp
**Subtítulo:** Co-piloto de Inteligencia Artificial para la Preservación y Traducción de Lenguas Originarias (Aymara y Quechua).
**Pie de página:** 
* Línea de Evaluación CE02: Ingeniería de Software
* Responsable: Brayner Aníbal Mamani Calcina

> 🗣️ **Nota del Orador:** *"Buenos días miembros del jurado. Hoy les presento YatiqApp, una solución tecnológica diseñada no solo con ingeniería de vanguardia, sino con un propósito social profundo: llevar la inteligencia artificial a nuestras lenguas originarias."*

---

## 🎴 Diapositiva 2: Planteamiento del Problema
**Título:** La Brecha Lingüística Digital
**Viñetas (Bullet points):**
* Más de 4 millones de personas hablan Quechua y Aymara en Perú y Bolivia.
* El 95% del ecosistema digital excluye estas lenguas.
* Asistentes como Siri o Google Assistant no tienen soporte conversacional para lenguas andinas.
* **El Reto Técnico:** Procesar voz a voz requiere modelos masivos de IA que normalmente son lentos y costosos de correr.

> 🗣️ **Nota del Orador:** *"A pesar de tener millones de hablantes, el aymara y el quechua están prácticamente invisibilizados en la tecnología moderna. Nuestro reto técnico fue crear un sistema capaz de traducir y hablar estas lenguas con la misma velocidad y naturalidad con la que interactuamos con Siri o Alexa."*

---

## 🎴 Diapositiva 3: La Solución (YatiqApp)
**Título:** YatiqApp: IA en tu Bolsillo
**Elementos Visuales Sugeridos:** Colocar aquí la *Captura de la App Móvil (Anexo 4)*.
**Viñetas:**
* **Frontend Nativo:** Aplicación móvil rápida y accesible desarrollada en Flutter.
* **Traductor Bidireccional:** Voz a Voz y Texto a Texto en tiempo real.
* **Asistente Educativo:** Módulo de aprendizaje interactivo (LMS) integrado.
* **Autonomía:** Historial y lecciones disponibles Offline.

> 🗣️ **Nota del Orador:** *"La solución es YatiqApp. Una aplicación móvil desarrollada en Flutter, lo que nos garantiza un rendimiento fluido tanto en Android como en iOS, y que actúa como un puente instantáneo entre el español y nuestras lenguas andinas."*

---

## 🎴 Diapositiva 4: Arquitectura del Sistema
**Título:** Arquitectura Híbrida en 3 Capas (3-Tier Cascade)
**Elementos Visuales Sugeridos:** Insertar el Diagrama C4 de la Arquitectura.
**Bloques a mostrar:**
1. **Capa Cliente:** App Móvil Flutter (UI y Grabación) + Panel Web.
2. **Capa Intermedia (Proxy):** Servidor Laravel (Autenticación y Caché).
3. **Capa Inferencial (Backend AI):** Microservicio FastAPI corriendo en GPU NVIDIA.

> 🗣️ **Nota del Orador:** *"A nivel de ingeniería, construimos una arquitectura híbrida de microservicios. Nuestro cliente móvil se comunica a través de HTTP Multipart con un backend asíncrono en FastAPI. Este diseño desacoplado nos permite delegar el procesamiento pesado a un servidor con GPU, manteniendo la aplicación del celular ligera y con bajo consumo de memoria."*

---

## 🎴 Diapositiva 5: Modelos Neuronales SOTA (State of the Art)
**Título:** El Pipeline Inferencial (Voz a Voz)
**Gráfico Sugerido:** Un flujo de 3 pasos: Micrófono ➡️ Texto ➡️ Texto Nativo ➡️ Audio Nativo.
**Viñetas:**
1. **ASR (Reconocimiento de Voz):** OpenAI Whisper Turbo (Transcribe el español).
2. **NMT (Traducción Neuronal):** NLLB-200 de Meta optimizado con adaptadores LoRA.
3. **TTS (Síntesis de Voz):** Meta MMS (Sintetiza audio realista en aymara/quechua).
* **Latencia Lograda:** < 1.0 segundos por inferencia.

> 🗣️ **Nota del Orador:** *"Para lograr la traducción de voz, ensamblamos un pipeline en cascada cargado directamente en la VRAM de nuestra GPU local. El proceso pasa por reconocimiento, traducción neuronal finaizada con técnicas LoRA, y síntesis acústica, logrando respuestas en menos de un segundo."*

---

## 🎴 Diapositiva 6: Plataforma de Datos y Tolerancia a Fallos
**Título:** Persistencia y Resiliencia
**Viñetas:**
* **Bases de Datos Embebidas:** SQLite en el servidor y Hive/SQLite en la App Móvil.
* **Funcionamiento Offline:** Almacenamiento de historial y progreso de lecciones directamente en el teléfono.
* **Seguridad:** Peticiones protegidas por Tokens CSRF, limpieza de archivos temporales (WAV) de memoria para preservar la privacidad del usuario.
* **Cola de Tareas (Jobs):** Entrenamientos intensivos en segundo plano (Database Queues).

> 🗣️ **Nota del Orador:** *"La robustez es clave. Usamos bases de datos embebidas como SQLite para la portabilidad del servidor y caché local en la app móvil. Además, limpiamos atómicamente todos los audios de los usuarios apenas son procesados para asegurar su privacidad absoluta."*

---

## 🎴 Diapositiva 7: Aseguramiento de Calidad (Model Arena)
**Título:** Validación Científica de la IA
**Elementos Visuales Sugeridos:** Gráfica de Convergencia (Anexo 3) y el Panel Comparador (Anexo 2).
**Viñetas:**
* **Testing Automatizado:** Matriz de pruebas funcionales (UI y Backend).
* **Precisión Superior:** El adaptador LoRA supera métricas estándares frente al modelo base (BLEU y ChrF++).
* **Reportes en Tiempo Real:** Interfaz web Laravel para monitoreo de pérdida (Loss Curve) por administradores.

> 🗣️ **Nota del Orador:** *"En calidad de software, no solo testeamos que la app no falle, evaluamos científicamente a la IA. Construimos un módulo 'Model Arena' que demuestra con métricas como BLEU y ChrF++ que nuestro re-entrenamiento (LoRA) mejora radicalmente las traducciones del modelo base."*

---

## 🎴 Diapositiva 8: Demostración en Vivo
**Título:** Demo: YatiqApp en Acción
**Contenido:** (Esta diapositiva puede tener solo un título grande o un video pre-grabado en bucle de la aplicación, mientras muestras el celular).

> 🗣️ **Nota del Orador (Acción):** *"Ahora pasaré a proyectar la pantalla de mi celular Android. Como pueden ver, presiono el micrófono y pregunto algo en español... [Mostrar funcionamiento]. La respuesta es inmediata. Si apago el Wi-Fi, pueden observar cómo mi historial sigue disponible en modo offline."*

---

## 🎴 Diapositiva 9: Futuro y Escalabilidad
**Título:** Roadmap de Evolución
**Viñetas:**
* **Despliegue Cloud:** Migración a instancias AWS EC2 (g5.xlarge) para millones de usuarios.
* **Nuevos Idiomas:** Integración de lenguas amazónicas (Shipibo-Conibo, Asháninka) mediante carga de adaptadores ligeros (Hot-swapping).
* **Edge Computing:** Cuantización extrema (4 bits) para correr Llama-3 directamente en el procesador del celular en futuras versiones.

> 🗣️ **Nota del Orador:** *"YatiqApp nació en un entorno local, pero está diseñado para el mundo. Nuestro plan de evolución contempla el despliegue en la nube de Amazon y la integración de lenguas amazónicas sin cambiar la arquitectura del sistema."*

---

## 🎴 Diapositiva 10: Cierre
**Título:** ¡Gracias!
**Subtítulo:** Preservando nuestra cultura con Inteligencia Artificial.
**Datos:** 
* Nombre: Brayner Mamani Calcina
* Repositorio / Contacto

> 🗣️ **Nota del Orador:** *"La tecnología debe ser un puente y no una barrera. YatiqApp es la demostración de que la ingeniería de software moderna puede rescatar y revalorizar nuestras raíces. Muchas gracias por su atención, quedo atento a sus preguntas."*
