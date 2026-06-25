# Juego san Josemaría

Juego de preguntas estilo Kahoot! para celebrar la fiesta de san Josemaría (26 de junio).

## Juego

Abre `index.html` o la URL publicada de la web.

En la pantalla de inicio se puede:

- Elegir idioma.
- Elegir categoría.
- Pulsar `¡EMPEZAR!` para jugar.

Categorías disponibles:

- `Vida`
- `Escritos`
- `Camino al Centenario`

Idiomas disponibles:

- Español
- Inglés
- Eslovaco
- Esloveno
- Portugués de Brasil
- Francés

Durante el juego, el botón `Salir` vuelve a la pantalla de inicio.

## Administración

Para entrar como administrador, añade `?rol=admin` a la URL.

Ejemplos:

- Local: `http://localhost:8000/?rol=admin`
- Web publicada: `https://tu-dominio.com/?rol=admin`

Desde Admin se puede:

- Editar preguntas y respuestas por idioma y categoría.
- Elegir cuál es la respuesta correcta.
- Exportar todas las preguntas a CSV.
- Importar un CSV y reemplazar las preguntas actuales.
- Mostrar u ocultar categorías una a una.
- Mostrar u ocultar idiomas uno a uno.
- Arrastrar y soltar idiomas para cambiar el orden en la pantalla de inicio.

Los cambios hechos desde Admin se guardan en el navegador con `localStorage`.

## CSV de preguntas

La app busca automáticamente un archivo llamado `questions.csv` en la misma carpeta que `index.html`.

Si existe `questions.csv`, la app usa ese banco de preguntas.

El CSV debe tener estas columnas:

```csv
language,category,question,option1,option2,option3,option4,correct
```

Valores esperados:

- `language`: `es`, `en`, `sk`, `sl`, `ptBR`, `fr`
- `category`: `vida`, `escritos`, `centenario`
- `correct`: número del `1` al `4`, indicando la respuesta correcta.

## Actualizar preguntas

Flujo recomendado:

1. Entra en Admin con `?rol=admin`.
2. Edita preguntas o importa un CSV.
3. Pulsa `Exportar CSV`.
4. Guarda el archivo con el nombre exacto `questions.csv`.
5. Sube `questions.csv` a GitHub en la misma carpeta que `index.html`.
6. Haz commit y push.

Cuando GitHub Pages publique el cambio, la app cargará el nuevo `questions.csv`.

## Desarrollo Local

Para probar la web en local:

```bash
python3 -m http.server 8000
```

URLs locales:

- Juego: `http://localhost:8000/`
- Admin: `http://localhost:8000/?rol=admin`

Es mejor probar con servidor local y no abriendo el archivo directamente, porque así `questions.csv` se carga igual que en producción.
