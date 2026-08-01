# Planificador de Producción — Silver Industrial

App para armar y repartir el plan semanal de producción de las 16 inyectoras de Silver Industrial (Tecnología en Plásticos).

## Qué resuelve

- Reemplaza el Excel de planificación semanal (`Planner.xlsx`), manteniendo la misma lógica de cálculo:
  - **HS Máquina** = Cantidad × Ciclo / 3600 (AUTO) o / 3300 (SEMI)
  - **Días de Producción** = HS Máquina ÷ horas disponibles según turno (1 turno = 8,5 h, 2 = 11,5 h, 3 = 15 h, 4 = 22,5 h)
- Maestro único de productos (nombre, ciclo estándar, tipo AUTO/SEMI), con alta rápida desde la solapa **Productos**.
- Carga semanal por máquina con orden/secuencia, cargada a mano en la reunión de planificación de los jueves.
- Alerta visual si una máquina se pasa de los días hábiles disponibles en la semana.
- Vista de impresión horizontal (una sola hoja, todas las máquinas) para repartir a cambiadores de molde, preparador de material, depósito, supervisor, jefe de planta, dueños e inspector de calidad — con descarga directa a PDF.

## Cómo se usa

1. Abrí la URL de GitHub Pages de este repo.
2. Solapa **Productos**: revisá o cargá el ciclo estándar de lo que vas a planificar. El maestro arrancó importado del histórico de `Planner.xlsx` (436 productos); algunos quedaron marcados "ciclo variable — revisar" porque el histórico tenía más de un valor registrado.
3. Solapa **Cargar plan**: elegí semana, días hábiles, y cargá producto/cantidad/turno/inicio por máquina. Los cálculos salen solos.
4. Solapa **Imprimir / PDF**: revisá la hoja y descargá el PDF para repartir.

## Nota técnica

Es un único archivo HTML autocontenido (sin backend). Los datos se guardan en el `localStorage` del navegador de quien lo usa — cada persona que entra tiene su propia copia local, no es un dato compartido en tiempo real entre varias personas. Si más adelante se necesita que varios usuarios vean el mismo plan actualizado, hay que sumar una base de datos compartida (quedó pensado para que ese cambio sea acotado).

Mantenido por Diego Ortiz — Coordinador de Mejora Continua / Consultor.
