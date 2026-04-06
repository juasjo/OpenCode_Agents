---
description: Desarrollo automático con loop de ejecución
agent: build
model: openai/gpt-5-codex
tools:
  write: true
  edit: true
  bash: true
---

TAREA:

$ARGUMENTS

REGLAS:

- NO pidas contexto si puedes hacer algo razonable
- CREA archivos reales
- EJECUTA el código
- CORRIGE automáticamente si falla

LOOP DE EJECUCIÓN:

Repite hasta que funcione o máximo 3 intentos:

1. Implementar código
2. Usar @tester para ejecutarlo
3. Si tester devuelve FAIL:
   - analizar errores
   - corregir código
   - volver a ejecutar

4. Si tester devuelve OK:
   - parar

PROCESO COMPLETO:

1. @planner → plan breve
2. implementar código en archivos
3. LOOP de ejecución (máx 3 veces)
4. @reviewer → revisión final
5. @tester → validación final

Corrige SOLO lo necesario, no reescribas todo

SALIDA FINAL:

- archivos creados
- cómo ejecutar
- resultado final (OK o FAIL)
