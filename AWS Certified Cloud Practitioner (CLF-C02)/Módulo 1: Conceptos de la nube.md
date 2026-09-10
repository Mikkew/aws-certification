# Módulo 1: Conceptos de la nube

## 1.1 Beneficios de la nube de AWS

### 1. Resumen rápido

La **computación en la nube** es la entrega a petición de recursos de TI mediante Internet con un esquema de pago por uso, lo que permite eliminar inversiones fijas en infraestructura física y escalar globalmente en minutos.

### 2. Objetivos de aprendizaje

- Identificar y explicar las **seis ventajas de la computación en la nube** de AWS.
- Comparar los modelos de servicio en la nube: **IaaS**, **PaaS** y **SaaS**.
- Diferenciar los modelos de despliegue en la nube: **Nube**, **Híbrido** y **On-premises**.
- Comprender la transformación de **gastos de capital (CapEx)** a **gastos variables (OpEx)**.

### 3. Explicación detallada

La computación en la nube reemplaza la visión tradicional de la infraestructura como hardware físico por un enfoque de la **infraestructura como software**. En el modelo tradicional **On-premises**, las empresas deben adquirir servidores físicos, gestionar centros de datos y dimensionar la capacidad basándose en suposiciones de picos máximos teóricos.

#### Las seis ventajas clave de la nube de AWS

1. **Cambiar los gastos de capital (CapEx) por gastos variables (OpEx):** En lugar de realizar inversiones masivas por adelantado en servidores y centros de datos sin saber cómo se utilizarán, solo paga cuando consume recursos y únicamente por la cantidad consumida.
2. **Beneficiarse de masivas economías de escala:** Debido a la utilización agregada de cientos de miles de clientes, AWS logra mayores economías de escala que se traducen en precios más bajos por pago de uso.
3. **Dejar de adivinar la capacidad:** Se elimina la incertidumbre en la planificación de capacidad. Se ajusta la infraestructura de manera elástica hacia arriba o hacia abajo en minutos según la demanda real.
4. **Aumentar la velocidad y la agilidad:** Los nuevos recursos de TI están disponibles a un solo clic, reduciendo el tiempo de aprovisionamiento de semanas a solo minutos.
5. **Dejar de gastar dinero en el mantenimiento de centros de datos:** Permite enfocarse en proyectos que diferencien al negocio en lugar de realizar el trabajo pesado no diferenciado como apilar, cablear y alimentar servidores.
6. **Volverse global en cuestión de minutos:** Se pueden desplegar aplicaciones en múltiples **Regiones de AWS** alrededor del mundo con unos pocos clics, ofreciendo menor latencia a los clientes.

#### Modelos de servicio en la nube

- **Infrastructure as a Service (IaaS):** Proporciona bloques básicos de construcción de TI como red, computadoras virtuales y espacio de almacenamiento (ej. **Amazon EC2**, **Amazon VPC**). Ofrece el mayor nivel de control y flexibilidad.
- **Platform as a Service (PaaS):** Reduce la necesidad de gestionar la infraestructura subyacente (hardware y sistemas operativos) para centrarse en el despliegue y gestión de aplicaciones (ej. **AWS Elastic Beanstalk**).
- **Software as a Service (SaaS):** Producto completo administrado por el proveedor de servicios, orientado al usuario final (ej. correo electrónico web).

| Modelo de Servicio | Nivel de Control | Responsabilidad del Cliente | Ejemplo en AWS |
| --- | --- | --- | --- |
| **IaaS** | Alto | Sistema operativo, parches, aplicaciones, datos | Amazon EC2 |
| **PaaS** | Medio | Código de la aplicación y datos | AWS Elastic Beanstalk |
| **SaaS** | Bajo | Configuración de usuario final y uso del software | AWS Artifact, Amazon Cognito |

#### Modelos de despliegue

- **Nube (Cloud-based):** La aplicación está completamente desplegada en la nube.
- **Híbrido (Hybrid):** Conecta la infraestructura basada en la nube con recursos existentes no ubicados en la nube (On-premises) mediante herramientas como **AWS Direct Connect** o **AWS Site-to-Site VPN**.
- **On-premises / Nube privada:** Despliegue de recursos utilizando tecnologías de virtualización en instalaciones locales.

### 4. Ejemplos prácticos

Para consultar las regiones globales disponibles directamente desde la interfaz de línea de comandos de AWS (**AWS CLI**), ejecute:

```
aws ec2 describe-regions --output table
```

**Explicación de la salida:**
El comando consulta la API de EC2 y devuelve una tabla con todas las regiones activadas en su cuenta, mostrando los nombres de los extremos (`Endpoint`) y los nombres de las regiones (`RegionName`), por ejemplo, `us-east-1` (N. Virginia) o `eu-west-1` (Irlanda).

**Escenario real:**
Una tienda de comercio electrónico experimenta un pico de tráfico el Buen Fin. En lugar de comprar 50 servidores físicos que estarían ociosos el resto del año, utiliza **Amazon EC2 Auto Scaling** para añadir instancias automáticamente durante el evento y destruirlas al finalizar, pagando únicamente por las horas utilizadas.

### 5. Errores comunes y cómo evitarlos

- **Confundir escalabilidad con elasticidad:** La **escalabilidad** es la capacidad de un sistema para manejar el crecimiento de la carga; la **elasticidad** es la capacidad de aumentar o reducir recursos automáticamente en respuesta a cambios en la demanda.
- **Asumir que IaaS elimina la administración del sistema operativo:** En IaaS (**Amazon EC2**), el cliente sigue siendo responsable de aplicar parches de seguridad al sistema operativo huésped.
- **Adivinar la capacidad por adelantado:** Intentar aprovisionar capacidad máxima por miedo a caídas conduce a costos innecesarios por recursos ociosos.

### 6. Preguntas de práctica

1. ¿Cuál de las siguientes es una ventaja directa de cambiar gastos de capital por gastos variables?
    - A) Pago de tarifas fijas mensuales obligatorias.
    - B) Sustitución de costos fijos por adelantado por costos basados en el consumo.
    - C) Control completo del mantenimiento del centro de datos físico.
    - D) Obligación de firmar contratos a largo plazo.
    *Respuesta correcta:* **B**. Permite a las organizaciones pagar únicamente por los recursos informáticos consumidos.
2. Un cliente desea desplegar una aplicación web pero no quiere gestionar el sistema operativo ni la plataforma de ejecución. ¿Qué modelo de servicio cumple con este requisito?
    - A) IaaS
    - B) SaaS
    - C) PaaS
    - D) On-premises
    *Respuesta correcta:* **C**. PaaS abstrae la gestión del sistema operativo e infraestructura para centrarse en la aplicación.
3. ¿Qué beneficio de la nube permite desplegar aplicaciones a usuarios finales de todo el mundo con la mínima latencia posible?
    - A) Economías de escala
    - B) Volverse global en cuestión de minutos
    - C) Detener la adivinación de capacidad
    - D) Infraestructura como hardware
    *Respuesta correcta:* **B**. Permite desplegar aplicaciones en múltiples Regiones de AWS cercanas a los usuarios con pocos clics.

### 7. Tarjetas rápidas / Flashcards

- **Pregunta:** ¿Qué ventaja de la nube evita realizar trabajo pesado no diferenciado como el mantenimiento físico de servidores?
    - **Respuesta:** Dejar de gastar dinero en el funcionamiento y mantenimiento de centros de datos.
- **Pregunta:** ¿Qué modelo de servicio es Amazon EC2?
    - **Respuesta:** IaaS (Infraestructura como Servicio).
- **Pregunta:** ¿Qué modelo de despliegue conecta servidores locales On-premises con recursos en AWS?
    - **Respuesta:** Despliegue Híbrido.

### 8. Gancho mnemotécnico

Memoriza las 6 ventajas con la sigla **C-E-A-V-M-G**:

> **C**ambiar CapEx por OpEx
> 
> 
> **E**conomías de escala masivas
> 
> **A**divinar capacidad jamás
> 
> **V**elocidad y agilidad
> 
> **M**antenimiento de Data Centers fuera
> 
> **G**lobal en minutos
> 

---

## 1.2 Principios de diseño (Well-Architected)

### 1. Resumen rápido

El **AWS Well-Architected Framework** proporciona una guía y mejores prácticas basadas en seis pilares fundamentales para evaluar e implementar arquitecturas seguras, eficientes, fiables y optimizadas en costos en la nube.

### 2. Objetivos de aprendizaje

- Identificar los **seis pilares del marco AWS Well-Architected**.
- Reconocer los principios de diseño específicos para cada pilar.
- Comprender el propósito y uso de la herramienta **AWS Well-Architected Tool**.
- Aplicar principios arquitectónicos cloud-native para eliminar puntos únicos de fallo.

### 3. Explicación detallada

El marco AWS Well-Architected ayuda a los arquitectos de la nube a construir la infraestructura más segura, de alto rendimiento, resiliente y eficiente posible para sus aplicaciones.

#### Los seis pilares del Well-Architected Framework

1. **Excelencia Operativa (Operational Excellence):** Se enfoca en ejecutar y monitorear sistemas para entregar valor de negocio y mejorar continuamente los procesos y procedimientos de soporte.
    - *Principios:* Realizar operaciones como código, hacer cambios pequeños y reversibles, refinar procedimientos con frecuencia, anticipar fallas y aprender de todas las fallas operativas.
2. **Seguridad (Security):** Se centra en proteger la información, los sistemas y los activos mientras se entrega valor al negocio mediante evaluaciones de riesgo y estrategias de mitigación.
    - *Principios:* Implementar una base de identidad sólida, permitir trazabilidad, aplicar seguridad en todas las capas, automatizar mejores prácticas de seguridad, proteger datos en tránsito y en reposo, mantener a las personas alejadas de los datos y prepararse para eventos de seguridad.
3. **Fiabilidad (Reliability):** Garantiza que una carga de trabajo ejecute su función de manera correcta y consistente cuando se espera. Incluye la capacidad de operar y recuperarse de fallas de manera automatizada.
    - *Principios:* Recuperarse automáticamente de fallas, probar procedimientos de recuperación, escalar horizontalmente para aumentar la disponibilidad agregada, dejar de adivinar capacidad y gestionar cambios mediante automatización.
4. **Eficiencia del Rendimiento (Performance Efficiency):** Se centra en el uso eficiente de los recursos informáticos y de TI para mantener esa eficiencia a medida que la demanda cambia y las tecnologías evolucionan.
    - *Principios:* Democratizar tecnologías avanzadas, volverse global en minutos, usar arquitecturas serverless, experimentar con más frecuencia y considerar la empatía mecánica.
5. **Optimización de Costos (Cost Optimization):** Se enfoca en la capacidad de ejecutar sistemas para brindar valor al negocio al precio más bajo posible sin comprometer el rendimiento.
    - *Principios:* Implementar **Cloud Financial Management**, adoptar un modelo de consumo, medir la eficiencia general, dejar de gastar dinero en trabajo pesado no diferenciado y analizar/atribuir gastos.
6. **Sostenibilidad (Sustainability):** Se enfoca en minimizar los impactos ambientales de la ejecución de cargas de trabajo en la nube, optimizando el consumo energético y la eficiencia de recursos.

| Pilar | Enfoque Principal | Concepto Clave |
| --- | --- | --- |
| **Excelencia Operativa** | Entrega de valor y mejora continua | Operaciones como código |
| **Seguridad** | Protección de datos y sistemas | Defensa en profundidad y menor privilegio |
| **Fiabilidad** | Recuperación ante fallas y resiliencia | Recuperación automática de fallas |
| **Eficiencia del Rendimiento** | Uso óptimo de recursos | Uso de arquitecturas serverless |
| **Optimización de Costos** | Eliminación de gastos innecesarios | Modelo de consumo (pagar por uso) |
| **Sostenibilidad** | Reducción del impacto ambiental | Minimizar recursos ociosos |

#### AWS Well-Architected Tool

Es una herramienta disponible en la **AWS Management Console** que permite revisar y evaluar las cargas de trabajo según los pilares del marco, entregando un plan de acción con orientación paso a paso para mitigar riesgos arquitectónicos.

### 4. Ejemplos prácticos

Para consultar y listar las evaluaciones creadas dentro de su cuenta usando AWS CLI:

```
aws wellarchitected list-workloads --max-results 5
```

**Explicación de la salida:**
Regresa una lista en JSON con los datos de las cargas de trabajo registradas (`WorkloadSummaries`), incluyendo su identificador `WorkloadId`, nombre del proyecto y el estado del análisis de riesgos en cada pilar.

**Escenario real:**
Una arquitectura web despliega sus instancias EC2 en una sola **Zona de Disponibilidad (AZ)**. Al aplicar la revisión de **Fiabilidad**, se identifica un punto único de fallo. La recomendación es migrar a un despliegue **Multi-AZ** respaldado por un **Application Load Balancer (ALB)** e instancias distribuidas dinámicamente.

### 5. Errores comunes y cómo evitarlos

- **Tratar la optimización de costos como un evento único:** Es un proceso continuo que requiere medición y análisis constante.
- **Proporcionar acceso con credenciales de usuario raíz (Root):** Se viola el pilar de Seguridad. Se debe usar **AWS Identity and Access Management (IAM)** bajo el principio de menor privilegio.
- **No probar la recuperación ante desastres:** Las estrategias de recuperación deben probarse periódicamente mediante simulaciones automatizadas.

### 6. Preguntas de práctica

1. ¿Cuál pilar del AWS Well-Architected Framework enfatiza la capacidad de recuperarse automáticamente de interrupciones del sistema?
    - A) Excelencia Operativa
    - B) Eficiencia del Rendimiento
    - C) Fiabilidad
    - D) Sostenibilidad
    *Respuesta correcta:* **C**. La Fiabilidad busca que los sistemas ejecuten su función correctamente y se recuperen de fallas de forma automatizada.
2. ¿Qué principio de diseño corresponde al pilar de Excelencia Operativa?
    - A) Realizar operaciones como código.
    - B) Mantener a las personas alejadas de los datos.
    - C) Adoptar un modelo de consumo.
    - D) Democratizar tecnologías avanzadas.
    *Respuesta correcta:* **A**. Definir e implementar infraestructura y procesos como código permite limitar errores humanos y responder con consistencia.
3. ¿Qué herramienta de AWS ayuda a los usuarios a revisar sus cargas de trabajo frente a las mejores prácticas de arquitectura y proporciona planes de mejora?
    - A) AWS Trusted Advisor
    - B) AWS Well-Architected Tool
    - C) AWS Config
    - D) AWS CloudTrail
    *Respuesta correcta:* **B**. La AWS Well-Architected Tool permite medir arquitecturas contra los 6 pilares del marco.

### 7. Tarjetas rápidas / Flashcards

- **Pregunta:** ¿Cuáles son los seis pilares del AWS Well-Architected Framework?
    - **Respuesta:** Excelencia Operativa, Seguridad, Fiabilidad, Eficiencia del Rendimiento, Optimización de Costos y Sostenibilidad.
- **Pregunta:** ¿A qué pilar pertenece el principio "Proteger datos en tránsito y en reposo"?
    - **Respuesta:** Al pilar de Seguridad.
- **Pregunta:** ¿Cuál es la recomendación del pilar de Fiabilidad para evitar puntos únicos de fallo?
    - **Respuesta:** Escalar horizontalmente distribuyendo la carga en múltiples recursos más pequeños.

### 8. Gancho mnemotécnico

Recuerda los 6 pilares pensando en la frase:

> **"E-S-F-E-C-S"** -> **E**l **S**istema **F**unciona **E**ficientemente **C**on **S**ostenibilidad
> 
> 
> (**E**xcelencia Operativa, **S**eguridad, **F**iabilidad, **E**ficiencia, **C**ostos, **S**ostenibilidad).
> 

---

## 1.3 Estrategias de migración (AWS CAF)

### 1. Resumen rápido

El **AWS Cloud Adoption Framework (AWS CAF)** ayuda a las organizaciones a diseñar un camino estructurado hacia la adopción exitosa de la nube, organizando sus recomendaciones en seis perspectivas interconectadas que abarcan personas, procesos y tecnología.

### 2. Objetivos de aprendizaje

- Reconocer el propósito del **AWS Cloud Adoption Framework (AWS CAF)**.
- Identificar las **seis perspectivas del AWS CAF** y clasificarlas en enfoques de negocio y técnicos.
- Asociar las partes interesadas (**stakeholders**) clave con cada perspectiva del CAF.
- Explicar las estrategias clásicas de migración a la nube (las **6 Rs de la migración**).

### 3. Explicación detallada

La adopción de la nube no ocurre instantáneamente; requiere una alineación deliberada en toda la organización. El AWS CAF ayuda a identificar lagunas en habilidades y procesos para trazar planes de migración integrales.

#### Las seis perspectivas del AWS CAF

El framework organiza sus guías en seis **perspectivas**:

1. **Perspectivas con enfoque de negocio (Business Capabilities):**
    - **Perspectiva de Negocio (Business):** Garantiza que las inversiones en TI se alineen con las necesidades del negocio y los resultados sean demostrables.
        - *Stakeholders:* Gerentes de negocio, gerentes de finanzas, dueños de presupuesto y estrategas.
    - **Perspectiva de Personas (People):** Evalúa estructuras organizativas, roles y requisitos de nuevas habilidades, priorizando la capacitación, contratación y gestión del cambio organizacional.
        - *Stakeholders:* Recursos Humanos, líderes de personal y gestores de cambio.
    - **Perspectiva de Gobernanza (Governance):** Se enfoca en habilidades y procesos para alinear la estrategia de TI con la estrategia comercial, maximizando el valor de la inversión y minimizando riesgos.
        - *Stakeholders:* CIO, directores de proyecto, arquitectos empresariales y analistas de negocio.
2. **Perspectivas con enfoque técnico (Technical Capabilities):**
    - **Perspectiva de Plataforma (Platform):** Incluye principios para describir la arquitectura del entorno en estado objetivo, aprovisionamiento de cómputo, red, almacenamiento y bases de datos.
        - *Stakeholders:* CTO, gerentes de TI y arquitectos de soluciones.
    - **Perspectiva de Seguridad (Security):** Garantiza que la organización cumpla con los objetivos de seguridad de visibilidad, auditabilidad, control y agilidad mediante la selección de controles adecuados.
        - *Stakeholders:* CISO, gerentes de seguridad de TI y analistas de seguridad.
    - **Perspectiva de Operaciones (Operations):** Define cómo se lleva a cabo el trabajo diario, trimestral y anual, alineando los procedimientos operativos con las necesidades del negocio.
        - *Stakeholders:* Gerentes de operaciones de TI y soporte de TI.

| Categoría | Perspectiva | Stakeholders Clave | Enfoque Principal |
| --- | --- | --- | --- |
| **Capacidades de Negocio** | **Negocio** | Gerentes de Finanzas, Estrategas | Alineación estratégica y ROI |
|  | **Personas** | Recursos Humanos, Managers | Capacitación y gestión del cambio |
|  | **Gobernanza** | CIO, Arquitectos Empresariales | Gestión de portafolio y licencias |
| **Capacidades Técnicas** | **Plataforma** | CTO, Arquitectos de Soluciones | Arquitectura de cómputo, red y almacenamiento |
|  | **Seguridad** | CISO, Analistas de Seguridad | Controles de identidad y protección de datos |
|  | **Operaciones** | Gerentes de Operaciones de TI | Monitoreo y continuidad del negocio |

#### Estrategias de migración de aplicaciones (Las 6 Rs)

Al migrar cargas de trabajo existentes a AWS, se utilizan 6 estrategias comunes:

1. **Rehost (Lift-and-Shift):** Mover aplicaciones a la nube sin realizar cambios arquitectónicos.
2. **Replatform (Lift-Tinker-and-Shift):** Hacer algunas optimizaciones básicas para obtener beneficios sin cambiar la arquitectura del núcleo de la aplicación.
3. **Repurchase (Drop-and-Shop):** Cambiar a un producto o modelo SaaS diferente.
4. **Refactor / Re-architect:** Rediseñar la aplicación aprovechando características nativas de la nube (ej. microservicios, serverless).
5. **Retain:** Mantener ciertas aplicaciones en el entorno On-premises por razones operativas o de dependencia.
6. **Retire:** Eliminar aplicaciones que ya no son necesarias ni aportan valor al negocio.

### 4. Ejemplos prácticos

Para consultar datos de descubrimiento de servidores durante la preparación de una migración mediante AWS CLI:

```
aws discovery describe-agents
```

**Explicación de la salida:**
Devuelve una lista estructurada en JSON con información de los agentes instalados en los servidores locales, indicando su identificador `agentId`, dirección IP, nombre de host y estado operativo (`HEALTHY`), lo que permite a la perspectiva de Plataforma catalogar los servidores a migrar.

**Escenario real:**
Una empresa financiera planea migrar a AWS. El departamento de Recursos Humanos utiliza la **Perspectiva de Personas** del AWS CAF para identificar la falta de conocimientos en la nube del personal y crea un programa de capacitación masivo en certificación AWS Cloud Practitioner antes de iniciar la migración.

### 5. Errores comunes y cómo evitarlos

- **Enfocar la adopción únicamente en la tecnología:** Ignorar a las personas y los procesos conduce a resistencias organizacionales y fallas en la adopción.
- **Confundir la Perspectiva de Negocio con la de Gobernanza:** Negocio se centra en finanzas y estrategia comercial; Gobernanza se centra en gestión de portafolio y licencias.
- **Tratar de refactorizar todas las aplicaciones en la primera fase:** Usar **Rehost** permite migraciones rápidas para reducir la huella física y posteriormente realizar **Refactor** en la nube.

### 6. Preguntas de práctica

1. ¿Qué perspectivas del AWS Cloud Adoption Framework (AWS CAF) se centran principalmente en las capacidades del negocio?
    - A) Plataforma, Seguridad y Operaciones
    - B) Negocio, Personas y Gobernanza
    - C) Negocio, Plataforma y Operaciones
    - D) Personas, Seguridad y Gobernanza
    *Respuesta correcta:* **B**. Las perspectivas de Negocio, Personas y Gobernanza abordan las capacidades organizacionales y comerciales.
2. ¿Qué stakeholder es el usuario principal de la perspectiva de Personas dentro del AWS CAF?
    - A) Director de Seguridad de la Información (CISO)
    - B) Gestores de Recursos Humanos y administradores de personal
    - C) Arquitectos de Soluciones y CTO
    - D) Administradores de base de datos
    *Respuesta correcta:* **B**. La perspectiva de Personas involucra a Recursos Humanos y líderes de personal para la gestión del cambio y entrenamiento.
3. Una empresa decide mover su servidor de base de datos a AWS exactamente como está configurado actualmente sin cambiar el sistema ni la arquitectura. ¿Qué estrategia de migración está utilizando?
    - A) Repurchase
    - B) Refactor
    - C) Rehost
    - D) Replatform
    *Respuesta correcta:* **C**. Rehost (conocido como *Lift-and-Shift*) implica mover la aplicación sin cambios a la nube.

### 7. Tarjetas rápidas / Flashcards

- **Pregunta:** ¿Cuáles son las 6 perspectivas del AWS CAF?
    - **Respuesta:** Negocio, Personas, Gobernanza, Plataforma, Seguridad y Operaciones.
- **Pregunta:** ¿A qué perspectiva del CAF corresponde el diseño de la arquitectura de destino y el aprovisionamiento de cómputo y red?
    - **Respuesta:** A la perspectiva de Plataforma.
- **Pregunta:** ¿Qué significa la estrategia de migración "Rehost"?
    - **Respuesta:** Migrar aplicaciones a la nube sin modificarlas (*Lift-and-Shift*).

### 8. Gancho mnemotécnico

Divide el CAF en dos grupos de 3:

> **Grupo Negocio:** **N-P-G** (**N**egocio, **P**ersonas, **G**obernanza)
> 
> 
> **Grupo Técnico:** **P-S-O** (**P**lataforma, **S**eguridad, **O**peraciones)
> 

---

## 1.4 Economía de la nube

### 1. Resumen rápido

La economía de la nube de AWS se basa en reemplazar costos fijos de capital por costos variables dinámicos, ofreciendo transparencia de precios y herramientas integradas para optimizar el **Costo Total de Propiedad (TCO)**.

### 2. Objetivos de aprendizaje

- Identificar los **tres factores fundamentales de costo** en AWS.
- Explicar la filosofía de precios de AWS y sus descuentos por reserva y volumen.
- Entender el concepto de **Costo Total de Propiedad (TCO)** y sus beneficios tangibles e intangibles.
- Conocer herramientas clave para estimación y análisis de costos como **AWS Pricing Calculator**, **AWS Budgets**, **AWS Cost Explorer** y **AWS Cost and Usage Report**.

### 3. Explicación detallada

#### Los tres factores impulsores de costo en AWS

A pesar de la variedad de servicios, la tarificación en AWS se basa principalmente en tres factores:

1. **Cómputo:** Se cobra generalmente por hora o por segundo según el tipo de instancia y sistema operativo.
2. **Almacenamiento:** Se cobra típicamente por gigabyte (GB) provisionado o utilizado.
3. **Transferencia de datos saliente:** La transferencia de datos **entrante** (Inbound) a AWS no tiene costo en la mayoría de los casos. La transferencia de datos **saliente** (Outbound) entre servicios de diferentes regiones o hacia Internet se acumula y se cobra por GB.

#### Filosofía de precios de AWS

- **Pague por lo que consume (Pay-as-you-go):** Permite pagar solo por los servicios que utiliza sin contratos a largo plazo.
- **Pague menos al reservar:** Permite reservar capacidad en servicios como **Amazon EC2** o **Amazon RDS** obteniendo hasta un 75% de descuento sobre tarifas bajo demanda:
    - *All Upfront Reserved Instance (AURI):* Mayor descuento pagando todo por adelantado.
    - *Partial Upfront Reserved Instance (PURI):* Descuento intermedio con pago parcial por adelantado.
    - *No Upfront Payments Reserved Instance (NURI):* Menor descuento sin pago inicial.
- **Pague menos usando más:** Descuentos por volumen escalonados en servicios como **Amazon S3**.
- **Pague aún menos a medida que AWS crece:** A medida que AWS escala e innova, traslada los ahorros operativos a los clientes reduciendo precios.

#### Costo Total de Propiedad (TCO) y Análisis Financiero

El **TCO** ayuda a estimar y comparar los costos directos e indirectos de ejecutar una infraestructura en las instalaciones locales (On-premises) frente a AWS.

- **Costos On-premises:** Incluye servidores, espacio físico de data center, electricidad, enfriamiento (HVAC), licenciamiento y personal de TI.
- **Beneficios Duros (Hard benefits):** Ahorros directos en hardware, software, mantenimiento y personal operativo.
- **Beneficios Blandos (Soft benefits):** Valor generado por la flexibilidad, productividad de los desarrolladores, agilidad empresarial y reducción del tiempo de comercialización.

| Característica | Centros de Datos Tradicionales (On-premises) | Nube de AWS |
| --- | --- | --- |
| **Modelo Financiero** | CapEx (Gastos de capital) | OpEx (Gastos variables) |
| **Planificación de Capacidad** | Adivinar picos máximos teóricos | Elasticidad basada en la demanda |
| **Transferencia de Datos** | Ancho de banda y líneas dedicadas fijas | Entrada gratis, salida por consumo |
| **Escalabilidad** | Lenta, requiere ciclo de compras | Inmediata (minutos) |

#### Herramientas de Gestión de Costos de AWS

- **AWS Pricing Calculator:** Herramienta web para estimar la factura mensual y modelar arquitecturas antes de construirlas.
- **AWS Billing Dashboard:** Muestra el estado del gasto mensual hasta la fecha y la previsión de costos.
- **AWS Cost Explorer:** Permite visualizar, comprender y gestionar costos e historial de uso durante los últimos 13 meses y pronosticar los próximos 3 meses.
- **AWS Budgets:** Permite definir presupuestos personalizados y enviar alertas por correo o **Amazon SNS** cuando se superen o se prevea superar el límite.
- **AWS Cost and Usage Report (CUR):** Proporciona la información más detallada de costos y uso desglosada por hora o por día enviada a un bucket de **Amazon S3**.

### 4. Ejemplos prácticos

#### Ejemplo de comando AWS CLI

Para consultar el costo y uso de la cuenta durante un periodo determinado usando AWS CLI:

```
aws ce get-cost-and-usage \
    --time-period Start=2026-08-01,End=2026-08-31 \
    --granularity MONTHLY \
    --metrics "UnblendedCost"
```

**Explicación de la salida:**
El comando consulta el servicio **AWS Cost Explorer** y devuelve un objeto JSON que detalla el costo total sin combinar (`UnblendedCost`) acumulado en el mes indicado, permitiendo realizar auditorías de gasto vía código.

#### Ejemplo numérico de cálculo de costos (On-Demand vs Reserved Instance)

Imagina que necesitas ejecutar una instancia EC2 `t3.medium` las 24 horas del día durante 1 año (8,760 horas):

- **Precio Bajo Demanda:** $0.0416 USD por hora.
    - *Costo anual Bajo Demanda:* \(8,760 \text{ horas} \times $0.0416 = $364.41 \text{ USD}\).
- **Precio Instancia Reservada (1 año All Upfront - AURI):** Supone un descuento del 40%.
    - *Costo anual Reservado:* \($364.41 \times (1 - 0.40) = $218.64 \text{ USD}\).
    - **Ahorro total:** \($145.77 \text{ USD}\) por instancia al año.

### 5. Errores comunes y cómo evitarlos

- **Creer que la transferencia de datos entrante tiene costo:** La transferencia de datos entrante (**Data Transfer IN**) es gratuita en la mayoría de los servicios.
- **No configurar presupuestos ni alertas:** Crear cuentas sin configurar **AWS Budgets** puede llevar a sorpresas financieras.
- **Pensar que los servicios gratuitos no generan cargos secundarios:** Servicios como **AWS CloudFormation** o **AWS Elastic Beanstalk** son gratuitos, pero los recursos que aprovisionan (como instancias EC2 o bases de datos RDS) sí se cobran.

### 6. Preguntas de práctica

1. ¿Cuál de los siguientes es un factor principal impulsor de costo en la nube de AWS?
    - A) La cantidad de reglas creadas en AWS IAM
    - B) La transferencia de datos entrante (Inbound)
    - C) La transferencia de datos saliente (Outbound)
    - D) La creación de esquemas en Amazon VPC
    *Respuesta correcta:* **C**. La transferencia de datos saliente se acumula y se cobra por gigabyte.
2. ¿Qué herramienta de AWS permite crear presupuestos personalizados para alertar cuando los costos superan o se pronostica que superarán los límites establecidos?
    - A) AWS Pricing Calculator
    - B) AWS Budgets
    - C) AWS Artifact
    - D) AWS Trusted Advisor
    *Respuesta correcta:* **B**. AWS Budgets permite configurar alertas sobre costos o uso real y pronosticado.
3. ¿Qué opción de compra de Instancias Reservadas ofrece el mayor descuento a cambio de realizar el pago total por adelantado?
    - A) Partial Upfront Reserved Instance (PURI)
    - B) No Upfront Payments Reserved Instance (NURI)
    - C) All Upfront Reserved Instance (AURI)
    - D) On-Demand Instance
    *Respuesta correcta:* **C**. AURI ofrece el descuento más elevado sobre el costo total al realizar un solo pago por adelantado.

### 7. Tarjetas rápidas / Flashcards

- **Pregunta:** ¿Cuáles son los tres impulsadores fundamentales de costo en AWS?
    - **Respuesta:** Cómputo, almacenamiento y transferencia de datos saliente.
- **Pregunta:** ¿Qué herramienta permite modelar y estimar los costos mensuales de una arquitectura antes de construirla?
    - **Respuesta:** AWS Pricing Calculator.
- **Pregunta:** ¿La transferencia de datos entrante hacia AWS tiene algún costo?
    - **Respuesta:** No, la transferencia de datos entrante es gratuita en la mayoría de los servicios.

### 8. Gancho mnemotécnico

Recuerda los pilares de precios de AWS con:

> **"P-R-V-G"** -> **P**aga lo usado, **R**eserva y ahorra, **V**olumen descuenta, **G**ana con AWS
> 
> 
> (**P**ay-as-you-go, **R**eservas, **V**olumen, **G**recimiento de AWS).
>