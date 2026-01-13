# 🛍️ Portal de Productos – E-commerce con Chat, Carrito y GraphQL

Aplicación web desarrollada con **Node.js, Express, MongoDB, GraphQL y Socket.IO** que implementa un **portal de productos convertido en un e-commerce completo**, con autenticación JWT, roles de usuario, carrito de compra, pedidos y comunicación en tiempo real mediante chat persistente.

El proyecto parte de una aplicación sencilla y se amplía progresivamente para simular el funcionamiento real de una tienda online, manteniendo una arquitectura clara, modular y escalable.

---

## 📌 Descripción general

El Portal de Productos permite:

- Registro e inicio de sesión de usuarios.
- Autenticación mediante **JWT**.
- Control de acceso por **roles (admin / user)**.
- CRUD completo de productos.
- Chat global en tiempo real con persistencia.
- **Carrito de compra para usuarios normales**.
- **Creación y gestión de pedidos (Orders)**.
- **Integración de GraphQL** conviviendo con la API REST existente.

---

## 👩‍💻 Usuario administrador por defecto

| Campo | Valor |
|------|------|
| Email | lydia@example.com |
| Contraseña | 1234 |
| Rol | admin |

⚠️ El administrador **no puede comprar productos**, solo gestionarlos.

---

## ⚙️ Requisitos previos

- Node.js (v18 o superior)
- MongoDB en local
- npm

---

## 🚀 Instalación y ejecución

### 1️⃣ Clonar el repositorio
```bash
git clone https://github.com/lydiaa-gr/Proga_web.Practica1-portal-productos-.git
cd portal-productos
```

### 2️⃣ Instalar dependencias
```bash
npm install
```

### 3️⃣ Variables de entorno

Crear un archivo `.env`:
```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/portal-products
JWT_SECRET=clave_super_segura
```

### 4️⃣ Iniciar servidor
```bash
npm run dev
```

---

## 🌐 Acceso

- Aplicación web:  
👉 http://localhost:3000

- GraphQL Playground:  
👉 http://localhost:3000/graphql

---

## 🧭 Uso de la aplicación

### 🔐 Autenticación
- Registro e inicio de sesión con JWT.
- El token se guarda en `localStorage`.
- Acceso condicionado por rol.

---

### 📦 Productos

#### Administrador
- Crear productos
- Editar productos
- Eliminar productos
- Gestionar stock

#### Usuario normal
- Ver productos
- Añadir productos al carrito

---

### 🛒 Carrito de compra

- Disponible **solo para usuarios normales**
- Persistente en `localStorage`
- Al añadir un producto:
  - El stock disminuye automáticamente
  - No se permite comprar sin stock

---

### 📦 Pedidos (Orders)

- Creación al finalizar la compra
- Incluyen:
  - Usuario
  - Productos
  - Cantidades
  - Precio total
- Estados:
  - `PENDING`
  - `COMPLETED`
- Gestión mediante **GraphQL**

---

### 💬 Chat en tiempo real

- Socket.IO
- Autenticación con JWT
- Mensajes persistentes
- Historial automático

---

## 🔷 GraphQL

### Endpoint
```bash
/graphql
```

### Types
- Product
- User
- Order
- OrderItem

### Queries
- products
- product(id)
- orders
- order(id)

### Mutations
- createOrder
- updateOrderStatus (admin)

GraphQL convive con REST (auth y productos).

---

## 🧱 Estructura del proyecto

```text
src/
│
├── server.js
├── config.js
│
├── models/
│   ├── User.js
│   ├── Product.js
│   ├── Order.js
│   └── ChatMessage.js
│
├── routes/
│   ├── authRoutes.js
│   └── productRoutes.js
│
├── graphql/
│   ├── schema.js
│   ├── resolvers.js
│   └── context.js
│
└── public/
    ├── index.html
    ├── register.html
    ├── products.html
    ├── chat.html
    └── styles.css
```

---

## 🔧 Funcionalidades clave

### 👤 Usuarios
- Registro e inicio de sesión
- JWT
- Roles

### 📦 Productos
- CRUD completo
- Validaciones de precio y stock

### 🛒 Carrito
- Solo usuarios normales
- Persistente
- Actualiza stock automáticamente

### 📦 Pedidos
- GraphQL
- Control de estado
- Asociados a usuario

### 💬 Chat
- Tiempo real
- Persistente
- Seguro

---

## 🧠 Decisiones de desarrollo

- Arquitectura modular
- REST + GraphQL
- JWT para seguridad
- Socket.IO para tiempo real
- Frontend en HTML, CSS y JS puro

---

## ✅ Estado del proyecto

✔ Funcional  
✔ Persistente  
✔ Seguro  
✔ Escalable  
✔ Adecuado como práctica final de Programación Web

