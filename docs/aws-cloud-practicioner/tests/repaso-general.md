# Repaso general

Test de 10 preguntas relacionadas con todos los módulos para reforzar conceptos.

!!! info ""

    Puedes ver la solución a cada pregunta haciendo click al icono _:octicons-light-bulb-16: Mostrar pista_.

:::{quizdown}

---
primaryColor: "#00bda4"
shuffleQuestions: false
shuffleAnswers: true
---

## ¿Qué servicio de AWS permite almacenar datos estructurados y no estructurados en una base de datos NoSQL y ofrece replicación global con baja latencia?

1. [ ] Amazon Aurora
2. [ ] Amazon RDS
3. [ ] Amazon Redshift
4. [x] Amazon DynamoDB Global Tables

> Amazon DynamoDB Global Tables permite replicar datos en múltiples regiones con baja latencia, ideal para aplicaciones globales y de alta disponibilidad.

## ¿Cuál de los siguientes servicios permite orquestar flujos de trabajo serverless con gestión automática de errores y reintentos?

1. [ ] Amazon MQ
2. [ ] AWS Step Functions
3. [ ] Amazon EventBridge
4. [x] AWS Step Functions Express Workflows

> AWS Step Functions Express Workflows están diseñados para flujos de trabajo de alta frecuencia y bajo coste, incluyendo la gestión automática de reintentos y errores.

## ¿Qué combinación de servicios permite implementar un pipeline de CI/CD completamente gestionado en AWS?

1. [ ] AWS CodePipeline, AWS CodeBuild, AWS CodeDeploy
2. [ ] AWS CodeCommit, Amazon SQS, AWS CodeDeploy
3. [ ] AWS Amplify, Amazon SNS, AWS CodeDeploy
4. [x] AWS CodePipeline, AWS CodeBuild, AWS CodeCommit

> La combinación de CodePipeline, CodeBuild y CodeCommit permite crear un pipeline de CI/CD completamente gestionado desde el control de versiones hasta la automatización de despliegues.

## ¿Qué opción de Amazon S3 minimiza los costes para datos a los que se accede de forma poco frecuente y solo está disponible en una única zona de disponibilidad?

1. [ ] S3 Standard-IA
2. [ ] S3 Intelligent-Tiering
3. [x] S3 One Zone-IA
4. [ ] S3 Glacier

> S3 One Zone-IA es ideal para datos poco accedidos que no requieren replicación en múltiples zonas de disponibilidad.

## ¿Qué servicio de AWS permite implementar aplicaciones web y móviles, gestionando tanto el backend como la autenticación de usuarios?

1. [ ] AWS Amplify
2. [ ] Amazon Cognito
3. [ ] AWS Cloud9
4. [x] AWS Amplify

> AWS Amplify facilita el desarrollo de aplicaciones frontend y backend, incluyendo autenticación, APIs, y almacenamiento.

## ¿Qué herramienta de AWS permite crear alarmas que activan automáticamente acciones como escalado o notificaciones en función de métricas?

1. [ ] Amazon GuardDuty
2. [ ] AWS Config
3. [ ] Amazon CloudTrail
4. [x] Amazon CloudWatch

> Amazon CloudWatch permite crear alarmas sobre métricas de uso, rendimiento y costes, y ejecutar acciones automáticas como escalado de instancias.

## ¿Qué servicio permite procesar grandes volúmenes de datos en tiempo real utilizando flujos de datos de alta velocidad?

1. [ ] Amazon Athena
2. [ ] Amazon Aurora
3. [x] Amazon Kinesis Data Streams
4. [ ] AWS Glue

> Amazon Kinesis Data Streams permite procesar flujos de datos en tiempo real, ideal para análisis de logs, clics o eventos de IoT.

## ¿Cuál es la mejor práctica para asegurar la rotación automática de secretos y contraseñas en AWS?

1. [ ] Almacenarlos en Amazon S3 con cifrado SSE
2. [ ] Configurar roles de IAM con claves de acceso estáticas
3. [ ] Guardarlos en AWS Systems Manager Parameter Store
4. [x] Utilizar AWS Secrets Manager

> AWS Secrets Manager permite gestionar secretos y contraseñas de forma segura, incluyendo la rotación automática y control de acceso.

## ¿Qué solución de balanceo de carga es más adecuada para aplicaciones modernas que requieren enrutamiento avanzado basado en contenido?

1. [ ] Classic Load Balancer
2. [ ] Network Load Balancer
3. [ ] Gateway Load Balancer
4. [x] Application Load Balancer

> Application Load Balancer (ALB) permite enrutar peticiones en función del contenido de la solicitud, ideal para aplicaciones modernas y microservicios.

## ¿Qué servicio de AWS permite implementar clústeres de Big Data escalables con Apache Spark y Hadoop?

1. [ ] AWS Glue
2. [ ] Amazon Redshift
3. [ ] Amazon Kinesis
4. [x] Amazon EMR

> Amazon EMR permite crear clústeres de Big Data escalables, utilizando Apache Spark, Hadoop y otros frameworks de procesamiento de datos.

:::
