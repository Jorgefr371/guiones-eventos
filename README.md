# Generador de guiones y copys — Eventos Cristian

Página estática de un solo archivo. No usa IA, no tiene backend, no guarda nada y no necesita claves.
Todo lo que genera sale de las plantillas que ya se midieron en las dos cuentas publicitarias
(Cristian Store · 1660058514692575 y Cristian Ecommerce · 1412506193638718).

## Qué hace

1. **Guiones de video** — cuatro aperturas distintas sobre la estructura ganadora, con el rótulo fijo
   (modelo arriba, fecha y con qué juega abajo) y un plan de grabación segundo a segundo para 28, 35 o 50 segundos.
2. **Copys para Meta** — cinco variantes con titular, descripción y texto principal, listas para copiar.
3. **Revisar video o foto** — se lee el archivo en el navegador (no se sube a ningún lado) y se compara
   con los números reales: duración, si tiene audio, relación de aspecto y resolución.

## Desplegar en Vercel

**Opción A — arrastrar la carpeta**

1. Entra a https://vercel.com/new
2. Arrastra la carpeta `generador-eventos` completa
3. Deploy. No hay que configurar nada: no tiene build ni variables de entorno.

**Opción B — desde la terminal**

```bash
npx vercel --cwd "generador-eventos" --prod
```

**Opción C — desde un repositorio**

Sube la carpeta a GitHub y conéctala en Vercel. Framework preset: **Other**. Build command: vacío.
Output directory: vacío (sirve la raíz).

## De dónde salen los números que cita la página

| Dato | Origen |
|---|---|
| 25-32 s → $702 por conversación | Evento XTZ 250, octubre 2026 |
| Más de 45 s → $728 | Cristian Store, últimos 90 días |
| Menos de 20 s → $1.595 a $5.354 | XTZ 250 y GN Naranja |
| Hook de producto → $541 | Cristian Ecommerce, octubre |
| Hook de escasez como apertura → $1.652 | Cristian Ecommerce, octubre |
| Imágenes → $539 con el CTR más alto | Evento XTZ 250 |

Son el histórico medido, no una promesa de resultado.

## Mantenimiento

Todo está en `index.html`. Para cambiar textos o números:

- **Hooks de los guiones** → arreglo `HOOKS`
- **Copys de Meta** → función `copys(d)`
- **Umbrales del revisor de video** → función `checksVideo(v, mb)`
- **Palabras que disparan la alerta** → arreglo `PROHIBIDAS`

Cuando cierres un evento nuevo, actualiza los costos citados para que la página siga diciendo la verdad.
# guiones-eventos
