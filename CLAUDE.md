# Tracking de Figuritas – Mundial 2026

Página estática HTML que muestra la planilla del álbum Panini FIFA World Cup 2026.
Desplegada en https://trackingdefiguritas.vercel.app

## Estructura del proyecto

```
index.html       # Toda la app (HTML + CSS + JS inline)
.vercel/         # Config del proyecto Vercel (no commitear)
.gitignore
```

## Cómo funciona

El estado del álbum vive en el `const PEGADAS = new Set([...])` dentro de `index.html`.
Cada entry es un string con el código de país + número: `'MEX1'`, `'ARG9'`, `'EGY19'`, etc.

- Figurita **pegada** → está en el Set → se muestra oscura en la planilla
- Figurita **faltante** → no está en el Set → se muestra clara

**Países:** 48 países × 20 figuritas cada uno  
**FWC:** figuritas 1–8 (arriba) y 9–19 (abajo)  
**CC:** figuritas 1–14  
**Total del álbum:** 993 figuritas

## Actualizar figuritas

Hay dos formas, ambas se hacen a través de Claude:

### 1. Por fotos del álbum
Usar el skill `album-figuritas`. Claude pedirá la carpeta con las fotos, analizará automáticamente con visión y actualizará el Set.

### 2. Por prompt directo
Si el usuario dice algo como "pegué MEX5, ARG10 y BRA3", agregar esas entradas al Set `PEGADAS` en `index.html` y desplegar.

## Desplegar

Siempre desplegar a producción después de cualquier cambio:
```bash
vercel --prod --yes
```

## Git

Push directo a `main`, sin PRs:
```bash
git add index.html
git commit -m "mensaje"
git push
```
Remote: `git@github.com:P0nj4/tracking_de_figuritas.git`

## Features pendientes

- [ ] Contador total en el header: "X / 993 figuritas pegadas"
