# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Un único usuario (el propio dueño de la app): un opositor a Policía Nacional preparando la prueba física de 1000 metros, entrenando 3 días fijos por semana (miércoles series cortas, viernes rodaje, domingo series largas o test según la semana). Uso estrictamente personal, no compartido con otros opositores.

## Product Purpose

Llevar el registro personal de entrenos de 1000 m (series, rodaje continuo, tests cronometrados) y traducir cada test directamente a la puntuación real del baremo oficial de la Policía Nacional, para que el usuario sepa en todo momento qué nota sacaría hoy y cuánto le falta para el 10/10 (2:55). Esta es la prioridad número uno del producto, por delante de la motivación o la constancia.

## Positioning

No es una app de running genérica: no sugiere planes de entreno ni rutinas inventadas (nunca hardcodea series/reps/ritmos concretos), solo estructura fija por día de la semana. Su valor diferencial frente a un tracker de running normal es traducir el tiempo cronometrado directamente a la puntuación oficial (baremo editable) de la prueba física.

## Operating Context

Entrenos reales al aire libre/pista, cronometrados con el móvil; el usuario introduce los tiempos manualmente después de cada sesión, normalmente desde el móvil. El "test mensual" de la app (primer domingo de cada mes) es una autoevaluación, no la convocatoria oficial de la oposición — a día de hoy no hay fecha de examen real fijada. App hermana: gym-tracker (mismo usuario, misma preparación de oposición, entrenos de gimnasio en vez de carrera) — ambas deben sentirse visualmente como la misma familia de apps, cada una con su propio contenido.

## Capabilities and Constraints

- 100% local: localStorage, sin backend ni cuentas, un solo usuario por dispositivo/navegador.
- Estático: un único `index.html` sin build, servido por GitHub Pages (`18jramxs.github.io/1000m/`).
- Chart.js vía CDN para las gráficas de progreso.
- Sin fecha de examen real fijada actualmente (solo el test mensual autoevaluado).

## Brand Commitments

Ninguno explícito más allá de compartir familia visual con gym-tracker (mismo usuario, mismo propósito de oposición).

## Evidence on Hand

Baremo oficial de puntuación 1000 m (Promo 42) ya cargado como valores por defecto editables en la app. Sin más contenido o assets de marca.

## Product Principles

1. La puntuación real del baremo manda: cualquier decisión de diseño debe dejar clarísimo qué nota sacaría el usuario ahora mismo.
2. Nunca inventar planes de entreno: solo estructura por día fijo, nunca series/ritmos/repeticiones concretas.
3. Coherencia de familia con gym-tracker: misma paleta, tipografía, componentes y patrones — cada app conserva su propio contenido y objetivo.
4. Todo funciona offline y sin fricción: sin login, sin backend, datos siempre en el dispositivo del usuario.

## Accessibility & Inclusion

Sin requisito específico confirmado.
