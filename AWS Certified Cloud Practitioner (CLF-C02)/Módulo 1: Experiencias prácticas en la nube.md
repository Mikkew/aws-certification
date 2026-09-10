#  Módulo 1 Conceptos de la nube - Laboratorios

## 1.1 Beneficios de la nube de AWS

- Laboratorio: crear un bucket S3, subir un archivo y verificar disponibilidad global.

### 1. Objetivo del laboratorio

Comprobar de forma práctica las ventajas fundamentales de la computación en la nube de AWS: **volverse global en minutos**, **eliminar la adivinación de capacidad** y cambiar el **gasto de capital (CapEx)** por un **gasto operativo variable (OpEx)**. Al finalizar, sabrás aprovisionar almacenamiento elástico en **Amazon S3**, configurar permisos de acceso y acceder al recurso desde cualquier parte del mundo mediante la infraestructura global de AWS.

### 2. Instrucciones paso a paso

#### Paso 1: Crear un bucket de almacenamiento global en Amazon S3

1. Inicia sesión en la **Consola de administración de AWS**.
2. En la barra de búsqueda superior, escribe `S3` y selecciona el servicio **S3**.
3. Haz clic en el botón **Crear bucket**.
4. En **Nombre del bucket**, ingresa un nombre único a nivel global (por ejemplo: `lab-clf-c02-mexico-2026`).
5. En **Región de AWS**, selecciona una región cercana, como `EE. UU. Este (N. Virginia) us-east-1`.
6. En la sección **Configuración de bloqueo de acceso público para este bucket**, desmarca la opción **Bloquear *todo* el acceso público**.
7. Selecciona la casilla de verificación que confirma el reconocimiento de que la configuración resultante puede ser pública.
8. Mantén las demás opciones por defecto y haz clic en **Crear bucket**.

#### Paso 2: Cargar un archivo al bucket

1. En la lista de buckets de Amazon S3, haz clic en el nombre del bucket recién creado (`lab-clf-c02-mexico-2026`).
2. Haz clic en el botón **Cargar** y luego en **Agregar archivos**.
3. Selecciona un archivo de prueba de tu equipo local (por ejemplo, `index.html` o una imagen `demo.png`).
4. Despliega la sección **Permisos** y en *Conceder acceso público*, selecciona **Lectura** para el archivo (o selecciona el archivo tras subirlo y en *Acciones de objetos* elige **Hacer público mediante ACL**).
5. Haz clic en el botón **Cargar**.

#### Paso 3: Verificar la disponibilidad global vía AWS CLI y HTTP

1. Abre tu terminal o **AWS CloudShell** y ejecuta el siguiente comando para listar el contenido del bucket desde la interfaz de línea de comandos:
*Explicación de la salida:* El comando devuelve la fecha de carga, el tamaño en bytes y el nombre del archivo subido, confirmando que el objeto está registrado en el almacenamiento de objetos de AWS.
    
    ```
    aws s3 ls s3://lab-clf-c02-mexico-2026/
    ```
    
2. Vuelve a la consola, haz clic en el objeto subido y copia la **URL del objeto** (formato: `https://lab-clf-c02-mexico-2026.s3.amazonaws.com/demo.png`).
3. Abre una ventana de navegador de incógnito o consulta la URL mediante `curl`:
*Explicación de la salida:* Recibirás una respuesta HTTP `200 OK`, lo que demuestra que el archivo es accesible globalmente a través de Internet sin haber configurado un servidor web físico ni administrado hardware.
    
    ```
    curl -I https://lab-clf-c02-mexico-2026.s3.amazonaws.com/demo.png
    ```
    

---

### 3. Resultado esperado

Verificarás que el archivo almacenado en Amazon S3 es accesible de inmediato desde cualquier ubicación geográfica con acceso a Internet. Esto demuestra cómo AWS permite desplegar activos globales en minutos sin inversión previa en servidores o centros de datos.

---

### 4. Errores comunes y cómo evitarlos

1. **Nombre de bucket duplicado:** Intentar usar un nombre que ya pertenece a otro usuario en cualquier región. *Solución:* Añade un prefijo o sufijo único con números o tus iniciales.
2. **Error HTTP `403 AccessDenied`:** Ocurre si la opción *Bloquear todo el acceso público* sigue activa en el bucket o si el objeto no tiene permisos de lectura pública habilitados. *Solución:* Revisa tanto la política/ACL del bucket como los permisos del objeto individual.
3. **Confusión sobre cargos de transferencia:** Creer que subir archivos genera cobros directos por entrada de datos. *Solución:* Recuerda que la transferencia de datos **hacia adentro** (*Data Transfer IN*) a AWS es gratuita; solo se factura la transferencia de datos **hacia afuera** (*Data Transfer OUT*).
4. **Dejar recursos públicos activos de forma permanente:** Riesgo de exposición accidental de datos sensibles. *Solución:* Al concluir el laboratorio, vacía y elimina el bucket para aplicar buenas prácticas de seguridad.

---

### 5. Preguntas de reflexión

1. ¿Cómo contrasta este método de aprovisionamiento elástico con el proceso tradicional de adquisición e instalación de discos duros en un centro de datos local?
2. ¿De qué manera el modelo de pago por almacenamiento consumido en Amazon S3 refleja el beneficio de cambiar CapEx por OpEx?

---

### 6. Flashcards rápidas

- **Pregunta:** ¿Cuál de las 6 ventajas de la nube se demuestra al servir contenido mundialmente en segundos sin gestionar hardware físico?
    - **Respuesta:** Volverse global en minutos (*Go global in minutes*).
- **Pregunta:** ¿Cómo se cobra la transferencia de datos entrante (*Data Transfer IN*) hacia Amazon S3?
    - **Respuesta:** La transferencia de datos hacia adentro del Cloud de AWS es gratuita.
- **Pregunta:** ¿Qué pilar financiero se optimiza al pagar solo por los gigabytes de almacenamiento utilizados en lugar de comprar arreglos de discos por adelantado?
    - **Respuesta:** Cambiar el gasto de capital (CapEx) por gastos operativos variables (OpEx).

---

## 1.2 Principios de diseño (Well-Architected)

- Laboratorio: usar AWS Well-Architected Tool para evaluar un workload ficticio y mapearlo a los 6 pilares.

### 1. Objetivo del laboratorio

Aprender a auditar y evaluar arquitecturas en la nube utilizando la **AWS Well-Architected Tool**. Comprenderás cómo mapear los componentes de un sistema ficticio frente a los **6 pilares del marco AWS Well-Architected**: *Excelencia Operativa*, *Seguridad*, *Fiabilidad*, *Eficiencia del Rendimiento*, *Optimización de Costos* y *Sostenibilidad*.

### 2. Instrucciones paso a paso

#### Paso 1: Definir una carga de trabajo (*Workload*) ficticia

1. En la Consola de AWS, busca y abre el servicio **AWS Well-Architected Tool**.
2. Haz clic en el botón **Definir carga de trabajo**.
3. Configura los datos generales:
    - **Nombre de la carga de trabajo:** `ECommerce-Platform-v1`.
    - **Descripción:** `Aplicación web de 3 niveles con ALB, instancias EC2 en Auto Scaling y base de datos Amazon RDS`.
    - **Entorno:** Selecciona **Producción**.
    - **Regiones:** Selecciona `us-east-1` (N. Virginia).
4. En la sección de Marcos, asegúrate de mantener marcado el **AWS Well-Architected Framework**.
5. Haz clic en **Definir carga de trabajo**.

#### Paso 2: Realizar la evaluación guiada por pilares

1. Selecciona la carga de trabajo recién creada y haz clic en **Iniciar revisión**.
2. Responde las preguntas clave simulando el estado actual de la plataforma:
    - **Pilar de Seguridad:** En la pregunta de gestión de identidades, marca *Usar identidades con un proveedor de identidades centralizado (IAM)* e *Implementar el principio de menor privilegio*.
    - **Pilar de Fiabilidad:** En la pregunta sobre prevención de fallas, marca *Escalar horizontalmente para aumentar la disponibilidad* y *Desplegar en múltiples Zonas de Disponibilidad (Multi-AZ)*.
    - **Pilar de Optimización de Costos:** Marca *Adoptar un modelo de consumo* e *Implementar la atribución de costos mediante etiquetas (tags)*.
    - **Pilar de Sostenibilidad:** Marca *Optimizar el uso de recursos informáticos mediante autoescalado y serverless*.
3. Avanza respondiendo o guardando las secciones hasta completar el cuestionario de los 6 pilares.

#### Paso 3: Consultar los hallazgos mediante AWS CLI y analizar el plan de mejora

1. Abre tu terminal con AWS CLI configurada y ejecuta el siguiente comando para consultar las cargas de trabajo definidas:
*Explicación de la salida:* Devuelve un JSON que incluye el `WorkloadId`, el estado de la revisión y el conteo de riesgos altos (*High Risks*) y medios (*Medium Risks*) identificados por la herramienta.
    
    ```
    aws wellarchitected list-workloads
    ```
    
2. Vuelve a la consola web de **AWS Well-Architected Tool**, selecciona tu *Workload* y haz clic en **Generar informe**.
3. Revisa la sección **Plan de mejora** (*Improvement Plan*), que indica los pasos de remediación arquitectónica priorizados para eliminar puntos únicos de falla.

---

### 3. Resultado esperado

Obtendrás un diagnóstico arquitectónico completo de la carga de trabajo evaluada, identificando riesgos de seguridad, brechas de fiabilidad y oportunidades de optimización de costos según las mejores prácticas del marco.

---

### 4. Errores comunes y cómo evitarlos

1. **Confundir la AWS Well-Architected Tool con AWS Trusted Advisor:** Asumir que la Well-Architected Tool audita automáticamente los recursos sin intervención humana. *Solución:* Recuerda que la Well-Architected Tool es un proceso de evaluación estructurado mediante cuestionario, mientras que Trusted Advisor realiza análisis automáticos en tiempo real.
2. **Omitir el pilar de Sostenibilidad:** Ignorar el impacto de recursos ociosos en el consumo energético. *Solución:* Incluye siempre la optimización de uso y la selección de tecnologías eficientes como AWS Graviton o Serverless.
3. **Responder de forma inexacta por asumir la existencia de controles:** Declarar que un sistema es tolerante a fallas sin contar con despliegues Multi-AZ configurados.

---

### 5. Preguntas de reflexión

1. ¿De qué manera la separación de responsabilidades y la automatización mediante infraestructura como código (CloudFormation) respalda al pilar de Excelencia Operativa?
2. Si un sistema migra de instancias EC2 fijas a arquitecturas serverless como AWS Lambda, ¿qué pilares del Well-Architected Framework reciben una mejora directa?

---

### 6. Flashcards rápidas

- **Pregunta:** ¿Cuáles son los 6 pilares del marco AWS Well-Architected?
    - **Respuesta:** Excelencia Operativa, Seguridad, Fiabilidad, Eficiencia del Rendimiento, Optimización de Costos y Sostenibilidad.
- **Pregunta:** ¿A qué pilar corresponde el principio de *"Escalar horizontalmente para aumentar la disponibilidad agregada del sistema"*?
    - **Respuesta:** Al pilar de Fiabilidad.
- **Pregunta:** ¿Qué herramienta de AWS genera informes y planes de mejora basados en evaluaciones guiadas de los 6 pilares?
    - **Respuesta:** La AWS Well-Architected Tool.

---

## 1.3 Estrategias de migración (AWS CAF)

- Laboratorio: simular migración de base de datos con AWS DMS hacia RDS.

### 1. Objetivo del laboratorio

Aprender a estructurar un plan de migración utilizando el marco **AWS Cloud Adoption Framework (AWS CAF)** y simular la migración de una base de datos hacia **Amazon RDS** utilizando **AWS Database Migration Service (AWS DMS)**. Identificarás el rol de las perspectivas técnicas y de negocio dentro de la estrategia de migración **Rehost / Replatform** (*Lift and Shift*).

---

```
+-------------------------------------------------------------------------+
|                ARQUITECTURA DE MIGRACIÓN CON AWS DMS                    |
|                                                                         |
|  ORIGEN (On-Premises / EC2)    INSTANCIA DE REPLICACIÓN    DESTINO (RDS)|
|  +--------------------+        +--------------------+    +------------+ |
|  | Base de Datos      | -----> | Instancia AWS DMS  | -> | Amazon RDS | |
|  | (MySQL / Postgres) |        | (Tarea CDC/Carga)  |    | (Gestiona) | |
|  +--------------------+        +--------------------+    +------------+ |
|                                                                         |
|  Marco de Alineación: AWS CAF (Perspectivas Plataforma y Operaciones)   |
+-------------------------------------------------------------------------+
```

---

### 2. Instrucciones paso a paso

#### Paso 1: Alineación previa con las 6 perspectivas del AWS CAF

1. **Perspectivas de Negocio (Negocio, Personas, Gobernanza):** Evalúa el impacto operativo, capacita al personal técnico y define el modelo de licencias en la nube.
2. **Perspectivas Técnicas (Plataforma, Seguridad, Operaciones):**
    - *Plataforma:* Diseña la infraestructura de red en la VPC y aprovisiona el servicio gestionado en Amazon RDS.
    - *Seguridad:* Configura grupos de seguridad (*Security Groups*) y políticas de acceso mediante IAM.
    - *Operaciones:* Define las ventanas de mantenimiento y las estrategias de respaldo en la nube.

#### Paso 2: Aprovisionar la base de datos de destino en Amazon RDS

1. En la Consola de AWS, navega al servicio **Amazon RDS**.
2. Haz clic en **Crear base de datos**.
3. Selecciona la creación sencilla o estándar con el motor **MySQL** (o PostgreSQL).
4. Elige el tipo de plantilla **Capa gratuita** (instancia `db.t3.micro`).
5. En *Identificador de la instancia*, escribe `rds-destino-db`.
6. Configura el usuario maestro y contraseña, mantén las opciones de red dentro de tu VPC por defecto y haz clic en **Crear base de datos**.

#### Paso 3: Configurar los puntos de enlace (*Endpoints*) en AWS DMS

1. Abre el servicio **AWS Database Migration Service (AWS DMS)**.
2. En el menú lateral, selecciona **Instancias de replicación** y haz clic en **Crear instancia de replicación**. Asigna el nombre `dms-instance-demo` y selecciona la VPC por defecto.
3. Selecciona **Puntos de enlace** (*Endpoints*) y configura dos entidades:
    - **Endpoint de origen (*Source*):** Configura los datos de conexión de tu base de datos local o EC2 de prueba.
    - **Endpoint de destino (*Target*):** Selecciona la base de datos `rds-destino-db` creada en Amazon RDS.
4. Haz clic en **Probar conexión** para validar que DMS tiene acceso de red a ambas bases de datos.

#### Paso 4: Ejecutar la tarea de migración y verificar estado vía AWS CLI

1. Crea una **Tarea de migración de datos** en la consola de DMS seleccionando el tipo *Migrar datos existentes y replicar cambios continuos* (Carga completa + CDC) para una migración con mínimo tiempo de inactividad.
2. Ejecuta la tarea y consulta su estado desde la AWS CLI ejecutando:
*Explicación de la salida:* Devuelve un objeto JSON con el estado de la tarea (`Status: running` o `replication-possible`), mostrando el porcentaje de tablas cargadas y el progreso de replicación en tiempo real.
    
    ```
    aws dms describe-replication-tasks
    ```
    

---

### 3. Resultado esperado

Verificarás cómo los datos se replican hacia Amazon RDS de forma transparente utilizando AWS DMS. Comprenderás cómo la estrategia **Rehost / Replatform** permite trasladar componentes a servicios gestionados reduciendo hasta un 30% en costos operativos y simplificando las tareas de parchado y administración del sistema operativo.

---

### 4. Errores comunes y cómo evitarlos

1. **Falta de conectividad de red entre DMS y RDS:** Reglas de grupos de seguridad que bloquean el tráfico entrante al puerto de la base de datos (ej. puerto 3306). *Solución:* Añadir una regla de entrada en el *Security Group* de RDS que permita el tráfico desde la IP de la instancia de replicación de DMS.
2. **Confundir la estrategia *Rehost* con *Refactor*:** Pensar que usar DMS implica rediseñar completamente el código de la aplicación. *Solución:* Recordar que *Rehost* (*Lift and Shift*) o *Replatform* mueve los datos/servidores con cambios mínimos o nulos en la arquitectura de la aplicación.
3. **No habilitar el registro binario en la base de datos de origen:** Necesario para que DMS capture los cambios continuos (CDC). *Solución:* Habilitar los logs de replicación en el origen antes de iniciar la tarea de sincronización.

---

### 5. Preguntas de reflexión

1. ¿Qué perspectivas del AWS Cloud Adoption Framework (AWS CAF) se centran en las capacidades organizacionales y de negocio en comparación con las perspectivas técnicas?
2. ¿Por qué delegar la administración del sistema operativo y parches de la base de datos a AWS mediante Amazon RDS representa una ventaja operativa bajo el modelo de responsabilidad compartida?

---

### 6. Flashcards rápidas

- **Pregunta:** ¿Cuáles son las 6 perspectivas organizacionales que define el marco AWS CAF?
    - **Respuesta:** Negocio, Personas, Gobernanza, Plataforma, Seguridad y Operaciones.
- **Pregunta:** ¿Qué significa la estrategia de migración "Rehost" (*Lift and Shift*)?
    - **Respuesta:** Migrar aplicaciones y bases de datos a la nube sin realizar modificaciones ni optimizaciones avanzadas.
- **Pregunta:** ¿Qué servicio de AWS facilita la migración continua de bases de datos hacia la nube sin tiempo de inactividad significativo?
    - **Respuesta:** AWS Database Migration Service (AWS DMS).

---

## 1.4 Economía de la nube

- Laboratorio: calcular costos de una instancia EC2 On-Demand vs Reserved Instance usando AWS Pricing Calculator.

### 1. Objetivo del laboratorio

Aprender a modelar, estimar y comparar los costos de cómputo en AWS utilizando la herramienta **AWS Pricing Calculator**. Al finalizar, sabrás cuantificar las diferencias financieras entre el modelo **Bajo demanda (*On-Demand*)**, las **Instancias Reservadas (*Reserved Instances*)** y los **Savings Plans**.

---

### 2. Instrucciones paso a paso

#### Paso 1: Configurar una estimación en AWS Pricing Calculator

1. Inicia sesión en la herramienta web pública **AWS Pricing Calculator** (`calculator.aws`).
2. Haz clic en el botón **Crear estimación**.
3. En la barra de búsqueda de servicios, escribe `Amazon EC2` y haz clic en **Configurar**.

#### Paso 2: Modelar la arquitectura con instancias Bajo demanda (*On-Demand*)

1. En *Descripción del grupo*, ingresa `Servidores Web - Bajo Demanda`.
2. Selecciona la Región: `EE. UU. Este (N. Virginia)`.
3. Especifica las características de la carga de trabajo:
    - **Sistema operativo:** Linux.
    - **Cantidad de instancias:** `2`.
    - **Tipo de instancia:** Selecciona la familia de propósito general `t2.micro` o `m5.large`.
4. En la sección **Estrategia de precios**, selecciona **Bajo demanda (*On-Demand*)**.
5. Revisa el costo mensual calculado y haz clic en **Guardar y agregar al servicio**.

#### Paso 3: Modelar la misma arquitectura con Instancias Reservadas / Savings Plans

1. Haz clic en **Agregar servicio** y vuelve a seleccionar `Amazon EC2`.
2. Ingresa en la descripción: `Servidores Web - Instancias Reservadas 3 Años`.
3. Mantén exactamente la misma región (`us-east-1`), cantidad (`2`) y tipo de instancia.
4. En **Estrategia de precios**, cambia la opción a **Instancia Reservada** (o *Compute Savings Plan*) con un contrato a **3 años** y opción de pago **Todo por adelantado (*All Upfront*)**.
5. Haz clic en **Guardar y agregar al servicio**.

#### Paso 4: Comparar y exportar la estimación financiera

1. Revisa el panel de resumen de la estimación en la herramienta.
2. Compara el costo mensual e inicial total de ambas opciones:
    - *Escenario Bajo Demanda:* Facturación mensual constante sin compromiso.
    - *Escenario Reservado / Savings Plan:* Descuento significativo (hasta 66% - 72%) sobre la tarifa por hora equivalente a cambio del compromiso de uso a largo plazo.
3. Haz clic en **Exportar** para descargar el reporte comparativo en formato CSV o PDF.

#### Paso 5: Consultar recomendaciones de optimización vía AWS CLI

Para verificar cómo AWS analiza el uso real de una cuenta para sugerir compras de reservas o dimensionamiento correcto (*right-sizing*), ejecuta en la CLI:

```
aws compute-optimizer get-ec2-instance-recommendations
```

*Explicación de la salida:* Devuelve un listado con los recursos sobredimensionados o subutilizados, recomendando cambios de tipo de instancia para reducir costos hasta un 25%.

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

### 3. Resultado esperado

Generarás una estimación de costos formal que demuestra que para cargas de trabajo continuas y estables (como bases de datos o servidores web de producción), el compromiso mediante Instancias Reservadas o Savings Plans genera ahorros significativos frente al pago Bajo Demanda.

---

### 4. Errores comunes y cómo evitarlos

1. **Omitir costos de almacenamiento adjuntos (Amazon EBS):** Estimar únicamente el tiempo de cómputo de la CPU/RAM sin incluir los gigabytes de volumen EBS requeridos por el sistema operativo. *Solución:* Incluir la sección de almacenamiento adjunto en la configuración de la calculadora.
2. **Confundir AWS Pricing Calculator con AWS Cost Explorer:** Intentar analizar facturas pasadas en lugar de estimar arquitecturas futuras. *Solución:* Recordar que Pricing Calculator proyecta costos hipotéticos, mientras que Cost Explorer analiza datos reales de uso histórico.
3. **Seleccionar regiones distintas en la comparación:** Comparar precios de instancias en `us-east-1` frente a regiones con estructuras impositivas u operativas diferentes.

---

### 5. Preguntas de reflexión

1. ¿Cuáles son los tres factores impulsoras fundamentales de costo en el modelo de pago por uso de AWS?
2. ¿En qué escenario operativo es preferible utilizar la tarifa Bajo demanda a pesar de no contar con descuentos a largo plazo?

---

### 6. Flashcards rápidas

- **Pregunta:** ¿Cuáles son los tres fundamentos principales del modelo de precios de pago por uso en AWS?
    - **Respuesta:** Cómputo (tiempo de ejecución), Almacenamiento (datos guardados) y Transferencia de datos SALIENTE (*Data Transfer OUT*).
- **Pregunta:** ¿Qué porcentaje aproximado de descuento se puede obtener al comprometerse con Compute Savings Plans o Instancias Reservadas a 3 años?
    - **Respuesta:** Descuentos de hasta un 66% a 72% en comparación con los precios Bajo demanda.
- **Pregunta:** ¿Qué herramienta gratuita de AWS permite calcular y modelar el costo estimado de una solución antes de desplegarla?
    - **Respuesta:** La AWS Pricing Calculator (`calculator.aws`).

---

💡 **Sugerencia de siguiente paso:** ¿Te gustaría que generemos una guía similar con prácticas de laboratorio paso a paso para el **Módulo 2: Seguridad y cumplimiento** o prefieres un conjunto de preguntas tipo examen sobre los conceptos económicos de la nube?