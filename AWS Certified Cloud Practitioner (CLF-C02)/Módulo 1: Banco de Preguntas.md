# Módulo 1: Conceptos de la nube

## 1.1 Beneficios de la nube de AWS

### Pregunta 1 (Opción múltiple)
Una empresa necesita desplegar una aplicación web orientada a usuarios en Asia, Europa y América con tiempos de respuesta mínimos. ¿Qué ventaja de la nube de AWS permite lograr este objetivo rápidamente?
- A) Aumentar la velocidad y agilidad
- B) Volverse global en minutos
- C) Cambiar gastos de capital por gastos operativos
- D) Dejar de adivinar la capacidad

**Respuesta correcta:** B

**Explicación breve:**
La ventaja de **volverse global en minutos** permite desplegar aplicaciones en múltiples Regiones de AWS alrededor del mundo con solo unos clics, reduciendo la latencia para los usuarios finales. La opción A se refiere al rápido aprovisionamiento de recursos de desarrollo; la C al modelo financiero; y la D a la flexibilidad de escalado.

---

### Pregunta 2 (Opción múltiple)
¿Qué concepto describe la capacidad de un sistema en la nube para ajustar automáticamente sus recursos informáticos en respuesta a fluctuaciones en la demanda en tiempo real?
- A) Escalabilidad
- B) Alta disponibilidad
- C) Elasticidad
- D) Tolerancia a fallos

**Respuesta correcta:** C

**Explicación breve:**
La **elasticidad** es la capacidad de aumentar o reducir recursos automáticamente según sea necesario para coincidir con la demanda real. La escalabilidad (A) es la capacidad de acomodar mayores cargas reforzando hardware o añadiendo nodos; la alta disponibilidad (B) y tolerancia a fallos (D) garantizan que el sistema permanezca operativo ante fallas.

---

### Pregunta 3 (Opción múltiple)
¿Cuál es un beneficio directo de sustituir los gastos de capital (CapEx) por gastos operativos variables (OpEx) en AWS?
- A) AWS asume la responsabilidad total de las configuraciones de seguridad del cliente.
- B) Las organizaciones pagan únicamente por los recursos informáticos consumidos sin realizar inversiones iniciales en hardware.
- C) Los costos de transferencia de datos de salida se vuelven completamente gratuitos.
- D) Se eliminan los contratos de soporte técnico.

**Respuesta correcta:** B

**Explicación breve:**
Cambiar CapEx por OpEx implica pagar bajo demanda por lo que se utiliza en lugar de invertir capital por adelantado en la compra de centros de datos y servidores físicos. La opción A contradice el modelo de responsabilidad compartida; la C es falsa ya que la transferencia de datos hacia afuera tiene costo; y la D no está relacionada.

---

### Pregunta 4 (Opción múltiple)
¿Qué beneficio de AWS permite a las startups probar rápidamente nuevas ideas de negocios aprovisionando servidores en cuestión de segundos?
- A) Economías de escala masivas
- B) Alta disponibilidad
- C) Aumentar la velocidad y la agilidad
- D) Replicación entre regiones

**Respuesta correcta:** C

**Explicación breve:**
Aumentar la velocidad y la agilidad permite que los recursos tecnológicos estén disponibles para los desarrolladores en minutos en lugar de semanas, facilitando la experimentación rápida y la innovación. Las economías de escala (A) reducen precios; la alta disponibilidad (B) evita caídas; y la replicación (D) es un mecanismo de resiliencia.

---

### Pregunta 5 (Opción múltiple)
Una organización desea reducir los costos derivados del mantenimiento físico, aire acondicionado y electricidad de sus propios centros de datos. ¿Qué ventaja de la nube de AWS aborda directamente esta necesidad?
- A) Dejar de gastar dinero en el funcionamiento y mantenimiento de centros de datos
- B) Volverse global en minutos
- C) Descuentos por uso reservado
- D) Arquitecturas desacopladas

**Respuesta correcta:** A

**Explicación breve:**
AWS se encarga de administrar y mantener el hardware físico y la infraestructura de los centros de datos, lo que permite a los clientes enfocar sus recursos financieros y humanos en proyectos de negocio. Las demás opciones son características técnicas o financieras diferentes.

---

### Pregunta 6 (Opción múltiple)
¿Cómo ayuda AWS a resolver el problema de adivinar las necesidades de capacidad de infraestructura?
- A) Obligando a comprar servidores físicos con margen de exceso del 50%.
- B) Permitiendo escalar los recursos automáticamente hacia arriba o hacia abajo según el uso real medido.
- C) Asignando capacidades fijas e inmutables durante contratos anuales.
- D) Generando reportes predictivos que previenen todo tipo de tráfico inusual.

**Respuesta correcta:** B

**Explicación breve:**
En la nube de AWS se elimina la adivinación de la capacidad porque los recursos se escalan elásticamente según la demanda real del tráfico. Forzar compras (A) o fijar capacidades (C) representa el modelo tradicional On-Premises.

---

### Pregunta 7 (Opción múltiple)
¿Qué característica de la infraestructura global de AWS garantiza que los recursos desplegados en una Zona de Disponibilidad (AZ) estén protegidos frente a desastres físicos que afecten a otra zona?
- A) Aislamiento físico y redes independientes de energía y conectividad entre AZs.
- B) Compartición de la misma fuente de energía eléctrica entre todas las AZs de una Región.
- C) Ubicación de todas las AZs en un mismo edificio central.
- D) Conexión exclusiva a través de Internet público sin fibra dedicada.

**Respuesta correcta:** A

**Explicación breve:**
Cada Zona de Disponibilidad (AZ) consta de uno o varios centros de datos discretos equipados con energía, enfriamiento y conectividad independientes, situados a una distancia física que los aísla de desastres comunes. Las opciones B y C romperían la tolerancia a fallas.

---

### Pregunta 8 (Opción múltiple)
¿Qué término describe un entorno informático que combina infraestructura física local (On-Premises) con servicios en la nube pública de AWS?
- A) Nube privada pura
- B) Nube híbrida
- C) Infraestructura Serverless
- D) Multisitio en caliente

**Respuesta correcta:** B

**Explicación breve:**
El modelo de **nube híbrida** permite a las empresas mantener ciertos activos o datos sensibles en servidores locales mientras extienden sus capacidades con la flexibilidad de la nube pública. La nube privada (A) no utiliza servicios públicos; Serverless (C) es un paradigma de cómputo.

---

### Pregunta 9 (Opción múltiple)
¿Cuál es la función principal de las ubicaciones de borde (Edge Locations) dentro de la infraestructura global de AWS?
- A) Ejecutar bases de datos relacionales de producción.
- B) Almacenar copias de seguridad de larga duración.
- C) Entregar contenido con menor latencia a los usuarios finales mediante caché local.
- D) Alojar la Consola de Administración de AWS.

**Respuesta correcta:** C

**Explicación breve:**
Las ubicaciones de borde (Edge Locations) forman parte de la red global de entrega de contenido (como Amazon CloudFront) y sirven datos en caché cerca de los usuarios finales para minimizar la latencia.

---

### Pregunta 10 (Opción múltiple)
¿Qué beneficio se logra cuando los precios de AWS disminuyen debido a la compra masiva de infraestructura por parte de millones de clientes?
- A) Elasticidad vertical
- B) Economías de escala masivas
- C) Precios fijos por suscripción
- D) Autoservicio bajo demanda

**Respuesta correcta:** B

**Explicación breve:**
Gracias al uso acumulado de cientos de miles de clientes, AWS logra ahorros operativos de gran escala que se traducen en reducciones continuas de precios para los usuarios.

---

### Pregunta 11 (Opción múltiple)
¿Qué característica de la computación en la nube permite a los usuarios aprovisionar servidores y almacenamiento de forma autónoma sin requerir intervención humana del proveedor?
- A) Amplio acceso a la red
- B) Autoservicio bajo demanda
- C) Agrupación de recursos
- D) Tolerancia a fallos por defecto

**Respuesta correcta:** B

**Explicación breve:**
El **autoservicio bajo demanda** (*On-demand self-service*) permite a los usuarios aprovisionar capacidades informáticas (como tiempo de servidor o almacenamiento) automáticamente sin interacción humana con AWS.

---

### Pregunta 12 (Opción múltiple)
¿Cuál es la diferencia fundamental entre escalabilidad e hiper-elasticidad en la nube?
- A) La escalabilidad requiere apagar los servidores; la elasticidad no.
- B) La escalabilidad aumenta la capacidad para absorber cargas mayores; la elasticidad incrementa o reduce recursos automáticamente adaptándose a la demanda cambiante.
- C) La elasticidad solo aplica a bases de datos; la escalabilidad solo a redes.
- D) No existe diferencia; ambos términos significan exactamente lo mismo.

**Respuesta correcta:** B

**Explicación breve:**
La escalabilidad permite acomodar mayores volúmenes de trabajo añadiendo potencia o nodos, mientras que la elasticidad enfatiza la capacidad dinámica de reducir o aumentar recursos en tiempo real según la demanda medida.

---

### Pregunta 13 (Respuesta múltiple - SELECCIONA DOS)
¿Cuáles de las siguientes opciones son ventajas clave de la computación en la nube de AWS? (Selecciona dos)
- A) Intervención manual obligatoria para cada actualización de software.
- B) Beneficiarse de economías de escala masivas.
- C) Reemplazar gastos operativos por inversiones de capital fijas.
- D) Aumentar la velocidad y la agilidad en la entrega de aplicaciones.
- E) Garantía de costo cero en todos los servicios de almacenamiento.

**Respuestas correctas:** B y D

**Explicación breve:**
Las 6 ventajas del cloud incluyen beneficiarse de economías de escala masivas (B) y aumentar la velocidad y agilidad (D). La C es incorrecta porque se cambia CapEx por OpEx; la A contradice la automatización y autoservicio.

---

### Pregunta 14 (Respuesta múltiple - SELECCIONA DOS)
¿Qué características definen a una Zona de Disponibilidad (AZ) de AWS? (Selecciona dos)
- A) Consta de uno o varios centros de datos discretos con alimentación y conectividad redundantes.
- B) Se encuentra ubicada dentro de la misma instalación física que las demás AZs de la Región.
- C) Está conectada con otras AZs de la misma Región mediante redes de latencia ultrabaja.
- D) Representa un punto de presencia exclusivo para la entrega de correos con SES.
- E) Es compartida de forma idéntica entre todas las cuentas de AWS sin aislamiento.

**Respuestas correctas:** A y C

**Explicación breve:**
Cada AZ está compuesta por uno o varios centros de datos aislados (A) e interconectados entre sí dentro de la Región mediante redes redundantes de alto ancho de banda y latencia ultrabaja (C).

---

### Pregunta 15 (Respuesta múltiple - SELECCIONA DOS)
¿Cuáles son dos de los tres fundamentos principales de precios en el modelo de pago por uso de AWS? (Selecciona dos)
- A) Tiempo de cómputo consumido.
- B) Solicitudes de soporte técnico enviadas.
- C) Almacenamiento de datos mantenido en la nube.
- D) Transferencia de datos entrante (Data Transfer IN).
- E) Número de usuarios creados en la consola de IAM.

**Respuestas correctas:** A y C

**Explicación breve:**
Los 3 fundamentos de cobro en AWS son: Cómputo (A), Almacenamiento (C) y Transferencia de datos SALIENTE (Data Transfer OUT). La transferencia entrante (D) es gratuita.

---

## 1.2 Principios de diseño (Well-Architected)

### Pregunta 16 (Opción múltiple)
¿Cuál pilar del AWS Well-Architected Framework se centra en la capacidad de ejecutar sistemas para ofrecer valor empresarial al precio más bajo posible?
- A) Eficiencia del rendimiento
- B) Sostenibilidad
- C) Optimización de costos
- D) Excelencia operativa

**Respuesta correcta:** C

**Explicación breve:**
El pilar de **Optimización de costos** (*Cost Optimization*) se enfoca en ejecutar sistemas con la máxima eficiencia financiera y al precio más bajo de operación.

---

### Pregunta 17 (Opción múltiple)
¿Qué principio de diseño corresponde al pilar de Seguridad del AWS Well-Architected Framework?
- A) Utilizar arquitecturas sin servidor por defecto.
- B) Mantener a las personas alejadas de los datos.
- C) Maximizar la utilización de hardware físico.
- D) Adoptar un modo de consumo.

**Respuesta correcta:** B

**Explicación breve:**
Reducir o eliminar la necesidad de acceso directo o manual de las personas a los datos de producción es un principio clave del pilar de Seguridad para reducir riesgos de errores o accesos no autorizados. La A pertenece a Rendimiento; la C a Sostenibilidad; y la D a Optimización de Costos.

---

### Pregunta 18 (Opción múltiple)
¿Qué herramienta disponible en la consola de AWS permite a los clientes evaluar el estado de sus cargas de trabajo en comparación con las mejores prácticas del Well-Architected Framework?
- A) AWS Trusted Advisor
- B) AWS Well-Architected Tool
- C) AWS Compute Optimizer
- D) AWS Service Catalog

**Respuesta correcta:** B

**Explicación breve:**
La **AWS Well-Architected Tool** es una herramienta gratuita en la consola que guía al usuario mediante un cuestionario sobre los 6 pilares para identificar riesgos y generar planes de mejora.

---

### Pregunta 19 (Opción múltiple)
Un arquitecto de soluciones está diseñando un sistema que utiliza grupos de Auto Scaling y balanceadores de carga para absorber fallas en instancias EC2 sin interrumpir el servicio. ¿A qué pilar contribuye principalmente esta práctica?
- A) Fiabilidad
- B) Excelencia operativa
- C) Sostenibilidad
- D) Optimización de costos

**Respuesta correcta:** A

**Explicación breve:**
El pilar de **Fiabilidad** (*Reliability*) abarca la capacidad de un sistema para recuperarse de interrupciones de infraestructura, adquirir recursos dinámicamente para satisfacer la demanda y mitigar fallas.

---

### Pregunta 20 (Opción múltiple)
¿Qué principio de diseño general de arquitectura recomienda dividir las aplicaciones monolíticas grandes en componentes pequeños y débilmente acoplados?
- A) Servicios, no servidores
- B) Acoplamiento débil (Loose coupling)
- C) Recursos desechables
- D) Simpatía mecánica

**Respuesta correcta:** B

**Explicación breve:**
El **desacoplamiento débil** garantiza que un cambio o falla en un componente no afecte en cascada a los demás componentes del sistema.

---

### Pregunta 21 (Opción múltiple)
¿Qué pilar del Well-Architected Framework se enfoca en minimizar el impacto medioambiental derivado de la ejecución de cargas de trabajo en la nube?
- A) Eficiencia del rendimiento
- B) Sostenibilidad
- C) Excelencia operativa
- D) Seguridad

**Respuesta correcta:** B

**Explicación breve:**
El pilar de **Sostenibilidad** (*Sustainability*) busca reducir el consumo energético y la huella ecológica general mediante la optimización de recursos e infraestructura en la nube.

---

### Pregunta 22 (Opción múltiple)
¿Cuál es un principio de diseño clave dentro del pilar de Excelencia Operativa?
- A) Realizar operaciones como código.
- B) Maximizar el acceso de superusuario para acelerar cambios.
- C) Evitar automatizaciones para mantener control manual directo.
- D) Mantener arquitecturas rígidas e inmutables.

**Respuesta correcta:** A

**Explicación breve:**
En la excelencia operativa, definir la infraestructura y los procedimientos de operaciones como código (por ejemplo, con AWS CloudFormation) permite automatizar procesos, reducir errores humanos y probar cambios de forma segura.

---

### Pregunta 23 (Opción múltiple)
¿Qué servicio apoya directamente al pilar de Seguridad mediante la centralización de credenciales y la aplicación del principio de menor privilegio?
- A) Amazon S3
- B) AWS IAM
- C) AWS Auto Scaling
- D) Amazon Route 53

**Respuesta correcta:** B

**Explicación breve:**
**AWS Identity and Access Management (IAM)** permite gestionar usuarios, roles y permisos centralizados aplicando el principio de menor privilegio, pilar fundamental de la seguridad en AWS.

---

### Pregunta 24 (Opción múltiple)
Un equipo técnico utiliza **AWS Graviton** y autoescalado elástico para reducir el gasto energético y ajustar la capacidad exacta de cómputo. ¿Qué pilar están fortaleciendo explícitamente?
- A) Excelencia operativa
- B) Sostenibilidad
- C) Seguridad
- D) Fiabilidad

**Respuesta correcta:** B

**Explicación breve:**
El uso de procesadores eficientes como Graviton y el autoescalado para eliminar capacidad ociosa son prácticas destacadas en las guías del pilar de Sostenibilidad.

---

### Pregunta 25 (Opción múltiple)
¿Qué principio del pilar de Eficiencia del rendimiento alienta a utilizar arquitecturas Serverless en lugar de administrar servidores virtuales directamente?
- A) Democratizar las tecnologías avanzadas
- B) Utilizar arquitecturas sin servidor (Serverless)
- C) Experimentar más a menudo
- D) Simpatía mecánica

**Respuesta correcta:** B

**Explicación breve:**
El principio de **utilizar arquitecturas sin servidor** elimina la carga operativa de gestionar y mantener servidores, permitiendo centrarse en la lógica de negocio con mayor rendimiento.

---

### Pregunta 26 (Opción múltiple)
¿Qué pilar incluye el principio de "Habilitar la trazabilidad" mediante la integración de logs y métricas con CloudTrail y CloudWatch?
- A) Seguridad
- B) Sostenibilidad
- C) Optimización de costos
- D) Eficiencia del rendimiento

**Respuesta correcta:** A

**Explicación breve:**
Integrar registros, monitoreo y auditorías automáticas (trazabilidad) para responder a eventos es un principio fundamental del pilar de Seguridad.

---

### Pregunta 27 (Opción múltiple)
¿Qué concepto promueve que los servidores en la nube deben ser tratados como recursos temporales y fácilmente reemplazables mediante scripts de automatización?
- A) Servicios, no servidores
- B) Recursos desechables (Disposable resources)
- C) Acoplamiento monolítico
- D) Replicación síncrona

**Respuesta correcta:** B

**Explicación breve:**
Tratar a los servidores como **recursos desechables** implica que cualquier instancia puede destruirse y reconstruirse automáticamente de forma consistente mediante código.

---

### Pregunta 28 (Respuesta múltiple - SELECCIONA DOS)
¿Cuáles de los siguientes son pilares del AWS Well-Architected Framework? (Selecciona dos)
- A) Disponibilidad continua
- B) Excelencia operativa
- C) Portabilidad de licencias
- D) Sostenibilidad
- E) Transparencia financiera total

**Respuestas correctas:** B y D

**Explicación breve:**
Los 6 pilares son: Excelencia Operativa, Seguridad, Fiabilidad, Eficiencia del Rendimiento, Optimización de Costos y Sostenibilidad.

---

### Pregunta 29 (Respuesta múltiple - SELECCIONA DOS)
¿Cuáles de las siguientes opciones representan principios de diseño del pilar de Optimización de costos? (Selecciona dos)
- A) Adoptar un modo de consumo.
- B) Escalar siempre de forma vertical.
- C) Analizar y atribuir el gasto mediante etiquetas (tags).
- D) Mantener todas las instancias en tamaño máximo por prevención.
- E) Desactivar las métricas de monitoreo de CloudWatch.

**Respuestas correctas:** A y C

**Explicación breve:**
El pilar de Optimización de costos recomienda pagar solo por lo que se usa (A) y categorizar los gastos mediante etiquetas para medir el retorno de inversión (C).

---

### Pregunta 30 (Respuesta múltiple - SELECCIONA DOS)
¿Qué prácticas contribuyen al pilar de Fiabilidad en AWS? (Selecciona dos)
- A) Probar los procedimientos de recuperación ante fallas mediante simulaciones.
- B) Utilizar una única Zona de Disponibilidad para centralizar datos.
- C) Escalar horizontalmente para aumentar la disponibilidad agregada.
- D) Guardar credenciales de acceso directo en el código fuente.
- E) Desactivar las copias de seguridad automáticas para ahorrar ancho de banda.

**Respuestas correctas:** A y C

**Explicación breve:**
Probar la recuperación simulando fallas y escalar horizontalmente añadiendo nodos distribuidos refuerzan la fiabilidad y resiliencia de los sistemas.

---

## 1.3 Estrategias de migración (AWS CAF)

### Pregunta 31 (Opción múltiple)
¿Cuál es el propósito principal del AWS Cloud Adoption Framework (AWS CAF)?
- A) Reemplazar la necesidad de contratar ingenieros de software.
- B) Ayudar a las organizaciones a construir y ejecutar un plan integral para su transformación digital en la nube.
- C) Generar presupuestos automáticos de facturación consolidada.
- D) Auditar únicamente el código fuente de aplicaciones Python.

**Respuesta correcta:** B

**Explicación breve:**
El **AWS CAF** identifica capacidades organizativas específicas y ofrece mejores prácticas para ayudar a las empresas a planificar y ejecutar con éxito su transformación digital.

---

### Pregunta 32 (Opción múltiple)
¿Cuántas perspectivas organizacionales agrupa el marco AWS Cloud Adoption Framework (AWS CAF)?
- A) 4
- B) 5
- C) 6
- D) 8

**Respuesta correcta:** C

**Explicación breve:**
El AWS CAF organiza sus capacidades en **6 perspectivas**: Negocio, Personas, Gobernanza, Plataforma, Seguridad y Operaciones.

---

### Pregunta 33 (Opción múltiple)
¿Qué perspectiva del AWS CAF se enfoca en la arquitectura de datos, la ingeniería de plataforma y el aprovisionamiento de componentes de infraestructura tecnológica?
- A) Gobernanza
- B) Plataforma
- C) Personas
- D) Negocio

**Respuesta correcta:** B

**Explicación breve:**
La perspectiva de **Plataforma** (*Platform*) abarca las capacidades técnicas como la arquitectura de solución, provisión de cómputo, almacenamiento, redes y bases de datos.

---

### Pregunta 34 (Opción múltiple)
Una empresa necesita migrar petabytes de datos locales hacia Amazon S3, pero su conexión a Internet tiene un ancho de banda muy limitado. ¿Qué servicio físico de AWS es el más adecuado?
- A) AWS Direct Connect
- B) AWS Snowball
- C) AWS Application Migration Service
- D) Amazon Storage Gateway

**Respuesta correcta:** B

**Explicación breve:**
**AWS Snowball** es un dispositivo físico seguro de almacenamiento que permite transferir grandes volúmenes de datos (petabytes) hacia y desde AWS de forma física, eludiendo las limitaciones de ancho de banda de red.

---

### Pregunta 35 (Opción múltiple)
¿Qué servicio de AWS facilita la migración de bases de datos relacionales o NoSQL hacia AWS de forma continua y con un tiempo de inactividad mínimo?
- A) AWS DMS (Database Migration Service)
- B) AWS Snowcone
- C) AWS Artifact
- D) AWS Glue

**Respuesta correcta:** A

**Explicación breve:**
**AWS DMS** permite migrar bases de datos hacia AWS rápidamente y de forma segura, manteniendo la base de datos de origen funcional durante la migración para minimizar el impacto en las aplicaciones.

---

### Pregunta 36 (Opción múltiple)
¿Qué perspectiva del AWS CAF ayuda a garantizar que los servicios en la nube se presten satisfaciendo las necesidades del negocio mediante la observabilidad y gestión de incidentes?
- A) Operaciones
- B) Negocio
- C) Personas
- D) Plataforma

**Respuesta correcta:** A

**Explicación breve:**
La perspectiva de **Operaciones** (*Operations*) se enfoca en mantener, monitorear y operar los servicios en la nube para garantizar que se cumplan los niveles de servicio acordados.

---

### Pregunta 37 (Opción múltiple)
En las fases de transformación del AWS CAF, ¿qué fase se centra en construir iniciativas piloto en producción para demostrar valor de negocio incremental?
- A) Envision
- B) Align
- C) Launch
- D) Scale

**Respuesta correcta:** C

**Explicación breve:**
La fase **Launch** busca crear y entregar proyectos piloto o pruebas de concepto en producción que demuestren beneficios tangibles para el negocio.

---

### Pregunta 38 (Opción múltiple)
¿Qué estrategia de migración (de las 6 R's) implica trasladar aplicaciones a la nube sin realizar cambios en su arquitectura ("Lift and Shift")?
- A) Rehost
- B) Refactor
- C) Repurchase
- D) Retain

**Respuesta correcta:** A

**Explicación breve:**
**Rehost** (también conocida como "Lift and Shift") consiste en migrar aplicaciones tal como están hacia instancias de la nube sin realizar optimizaciones ni cambios de código.

---

### Pregunta 39 (Respuesta múltiple - SELECCIONA DOS)
¿Cuáles de las siguientes corresponden a perspectivas dentro del marco AWS Cloud Adoption Framework (AWS CAF)? (Selecciona dos)
- A) Gobernanza
- B) Almacenamiento
- C) Personas
- D) Redes
- E) Cómputo

**Respuestas correctas:** A y C

**Explicación breve:**
Las 6 perspectivas del CAF son: Negocio, Personas, Gobernanza, Plataforma, Seguridad y Operaciones.

---

### Pregunta 40 (Respuesta múltiple - SELECCIONA DOS)
¿Qué herramientas o servicios de AWS facilitan el proceso de migración de datos y servidores desde entornos On-Premises hacia AWS? (Selecciona dos)
- A) AWS Snowball
- B) Amazon Route 53
- C) AWS Database Migration Service (AWS DMS)
- D) Amazon QuickSight
- E) AWS CodeDeploy

**Respuestas correctas:** A y C

**Explicación breve:**
AWS Snowball (A) permite mover volúmenes masivos de archivos físicamente, mientras que AWS DMS (C) migra bases de datos con replicación continua.

---

## 1.4 Economía de la nube

### Pregunta 41 (Opción múltiple)
¿Qué herramienta web gratuita de AWS permite a los usuarios modelar y estimar el costo total de una solución antes de construirla o desplegarla?
- A) AWS Cost Explorer
- B) AWS Pricing Calculator
- C) AWS Budgets
- D) AWS Billing Dashboard

**Respuesta correcta:** B

**Explicación breve:**
La **AWS Pricing Calculator** es una herramienta interactiva que permite calcular estimaciones de costos mensuales para arquitecturas hipotéticas en AWS antes de crear los recursos.

---

### Pregunta 42 (Opción múltiple)
¿Qué proceso consiste en analizar las instancias EC2 activas para ajustar su tamaño al tipo y capacidad mínima requerida sin comprometer el rendimiento?
- A) Replicación geográfica
- B) Dimensionamiento correcto (Right-sizing)
- C) Acoplamiento rígido
- D) Desacoplamiento Serverless

**Respuesta correcta:** B

**Explicación breve:**
El **dimensionamiento correcto** (*Right-sizing*) es el proceso de adecuar los tipos y tamaños de recursos a los requisitos reales de rendimiento al menor costo posible.

---

### Pregunta 43 (Opción múltiple)
¿Qué servicio de AWS utiliza aprendizaje automático para analizar métricas de uso de CloudWatch y recomendar la configuración óptima para reducir costos hasta un 25%?
- A) AWS Compute Optimizer
- B) AWS Trusted Advisor
- C) AWS Pricing Calculator
- D) AWS Service Catalog

**Respuesta correcta:** A

**Explicación breve:**
**AWS Compute Optimizer** analiza métricas históricas de rendimiento en CloudWatch con Machine Learning para recomendar configuraciones y tamaños ideales de instancias EC2, volúmenes EBS y Lambda.

---

### Pregunta 44 (Opción múltiple)
¿Qué modelo de licencia de software permite a los clientes trasladar sus licencias preexistentes On-Premises hacia instancias en la nube de AWS?
- A) Pay-as-you-go
- B) Bring Your Own License (BYOL)
- C) License On-Demand
- D) Open Source Free

**Respuesta correcta:** B

**Explicación breve:**
El modelo **BYOL** (*Bring Your Own License*) permite reutilizar licencias de software existentes del cliente (como Windows Server o SQL Server) en instancias de AWS (como Dedicated Hosts), optimizando costos.

---

### Pregunta 45 (Opción múltiple)
¿Qué sucede con los costos unitarios de procesamiento e infraestructura en AWS a medida que aumenta la adopción masiva por parte de millones de clientes?
- A) Aumentan para compensar el uso de ancho de banda.
- B) Permanecen estáticos e inmutables por norma legal.
- C) Disminuyen debido a las economías de escala masivas que logra AWS.
- D) Se vuelven impredecibles mes con mes.

**Respuesta correcta:** C

**Explicación breve:**
A medida que AWS escala su infraestructura global para millones de usuarios, obtiene eficiencias operativas que le permiten reducir periódicamente los precios de sus servicios.

---

### Pregunta 46 (Opción múltiple)
¿Cuál de los siguientes es un costo variable típico en la economía de la nube de AWS?
- A) Compra de racks y gabinetes para data centers.
- B) Pago por la cantidad de gigabytes transferidos hacia fuera de la nube (Data Transfer OUT).
- C) Contratos de arrendamiento a 10 años para edificios físicos.
- D) Salarios fijos del personal de mantenimiento de generadores eléctricos de AWS.

**Respuesta correcta:** B

**Explicación breve:**
En AWS, la transferencia de datos hacia afuera (*Data Transfer OUT*) se cobra de forma variable según los gigabytes reales consumidos cada mes.

---

### Pregunta 47 (Opción múltiple)
¿Qué práctica financiera permite etiquetar recursos con valores como "CentroDeCostos" o "Proyecto" para atribuir y desglosar el gasto detalladamente?
- A) Etiquetas de asignación de costos (Cost Allocation Tags)
- B) Certificados SSL en ACM
- C) Reglas de grupos de seguridad
- D) Tablas de ruteo de VPC

**Respuesta correcta:** A

**Explicación breve:**
Las **etiquetas de asignación de costos** (*Cost Allocation Tags*) permiten organizar y realizar un seguimiento preciso de los cargos de AWS por proyectos, departamentos o entornos en los informes financieros.

---

### Pregunta 48 (Opción múltiple)
¿Qué herramienta de AWS permite visualizar el historial de costos actual con filtros detallados y proyectar los gastos futuros a 12 meses?
- A) AWS Cost Explorer
- B) AWS Pricing Calculator
- C) AWS Service Quotas
- D) AWS Organizations

**Respuesta correcta:** A

**Explicación breve:**
**AWS Cost Explorer** ofrece una interfaz gráfica para analizar patrones de gasto pasados, filtrar el uso y generar pronósticos de costos futuros.

---

### Pregunta 49 (Respuesta múltiple - SELECCIONA DOS)
¿Qué herramientas de AWS apoyan directamente el proceso continuo de dimensionamiento correcto (*Right-sizing*) de recursos? (Selecciona dos)
- A) AWS Compute Optimizer
- B) AWS Trusted Advisor
- C) AWS Artifact
- D) AWS Shield Standard
- E) AWS KMS

**Respuestas correctas:** A y B

**Explicación breve:**
Tanto AWS Compute Optimizer como AWS Trusted Advisor analizan recursos sobreprovisionados o subutilizados y emiten sugerencias para ajustar su tamaño.

---

### Pregunta 50 (Respuesta múltiple - SELECCIONA DOS)
¿Cuáles de las siguientes afirmaciones representan buenas prácticas para la optimización de costos en AWS? (Selecciona dos)
- A) Iniciar siempre las arquitecturas utilizando los tipos de instancias EC2 más grandes disponibles.
- B) Detener o eliminar recursos no utilizados en entornos de desarrollo durante horarios no laborales.
- C) Realizar un dimensionamiento correcto (*Right-sizing*) antes y después de migrar a la nube.
- D) Evitar el uso de etiquetas en los recursos para simplificar la consola.
- E) Comprar siempre capacidad física fija para el máximo pico esperado a 5 años.

**Respuestas correctas:** B y C

**Explicación breve:**
Automatizar la eliminación/apagado de recursos en horarios ociosos (B) y aplicar el dimensionamiento correcto antes y después de la migración (C) son estrategias clave para la eficiencia económica.