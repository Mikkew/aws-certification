#  Módulo 1: Experiencias prácticas en la nube

## 1.1 Beneficios de la nube de AWS
- **Laboratorio:** Crear un bucket S3, subir un archivo y verificar disponibilidad global.
- **Paso a paso:** Acceso a la consola, creación de bucket, carga de archivo y prueba de acceso público.

### 1. Objetivo del laboratorio
Comprobar de forma práctica las ventajas fundamentales de la computación en la nube de AWS: **volverse global en minutos**, **eliminar la adivinación de la capacidad** y cambiar el **gasto de capital (CapEx)** por un **gasto operativo variable (OpEx)**. Al finalizar, aprenderás a aprovisionar almacenamiento elástico en **Amazon S3**, configurar permisos de acceso y verificar la disponibilidad del objeto desde cualquier parte del mundo a través de la infraestructura global de AWS.

### 2. Instrucciones paso a paso

#### Paso 1: Acceso a la consola y navegación hacia Amazon S3
1. Inicia sesión en la **Consola de administración de AWS** con tus credenciales.
2. En la barra de búsqueda superior, escribe `S3` y selecciona el servicio **S3** (Almacenamiento de objetos escalable en la nube).

#### Paso 2: Creación del bucket de Amazon S3
1. En el panel principal de Amazon S3, haz clic en el botón **Crear bucket**.
2. En **Nombre del bucket**, ingresa un nombre único a nivel global (por ejemplo: `lab-clf-c02-mexico-2026`).
3. En **Región de AWS**, selecciona una región geográficamente conveniente, como `EE. UU. Este (N. Virginia) us-east-1`.
4. En la sección **Configuración de bloqueo de acceso público para este bucket**, desmarca la opción **Bloquear *todo* el acceso público**.
5. Marca la casilla de verificación requerida para confirmar que comprendes que los recursos pueden volverse públicos.
6. Mantén las demás opciones predeterminadas (cifrado por defecto activado) y haz clic en **Crear bucket**.

#### Paso 3: Carga de un archivo al bucket
1. En la lista de buckets, selecciona el nombre del bucket recién creado (`lab-clf-c02-mexico-2026`).
2. Haz clic en el botón **Cargar** y luego en **Agregar archivos**.
3. Selecciona un archivo de prueba local (por ejemplo, una imagen `demo.png` o un documento `index.html`).
4. Despliega la sección **Permisos** y en *Conceder acceso público*, otorga permiso de **Lectura** para el objeto (o bien, una vez subido el archivo, selecciónalo en la lista y en *Acciones de objetos* elige **Hacer público mediante ACL**).
5. Haz clic en el botón **Cargar**.

#### Paso 4: Prueba de acceso público y verificación global
1. Abre tu terminal local o **AWS CloudShell** y ejecuta el siguiente comando con la **AWS CLI** para listar el contenido del bucket:
   ```bash
   aws s3 ls s3://lab-clf-c02-mexico-2026/
   ```
   *Explicación de la salida:* Devuelve la fecha de carga, el tamaño en bytes y el nombre del archivo registrado, confirmando que el objeto reside en el almacenamiento de objetos de AWS.
2. Regresa a la consola web de Amazon S3, selecciona el archivo cargado y copia la **URL del objeto** (formato: `https://lab-clf-c02-mexico-2026.s3.amazonaws.com/demo.png`).
3. Abre una ventana de navegador en modo incógnito o ejecuta el comando `curl` desde tu terminal:
   ```bash
   curl -I https://lab-clf-c02-mexico-2026.s3.amazonaws.com/demo.png
   ```
   *Explicación de la salida:* Se recibe una respuesta HTTP `200 OK`, demostrando que el archivo está publicado y disponible de forma inmediata a nivel mundial.

---

### 3. Resultado esperado
Comprobarás que el archivo almacenado en Amazon S3 se sirve globalmente a través de Internet sin necesidad de adquirir hardware físico, aprovisionar servidores web ni estimar la capacidad de disco por adelantado.

---

### 4. Errores comunes y cómo evitarlos
1. **Conflicto por nombre de bucket duplicado:** Intentar usar un nombre de bucket que ya utiliza otra cuenta en el mundo. *Solución:* Añade un prefijo o sufijo único con la fecha o tus iniciales.
2. **Error HTTP `403 AccessDenied`:** Ocurre cuando la opción *Bloquear todo el acceso público* continúa activa en el bucket o el objeto no fue configurado con permisos de lectura pública. *Solución:* Verifica los permisos tanto a nivel de bucket como en las ACLs del objeto.
3. **Mala interpretación de los costos de transferencia:** Suponer que la carga de archivos genera cargos por datos entrantes. *Solución:* Recuerda que la transferencia de datos **hacia adentro** (*Data Transfer IN*) a AWS es gratuita; solo se factura la transferencia de datos **hacia afuera** (*Data Transfer OUT*).
4. **Dejar recursos públicos sin supervisión:** Mantener buckets públicos expone datos innecesariamente. *Solución:* Elimina el objeto y el bucket al concluir la práctica para seguir buenas prácticas de seguridad.

---

### 5. Preguntas de reflexión
1. ¿De qué manera el aprovisionamiento de este bucket en S3 refleja el beneficio de la nube de *"Aumentar la velocidad y la agilidad"* frente a la instalación de servidores físicos On-premises?
2. ¿Por qué el modelo de cobro basado en los gigabytes almacenados en S3 ejemplifica la transición de gastos de capital (CapEx) a gastos operativos variables (OpEx)?

---

### 6. Flashcards rápidas
- **Pregunta:** ¿Cuál de las 6 ventajas de la nube se demuestra al poner a disposición de usuarios globales un archivo en segundos sin gestionar data centers?
  - **Respuesta:** Volverse global en minutos (*Go global in minutes*).
- **Pregunta:** ¿Cuál es el costo de la transferencia de datos entrante (*Data Transfer IN*) hacia servicios como Amazon S3?
  - **Respuesta:** Es totalmente gratuita (*Data Transfer IN is free*).
- **Pregunta:** ¿Qué principio económico se aplica al pagar únicamente por el almacenamiento consumido en lugar de comprar infraestructura fija?
  - **Respuesta:** Cambiar el gasto de capital (CapEx) por gasto operativo variable (OpEx).

---

## 1.2 Principios de diseño (Well-Architected)
- **Laboratorio:** Usar AWS Well-Architected Tool para evaluar un workload ficticio.
- **Paso a paso:** Acceso a la herramienta, creación de workload, responder preguntas de los 6 pilares y revisar recomendaciones.

### 1. Objetivo del laboratorio
Aprender a auditar y evaluar arquitecturas de soluciones en la nube mediante la **AWS Well-Architected Tool**. Comprenderás cómo mapear los componentes de un sistema ficticio con los **6 pilares del marco AWS Well-Architected**: *Excelencia Operativa*, *Seguridad*, *Fiabilidad*, *Eficiencia del Rendimiento*, *Optimización de Costos* y *Sostenibilidad*.

### 2. Instrucciones paso a paso

#### Paso 1: Acceso a la herramienta y creación de la carga de trabajo (*Workload*)
1. En la barra de búsqueda de la Consola de administración de AWS, ingresa `Well-Architected Tool` y abre el servicio.
2. Haz clic en el botón **Definir carga de trabajo** (*Define workload*).
3. Ingresa los datos del proyecto ficticio:
   - **Nombre de la carga de trabajo:** `Plataforma-ECommerce-AWS`.
   - **Descripción:** `Aplicación web de 3 niveles con Amazon CloudFront, ALB, Auto Scaling de EC2 y Amazon RDS`.
   - **Entorno:** Selecciona **Producción**.
   - **Regiones:** Selecciona `us-east-1 (N. Virginia)`.
4. En la sección *Marcos* (*Lenses*), confirma que esté seleccionado el **AWS Well-Architected Framework**.
5. Haz clic en **Definir carga de trabajo**.

#### Paso 2: Evaluación guiada y respuesta de preguntas de los 6 pilares
1. Selecciona la carga de trabajo creada y haz clic en **Iniciar revisión** (*Start review*).
2. Responde las preguntas representativas para cada pilar:
   - **Excelencia Operativa:** Para la pregunta sobre automatización de operaciones, marca la opción *Realizar operaciones como código* (usando **AWS CloudFormation**).
   - **Seguridad:** En la pregunta de gestión de identidades, marca *Usar autenticación multifactor (MFA)* y *Aplicar el principio de menor privilegio con IAM*.
   - **Fiabilidad:** En la sección de prevención de fallas, marca *Despliegue en múltiples Zonas de Disponibilidad (Multi-AZ)* y *Recuperación automática mediante Auto Scaling*.
   - **Eficiencia del Rendimiento:** En la selección de tecnologías, marca *Uso de almacenamiento en caché con Amazon ElastiCache* y *Distribución de contenido con CloudFront*.
   - **Optimización de Costos:** En la gestión de consumo, marca *Adopción de un modelo de consumo (pagar solo por uso)* y *Uso de Instancias Reservadas / Savings Plans para cargas estables*.
   - **Sostenibilidad:** En la optimización de recursos, marca *Escalado elástico para eliminar capacidad ociosa* y *Uso de procesadores eficientes como AWS Graviton*.

#### Paso 3: Revisión de recomendaciones y exportación de informe con AWS CLI
1. Completa las preguntas del cuestionario y haz clic en **Guardar y salir**.
2. Para consultar el estado de las evaluaciones registradas en tu cuenta desde la **AWS CLI**, ejecuta:
   ```bash
   aws wellarchitected list-workloads
   ```
   *Explicación de la salida:* Muestra un objeto JSON con el `WorkloadId`, el estado de la respuesta y el número de riesgos altos (*High Risk Issues - HRIs*) y riesgos medios (*Medium Risk Issues - MRIs*) detectados.
3. Regresa a la consola web, selecciona la carga de trabajo y haz clic en **Generar informe** (*Generate report*). Revisa el *Plan de mejora* (*Improvement Plan*) generado automáticamente.

---

### 3. Resultado esperado
Obtendrás un informe de arquitectura formal que cuantifica los riesgos del sistema y proporciona recomendaciones priorizadas basadas en los 6 pilares de AWS para mejorar la postura operativa y reducir costos.

---

### 4. Errores comunes y cómo evitarlos
1. **Confundir la Well-Architected Tool con AWS Trusted Advisor:** Asumir que la herramienta escanea de forma automática los recursos desplegados. *Solución:* Recuerda que la Well-Architected Tool es una revisión cualitativa guiada por cuestionario, mientras que Trusted Advisor realiza comprobaciones automáticas continuas.
2. **Ignorar el pilar de Sostenibilidad:** Enfocarse solo en servidores sin considerar el impacto del uso eficiente de la energía. *Solución:* Incluye la optimización de capacidad y la reducción de datos ociosos en S3 Glacier.
3. **Marcar controles no implementados:** Declarar que existen respaldos o alta disponibilidad cuando no están configurados, falseando el reporte de riesgo.

---

### 5. Preguntas de reflexión
1. ¿Cómo ayuda el principio de *"Realizar operaciones como código"* (usando CloudFormation) a cumplir con el pilar de Excelencia Operativa?
2. ¿De qué manera la migración de servidores físicos a servicios administrados Serverless (como AWS Lambda) beneficia simultáneamente a los pilares de Optimización de Costos y Sostenibilidad?

---

### 6. Flashcards rápidas
- **Pregunta:** ¿Cuáles son los 6 pilares del marco AWS Well-Architected?
  - **Respuesta:** Excelencia Operativa, Seguridad, Fiabilidad, Eficiencia del Rendimiento, Optimización de Costos y Sostenibilidad.
- **Pregunta:** ¿Qué herramienta de la consola de AWS permite evaluar cargas de trabajo mediante cuestionarios y genera planes de remediación estructurados?
  - **Respuesta:** La AWS Well-Architected Tool.
- **Pregunta:** ¿A qué pilar corresponde la recomendación de *"Escalar horizontalmente para reemplazar un recurso grande por múltiples recursos pequeños"*?
  - **Respuesta:** Al pilar de Fiabilidad.

---

## 1.3 Estrategias de migración (AWS CAF)
- **Laboratorio:** Simular migración de base de datos con AWS DMS hacia RDS.
- **Paso a paso:** Crear instancia RDS, configurar DMS, replicar datos y validar migración.

### 1. Objetivo del laboratorio
Estructurar la adopción de la nube alineada con las 6 perspectivas del **AWS Cloud Adoption Framework (AWS CAF)** y simular la migración de una base de datos relacional hacia **Amazon RDS** utilizando **AWS Database Migration Service (AWS DMS)**. Practicarás la estrategia de migración **Rehost / Replatform** (*Lift and Shift*) manteniendo la base de datos de origen operativa.

---

```
+-------------------------------------------------------------------------+
|                ARQUITECTURA DE MIGRACIÓN CON AWS DMS                    |
|                                                                         |
|  ORIGEN (On-Premises / EC2)    INSTANCIA DE REPLICACIÓN    DESTINO (RDS)|
|  +--------------------+        +--------------------+    +------------+ |
|  | Base de Datos      | -----> | Instancia AWS DMS  | -> | Amazon RDS | |
|  | (MySQL / Postgres) |        | (Tarea CDC/Carga)  |    | (SQL)      | |
|  +--------------------+        +--------------------+    +------------+ |
|                                                                         |
|  Marco de Alineación: AWS CAF (Perspectiva de Plataforma y Operaciones) |
+-------------------------------------------------------------------------+
```

---

### 2. Instrucciones paso a paso

#### Paso 1: Alineación con las perspectivas del AWS CAF
1. **Perspectivas de Negocio (Negocio, Personas, Gobernanza):** Define los objetivos de ROI, capacita al equipo de administradores de bases de datos y gestiona el cumplimiento de licencias.
2. **Perspectivas Técnicas (Plataforma, Seguridad, Operaciones):** Diseña la red en la VPC, configura las políticas de menor privilegio en IAM y establece las ventanas de mantenimiento en Amazon RDS.

#### Paso 2: Creación de la instancia de destino en Amazon RDS
1. En la consola de AWS, navega a **Amazon RDS** y haz clic en **Crear base de datos**.
2. Selecciona la creación estándar con el motor **MySQL** (o PostgreSQL).
3. Selecciona la plantilla de **Capa gratuita** (instancia `db.t3.micro`).
4. En **Identificador de la instancia**, ingresa `rds-destino-db`.
5. Configura las credenciales maestras (usuario y contraseña) y mantén la conectividad en tu VPC por defecto.
6. Haz clic en **Crear base de datos** y aguarda a que el estado cambie a *Disponible*.

#### Paso 3: Configuración de la instancia y Puntos de Enlace (*Endpoints*) en AWS DMS
1. Abre el servicio **AWS Database Migration Service (AWS DMS)**.
2. En el menú lateral, selecciona **Instancias de replicación** y crea una nueva instancia llamada `dms-replication-instance` asignada a tu VPC.
3. Selecciona **Puntos de enlace** (*Endpoints*) y configura dos entidades:
   - **Endpoint de origen (*Source*):** Introduce los datos de conexión de tu base de datos de prueba local o alojada en EC2.
   - **Endpoint de destino (*Target*):** Selecciona la instancia `rds-destino-db` recién creada en Amazon RDS.
4. Haz clic en **Probar conexión** para garantizar la conectividad de red entre DMS y ambas bases de datos.

#### Paso 4: Creación de la tarea de migración, replicación y validación
1. Selecciona **Tareas de migración de datos** y haz clic en **Crear tarea**.
2. En *Tipo de migración*, selecciona **Migrar datos existentes y replicar cambios continuos** (*Full load + CDC*) para lograr una migración con el mínimo tiempo de inactividad.
3. Inicia la tarea de migración.
4. Para monitorear el progreso de la tarea desde la **AWS CLI**, ejecuta:
   ```bash
   aws dms describe-replication-tasks
   ```
   *Explicación de la salida:* Devuelve un JSON que detalla el `Status` de la tarea (`running` o `replication-complete`), el porcentaje de tablas migradas y las métricas de replicación de registros.

---

### 3. Resultado esperado
Validarás que las tablas y registros de la base de datos de origen se hayan replicado correctamente hacia Amazon RDS mediante AWS DMS, experimentando cómo la estrategia **Rehost / Replatform** permite reducir los costos de administración hasta en un 30%.

---

### 4. Errores comunes y cómo evitarlos
1. **Reglas de seguridad de red incompletas:** El Security Group de RDS no permite tráfico entrante desde la instancia de replicación de DMS. *Solución:* Añade una regla de entrada en el Security Group de RDS autorizando la dirección IP de la instancia DMS.
2. **Registros binarios desactivados en el origen:** No tener activada la replicación CDC (*Change Data Capture*) en la base de datos de origen. *Solución:* Habilita el *binlog* o los registros de replicación en la base de origen antes de ejecutar la tarea.
3. **Confundir Rehost con Refactor:** Creer que la estrategia *Rehost* requiere modificar la estructura completa de la aplicación. *Solución:* Recordar que *Rehost* (*Lift and Shift*) traslada la carga tal como está sin optimizaciones avanzadas de código.

---

### 5. Preguntas de reflexión
1. ¿De qué manera la perspectiva de **Plataforma** del AWS CAF facilita la definición de patrones de arquitectura para mover bases de datos a Amazon RDS?
2. ¿Por qué utilizar AWS DMS para una replicación continua en segundo plano minimiza el impacto operativo en los usuarios finales durante la fase de corte (*cutover*)?

---

### 6. Flashcards rápidas
- **Pregunta:** ¿Cuáles son las 6 perspectivas que componen el framework AWS CAF?
  - **Respuesta:** Negocio, Personas, Gobernanza, Plataforma, Seguridad y Operaciones.
- **Pregunta:** ¿Qué caracteriza a la estrategia de migración de aplicaciones denominada "Rehost" (*Lift and Shift*)?
  - **Respuesta:** Migrar aplicaciones o bases de datos a la nube tal como están, sin realizar cambios en su arquitectura.
- **Pregunta:** ¿Qué servicio de AWS se utiliza para replicar y migrar bases de datos de forma continua hacia la nube?
  - **Respuesta:** AWS Database Migration Service (AWS DMS).

---

## 1.4 Economía de la nube
- **Laboratorio:** Calcular costos de una instancia EC2 On-Demand vs Reserved Instance usando AWS Pricing Calculator.
- **Paso a paso:** Abrir Pricing Calculator, configurar instancia On-Demand, configurar Reserved Instance, comparar costos y documentar ahorro.

### 1. Objetivo del laboratorio
Aprender a proyectar, modelar y comparar costos de infraestructura utilizando la herramienta pública **AWS Pricing Calculator**. Aprenderás a cuantificar el impacto económico de utilizar **Instancias Bajo Demanda (*On-Demand*)** frente a compromisos a largo plazo mediante **Instancias Reservadas (*Reserved Instances*)** o **Savings Plans**, calculando el porcentaje de ahorro acumulado.

---

```
+-------------------------------------------------------------------------+
|         COMPARATIVA FINANCIERA EN AWS PRICING CALCULATOR                |
|                                                                         |
|  MODELO DE COMPRA           COMPROMISO        DESCUENTO APROXIMADO      |
|  +----------------------+   +--------------+  +----------------------+  |
|  | Bajo Demanda         |   Sin compromiso |  0% (Tarifa base)    |  |
|  | Instancia Reservada  |   1 o 3 años     |  Hasta 66% - 72%     |  |
|  | Compute Savings Plan |   1 o 3 años     |  Hasta 66% - 72%     |  |
|  +----------------------+   +--------------+  +----------------------+  |
|                                                                         |
|  Herramienta de estimación: AWS Pricing Calculator (calculator.aws)     |
+-------------------------------------------------------------------------+
```

---

### 2. Instrucciones paso a paso

#### Paso 1: Acceso a AWS Pricing Calculator
1. Abre tu navegador web e ingresa al portal público de la calculadora: `https://calculator.aws/`.
2. Haz clic en el botón **Crear estimación** (*Create estimate*).

#### Paso 2: Configuración de la instancia en modelo Bajo Demanda (*On-Demand*)
1. En la barra de búsqueda de servicios, escribe `Amazon EC2` y haz clic en **Configurar**.
2. En *Descripción del grupo*, escribe `Servidores-Web-OnDemand`.
3. Selecciona la Región: `EE. UU. Este (N. Virginia)`.
4. En las especificaciones de la carga de trabajo:
   - **Sistema operativo:** Linux.
   - **Cantidad de instancias:** `1`.
   - **Tipo de instancia:** Busca y selecciona la instancia de propósito general `m4.large`.
5. En la sección **Estrategia de precios**, selecciona **Bajo demanda (*On-Demand*)**.
6. Haz clic en **Guardar y agregar al servicio**.

#### Paso 3: Configuración de la misma instancia como Instancia Reservada
1. En la estimación activa, haz clic en **Agregar servicio** y vuelve a seleccionar `Amazon EC2`.
2. En la descripción, ingresa `Servidores-Web-Reservado-3Anos`.
3. Mantén la misma región (`us-east-1`), cantidad (`1`) y tipo de instancia (`m4.large`).
4. En **Estrategia de precios**, selecciona **Instancia Reservada** (o *Compute Savings Plan*) a un plazo de **3 años** con la opción de pago **Todo por adelantado (*All Upfront*)**.
5. Haz clic en **Guardar y agregar al servicio**.

#### Paso 4: Comparación de costos, documentación de ahorro y consulta con AWS CLI
1. Revisa el desglose financiero en el resumen de la estimación:
   - **Costo Bajo Demanda (`m4.large`):** ~\$0.10 USD por hora (~\$876.00 USD anuales).
   - **Costo Instancia Reservada (3 años All Upfront):** ~\$0.037 USD por hora equivalente (~\$324.12 USD anuales), lo que representa un ahorro superior al 60%.
2. Haz clic en **Exportar** para descargar el reporte comparativo en formato PDF o CSV.
3. Para consultar si tu cuenta tiene recomendaciones activas de redimensionamiento (*right-sizing*) basadas en métricas de CloudWatch, ejecuta en tu terminal con la **AWS CLI**:
   ```bash
   aws compute-optimizer get-ec2-instance-recommendations
   ```
   *Explicación de la salida:* Devuelve un informe estructurado que analiza recursos sobredimensionados o subutilizados y sugiere el tipo de instancia óptimo para reducir costos hasta un 25%.

---

### 3. Resultado esperado
Generarás una proyección financiera verifícala que demuestra que para cargas de trabajo estables e ininterrumpidas (como bases de datos o servidores principales), el uso de Instancias Reservadas o Savings Plans disminuye los costos operativos drásticamente en comparación con la tarifa Bajo Demanda.

---

### 4. Errores comunes y cómo evitarlos
1. **Omitir el almacenamiento EBS en el cálculo:** Evaluar solo la CPU y memoria RAM sin agregar los gigabytes del volumen de almacenamiento en bloque adjunto. *Solución:* Incluir los GBs del volumen EBS necesarios para el sistema operativo en la estimación.
2. **Confundir Pricing Calculator con Cost Explorer:** Intentar analizar consumo histórico en lugar de estimar costos de arquitecturas futuras. *Solución:* Usa Pricing Calculator para proyectos antes de desplegar y Cost Explorer para analizar el gasto real de la cuenta.
3. **Comparar instancias en regiones distintas:** Seleccionar regiones diferentes entre los dos modelos, lo que altera la comparación debido a las variaciones regionales de precio.

---

### 5. Preguntas de reflexión
1. ¿Cuáles son los tres factores impulsoras fundamentales de costo en el modelo de pago por uso de AWS?
2. ¿En qué escenario técnico es preferible utilizar la modalidad Bajo Demanda a pesar de ser más costosa por hora que una Instancia Reservada?

---

### 6. Flashcards rápidas
- **Pregunta:** ¿Cuáles son los tres fundamentos de precios en el modelo de pago por uso de AWS?
  - **Respuesta:** Cómputo (tiempo de ejecución), Almacenamiento (datos guardados) y Transferencia de datos SALIENTE (*Data Transfer OUT*).
- **Pregunta:** ¿Qué herramienta pública de AWS permite modelar y estimar el costo de una solución antes de construirla?
  - **Respuesta:** La AWS Pricing Calculator (`calculator.aws`).
- **Pregunta:** ¿Qué porcentaje de ahorro aproximado se puede obtener al contratar Instancias Reservadas a 3 años frente a la tarifa Bajo Demanda?
  - **Respuesta:** Descuentos de hasta un 60% a 72% sobre el precio Bajo Demanda.