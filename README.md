# ETH Events ◈

> Plataforma de eventos Web3 impulsada por GitHub Issues + Actions + Pages.

---

## 📅 Agregar un evento

1. Abre un **[nuevo issue](../../issues/new?template=event.md)**
2. Usa el template `📅 Nuevo Evento`
3. Llena todos los campos
4. Un maintainer agrega el label **`approved`**
5. El evento aparece en el sitio automáticamente ⚡

---

## 🏷️ Labels del sistema

| Label | Descripción |
|-------|-------------|
| `evento` | Todos los issues de evento |
| `pendiente` | En revisión por maintainers |
| `approved` | ✅ Publicado en el sitio |
| `rechazado` | ❌ No cumple criterios |

---

## 🗂️ Estructura del proyecto

```
eth-events/
├── index.html                          # Sitio principal
├── events.json                         # Generado automáticamente
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── event.md                    # Template para eventos
│   └── workflows/
│       ├── sync-events.yml             # Parsea issues → events.json
│       └── deploy.yml                  # Deploy a GitHub Pages
└── README.md
```

---

## ⚙️ Cómo funciona el workflow

```
Issue abierto/editado
        ↓
sync-events.yml se dispara
        ↓
Lee todos los issues con label "approved"
        ↓
Parsea el body con regex por secciones
        ↓
Genera events.json ordenado por fecha
        ↓
Commit automático al repo
        ↓
deploy.yml detecta el push
        ↓
GitHub Pages actualizado ✅
```

---

## 🎨 Personalización

El diseño usa CSS variables en `:root`. Para cambiar los colores principales:

```css
:root {
  --accent: #627eea;    /* Color principal (Ethereum blue) */
  --bg: #0a0b0f;        /* Fondo */
  --surface: #111318;   /* Cards */
}
```

---

## 📜 Licencia

MIT — Úsalo, forkéalo, mejóralo.
