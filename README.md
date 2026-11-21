# Codelabs de Flutter y Firebase

Codelabs no oficiales, en español, sobre Flutter, Firebase y GenKit. Cada uno es un tutorial paso a paso, hecho con
[claat](https://github.com/googlecodelabs/tools/tree/main/claat), y este repositorio es el sitio que los publica: un
catálogo con búsqueda, filtros y modo oscuro, en HTML, CSS y JavaScript sin frameworks.

## Codelabs

| Codelab                                                                  | Duración | Estado    |
| ------------------------------------------------------------------------ | -------- | --------- |
| [Firebase SQL Connect con Flutter](sql-connect-flutter/index.html)       | 133 min  | Publicado |
| [Integrando GenKit Dart en Flutter](genkit-dart-flutter/index.html)      | 101 min  | Publicado |
| [GenKit en el dispositivo con Flutter](genkit-flutter-device/index.html) | 115 min  | Borrador  |

## Ver el sitio en local

```bash
python3 -m http.server 8000
```

Y abre http://localhost:8000. También puedes usar `claat serve` o `npx http-server`.

## Agregar o actualizar un codelab

Los archivos Markdown de origen no están en este repositorio: viven en la carpeta `catalog/codelabs` de las
herramientas de codelabs. Desde ahí:

1. **Exporta** el Markdown a HTML con claat:

   ```bash
   cd catalog/codelabs
   claat export -o .. <codelab>.md
   ```

   Esto crea o actualiza la carpeta del codelab (por ejemplo, `genkit-flutter-device/`) con:

   - `index.html`: el contenido del codelab.
   - `codelab.json`: los metadatos (título, duración, estado, categorías).
   - `img/`: las imágenes.

2. **Regenera el índice** del catálogo, que lee el `codelab.json` de cada carpeta:

   ```bash
   cd ..
   node build-index.js . codelabs.json
   ```

3. **Copia** a este repositorio la carpeta del codelab y el `codelabs.json`, y súbelos.

## Estructura

```
.
├── index.html          # El catálogo
├── style.css           # Estilos (tema claro y oscuro)
├── app.js              # Búsqueda, filtros y orden
├── build-index.js      # Genera codelabs.json
├── codelabs.json       # El índice de codelabs (generado)
├── sql-connect-flutter/
├── genkit-dart-flutter/
└── genkit-flutter-device/
```
