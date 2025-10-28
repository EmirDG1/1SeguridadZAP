# Análisis de Vulnerabilidades con OWASP ZAP

##  Alumno
**Guillermo Emir Duarte González**

## Universidad
**CESUN Universidad**

## Materia
**Programación Funcional**

## Fecha
**28 de octubre de 2025**

---

## Descripción del Proyecto
Este repositorio contiene el **análisis de seguridad** realizado con la herramienta **OWASP ZAP (Zed Attack Proxy)** sobre la aplicación **Tienda de Autos**, alojada en GitHub Pages.

El propósito de esta práctica es **identificar vulnerabilidades comunes** en aplicaciones web y aplicar los conocimientos sobre seguridad informática vistos en clase.

---

## Metodología
- **Herramienta:** OWASP ZAP 2.16.1  
- **Tipo de escaneo:** Activo y pasivo  
- **Proxy:** localhost:8080  
- **Navegador:** Chrome controlado por ZAP  
- **URL analizada:** [https://emirdg1.github.io/backend/](https://emirdg1.github.io/backend/)

Durante el análisis, se navegaron todas las rutas del sitio y se ejecutó el escaneo completo para detectar cabeceras de seguridad faltantes y posibles configuraciones vulnerables.

---

## Principales Vulnerabilidades Detectadas

| Vulnerabilidad | Nivel de Riesgo | Descripción | Recomendación |
|----------------|-----------------|--------------|----------------|
| **Content Security Policy (CSP) Header Not Set** | Medio | Falta la cabecera CSP que previene ataques XSS. | Agregar `Content-Security-Policy` al servidor. |
| **Strict-Transport-Security Header Not Set** | Medio | No se detecta cabecera HSTS para HTTPS. | Añadir `Strict-Transport-Security: max-age=31536000; includeSubDomains`. |
| **Cross-Domain Misconfiguration** | Bajo | Permite solicitudes desde orígenes externos. | Limitar `Access-Control-Allow-Origin`. |
| **X-Content-Type-Options Header Missing** | Bajo | Archivos podrían ejecutarse como scripts. | Añadir `X-Content-Type-Options: nosniff`. |

---

## Evidencias
Las evidencias del escaneo se encuentran dentro de la carpeta `seguridad/capturas/`, donde se muestran:
- Alertas detectadas
- Árbol de sitios escaneados
- Panel general de OWASP ZAP

---

## Archivos Incluidos
