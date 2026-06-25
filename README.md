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

## Desarrollo Local

Para probar la web en local:

```bash
python3 -m http.server 8000
```

URLs locales:

- Juego: `http://localhost:8000/`

Es mejor probar con servidor local y no abriendo el archivo directamente, porque así `questions.csv` se carga igual que en producción.
