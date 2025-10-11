# 🍕 Pizzería Mamma Mia — Hito 6 (React Context API)

<img width="912" height="582" alt="image" src="https://github.com/user-attachments/assets/ab28a661-0255-4b64-a67d-5d64c755f45d" />

## 🔖 Descripción General

En este hito se implementó la **Context API de React** para manejar de forma global los estados de **autenticación, carrito de compras y listado de pizzas**, reemplazando el paso de props entre componentes y optimizando la persistencia con `localStorage`.

---

## 🚀 Tecnologías utilizadas

* **Vite + React 18**
* **React Context API** (Auth, Cart, Pizza)
* **React Router v6**
* **React-Bootstrap + Bootstrap 5**
* **LocalStorage** para persistencia
* **GitHub Actions + GitHub Pages** para CI/CD y despliegue continuo

---

## 🔍 Estructura del proyecto

```
src/
├── components/        # Componentes visuales (Navbar, Footer, CardPizza, etc.)
├── context/           # Estados globales: AuthContext, CartContext, PizzaContext
├── data/              # Datos estáticos iniciales (pizzas.js)
├── pages/             # Páginas: Home, Cart, Pizza, LoginPage, RegisterPage, Profile, NotFound
├── routes/            # Rutas protegidas (ProtectedRoute)
├── App.jsx            # Definición de rutas y estructura principal
└── main.jsx           # Punto de entrada con Context Providers y Router
```

---

## 🔹 Requerimientos del hito

### 1. Context API (Estado Global) ✅

**AuthContext:**

* Maneja inicio/cierre de sesión y persistencia en `localStorage`.
* Provee `login()` y `logout()`.

**CartContext:**

* Maneja el carrito global: `add`, `inc`, `dec`, `remove`.
* Calcula total automático y guarda en `localStorage`.
* Implementa un **badge rojo** en las cards mostrando cantidad por pizza.

**PizzaContext:**

* Obtiene pizzas desde `http://localhost:5000/api/pizzas`.
* Entrega datos globalmente a `Home` y `Pizza`.

---

### 2. Consumo de API REST ✅

* Se levantó un servidor simple (Express) con endpoint `/api/pizzas`.
* `Home` y `Pizza` consumen la API mediante `fetch()`.
* Al entrar en `/pizza/:id` se muestra la pizza seleccionada.

---

### 3. Navegación y Rutas ✅

* `App.jsx` define todas las rutas:

  * `/` → Home
  * `/pizza/:id` → Pizza (dinámica)
  * `/cart` → Cart
  * `/login`, `/register`, `/profile` → vistas de usuario
  * `*` → NotFound
* Se agregó **botón “Volver”** en `Pizza.jsx` con `useNavigate(-1)`.

---

### 4. Interfaz y UX ✅

* Diseño responsive y consistente con Bootstrap.
* `CardPizza` incluye dos acciones:

  * `Ver más` → Navega a `/pizza/:id`
  * `Añadir` → Agrega al carrito global
* Se agregó **badge circular rojo con número dinámico** en cada card.
* `Cart.jsx` permite aumentar, disminuir o eliminar pizzas.

---

### 5. Despliegue continuo (CI/CD) ✅

* Workflow `.github/workflows/deploy.yml` configurado para GitHub Pages.
* Genera `404.html` como fallback para rutas internas.
* Despliegue automático tras `push` a `main`.

---

## 🔑 Contextos Implementados

| Contexto         | Estado                       | Persistencia | Acciones principales          |
| ---------------- | ---------------------------- | ------------ | ----------------------------- |
| **AuthContext**  | Usuario logeado / no logeado | localStorage | `login`, `logout`             |
| **CartContext**  | Array de pizzas con cantidad | localStorage | `add`, `inc`, `dec`, `remove` |
| **PizzaContext** | Lista de pizzas (API)        | No aplica    | `fetch` inicial               |

---

## 📱 Live Preview
<img width="1222" height="896" alt="image" src="https://github.com/user-attachments/assets/c0ca0bc0-9a72-4ee5-83b6-1e6e01895bc2" />
<img width="1219" height="781" alt="image" src="https://github.com/user-attachments/assets/a30f583c-7ff5-458a-8429-2ca13646ead6" />
<img width="1206" height="775" alt="image" src="https://github.com/user-attachments/assets/c9badcff-6252-4f9e-97c4-ccf05e8a7de8" />

Despliegue en GitHub Pages:
➡️ https://remigio96.github.io/PizzeriaMM_6_React_Context/



