# Dashboard de Comisiones - LUTEC

Panel web que muestra las comisiones de compras por comprador, leyendo datos
en vivo desde Monday.com a través de n8n.

## Cómo funciona

- La web consulta un webhook de n8n
- n8n lee los sub-items de Monday (materiales con precio bolsa, compra y comprador)
- n8n calcula la comisión escalonada por utilidad
- La web muestra el dashboard general y el detalle por comprador

## Tabla de comisión

| Utilidad | Comisión |
|----------|----------|
| < 10%    | 0%       |
| 10 - 20% | 0.25%    |
| 20 - 30% | 0.50%    |
| >= 30%   | 0.75%    |

## Archivos

- `index.html` — el dashboard (todo en un archivo)
- `netlify.toml` — configuración de publicación

## Configuración

La URL del webhook de n8n está dentro de `index.html`, en la variable `API_URL`.
