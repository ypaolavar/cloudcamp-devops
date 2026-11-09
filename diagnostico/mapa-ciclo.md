| # | Problema | Fase del ciclo | Rol responsable | Práctica propuesta |
| --- | --- | --- | --- | --- |
| 1 | Los despliegues se hacen una vez al mes, de forma manual por SSH, y tardan unas 6 horas. | Deploy | DevOps | Usar una imagen de Docker construida mediante un pipeline, usar Helm charts y sincronizar el contenedor con Argo/Flux CD al clúster. |
| 2 | Cerca del 30 % de los despliegues provoca errores en producción. | Deploy | DevOps | Usar ambientes equivalentes a producción para probar antes de hacer la salida. |
| 3 | No existen pruebas automatizadas y cada versión se prueba a mano durante 3 días. | Build | Platform Eng. | Usar un pipeline con pruebas de QA integradas; estas se ejecutan en el entorno de QA o preproducción. |
| 4 | Las caídas del sitio se detectan cuando los clientes se quejan en redes sociales. | Operate | SRE | Configurar monitoreo a la plataforma y sus recursos cloud, Dynatrace, Grafana. |
| 5 | Los desarrolladores esperan hasta 2 semanas para obtener un servidor de pruebas. | Plan | Platform Eng. | Tener creado un servidor para el ambiente de pruebas y automatizar el proceso de creación mediante un flujo que se corre en el IDP. |
| 6 | Las contraseñas de la base de datos están escritas en el código del repo. | Build | DevSecOps | Usar AWS Secrets Manager y configurar un check que rompe el pipeline si detecta valores sensibles quemados en el código. |
| 7 | Si un despliegue falla, no existe un procedimiento de reversión y la recuperación tarda horas. | Deploy | SRE | Versionar la aplicación y hacer rollback con backups tomados antes de la actividad. |
| 8 | El modelo de recomendación de productos se reentrena a mano cada pocos meses y nadie mide si sus predicciones empeoran. | Operate | MLOps | Entrenamiento automatizado y monitoreo de la calidad de las predicciones. |


## Ajustes tras revisión con IA

Cambio aceptado

Fila 7: El fallo ocurre durante un despliegue, así que Deploy podría ser más preciso que Operate. También conviene distinguir entre revertir la versión de la aplicación y recuperar datos: los backups no sustituyen un procedimiento de rollback probado. 

Erratas de sintaxis.

Cambios no aceptados

Sugerencias relacionadas con fases adicionales a las 4 descritas en el ejercicio (plan, build, deploy u operate), como monitoreo y Test.