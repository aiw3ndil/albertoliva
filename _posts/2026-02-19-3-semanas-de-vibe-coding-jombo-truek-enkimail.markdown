---
layout: post
title: "3 semanas de Vibe Coding"
date: 2026-02-19 10:00:00 +0200
categories: [tecnología, desarrollo, proyectos]
---

<img src="/assets/images/jombo-logo.png" alt="Logos de los proyectos" style="float: left; width: 40%; margin-right: 20px; margin-bottom: 10px; border-radius: 8px;">

Últimamente se habla mucho del concepto de **Vibe Coding**, esa forma de desarrollar donde la fricción entre la idea y la ejecución casi desaparece gracias a la asistencia de la IA. Tras aplicarlo intensamente durante unas tres semanas, hoy puedo decir que el resultado ha sido increíble: he lanzado tres proyectos funcionales y listos para usar. La velocidad de iteración ha sido la clave para poder gestionar tres productos distintos en paralelo.

<div style="clear: both;"></div>

<!--more-->

Aquí os presento en qué he estado trabajando:

1.  **[Jombo.es](https://jombo.es)**: Un servicio de carpooling (viaje compartido) centrado en la comunidad y, lo más importante, **sin comisiones**. La idea es facilitar el transporte compartido de forma ética y directa.
2.  **[Truek.xyz](https://truek.xyz)**: Una plataforma de intercambio de objetos. En un mundo donde acumulamos demasiado, Truek facilita el trueque de aquello que ya no usamos por lo que realmente necesitamos.
3.  **[Enkimail.com](https://enkimail.com)**: Un procesador de colas de correo diseñado específicamente para email marketing. Permite gestionar envíos masivos de forma eficiente y controlada.

### El Stack Tecnológico
Para los tres proyectos he mantenido un stack muy similar, lo que me ha permitido ser extremadamente ágil:
*   **Backend:** Ruby en modo API. La velocidad de desarrollo de Ruby sigue siendo imbatible para estas tareas.
*   **Frontend:** Next.js. Todos los frontends están alojados de forma gratuita en **Vercel**, aprovechando su excelente integración y rendimiento.
*   **Infraestructura de Backend:** Todos los backends conviven en un mismo servidor gestionado con **Coolify**. Para quienes no lo conozcan, Coolify es como tener un "Heroku autogestionado"; una maravilla para simplificar despliegues y gestión de contenedores sin pagar los precios de las plataformas PaaS tradicionales.

### El reto de Enkimail
El proyecto de **Enkimail** ha sido el más exigente a nivel de infraestructura. He utilizado **Docker** para levantar un servidor **Postfix** que la propia web utiliza para realizar los envíos. 

Cualquiera que haya trabajado con email marketing sabe que la reputación de la IP lo es todo. He tenido muchísima suerte al encontrar una IP limpia que no figura en ninguna lista negra, lo cual es fundamental para asegurar que los correos lleguen a la bandeja de entrada y no a spam desde el primer día.

Estas tres semanas han sido un recordatorio de que, con las herramientas adecuadas y el enfoque correcto, la distancia entre "tengo una idea" y "tengo un producto" nunca ha sido tan corta.

¿Qué os parecen los proyectos? ¡Os leo en los comentarios!
