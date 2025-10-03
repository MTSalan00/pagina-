# 🏦 Maze Bank - Gestor Financiero Personal v2.0

Un gestor de gastos e ingresos moderno y completo con **backend y base de datos local** que te permite controlar tus finanzas personales de manera eficiente.

## ✨ Características

### 💰 Gestión de Transacciones
- **Agregar gastos e ingresos** con descripción, cantidad y categoría
- **Categorías predeterminadas** para gastos e ingresos comunes
- **Categorías personalizadas** que puedes crear y gestionar
- **Historial completo** de todas las transacciones
- **Filtros avanzados** por tipo y categoría

### 📊 Estadísticas Detalladas
- **Estadísticas por período**: Diario, Semanal, Mensual y Total
- **Balance total** en tiempo real
- **Resumen de ingresos y gastos**
- **Promedio de transacciones**
- **Contador de transacciones**

### 🗄️ Base de Datos Local
- **SQLite** - Base de datos local sin necesidad de servidor externo
- **API REST** - Endpoints para todas las operaciones
- **Migración automática** de datos localStorage a base de datos
- **Backup y exportación** de datos
- **Persistencia real** - Los datos no se pierden al limpiar el navegador

### 📱 Diseño Responsivo
- **Compatible con móviles y escritorio**
- **Interfaz moderna** con tema verde profesional
- **Fácil de usar** con navegación intuitiva

## 🚀 Instalación y Uso

### Prerrequisitos
- **Node.js** (versión 14.0.0 o superior)
- **npm** (viene incluido con Node.js)

### Instalación

1. **Clona o descarga el proyecto**
   ```bash
   git clone <url-del-repositorio>
   cd gestordegastoss
   ```

2. **Instala las dependencias**
   ```bash
   npm install
   ```

3. **Inicia el servidor**
   ```bash
   npm start
   ```

4. **Abre tu navegador**
   - Ve a: `http://localhost:5000`
   - El servidor backend estará corriendo en el puerto 5000
   - El frontend se servirá automáticamente desde el mismo puerto

### Scripts Disponibles

```bash
# Iniciar servidor de producción
npm start

# Iniciar servidor de desarrollo (con auto-reload)
npm run dev

# Servir solo el frontend (puerto 3000)
npm run frontend

# Iniciar backend y frontend simultáneamente
npm run dev-full
```

## 📁 Estructura del Proyecto

```
gestordegastoss/
├── frontend/                 # Frontend (HTML, CSS, JS)
│   ├── index.html           # Página principal
│   ├── styles.css           # Estilos CSS
│   └── app.js               # Lógica JavaScript (v2.0)
├── backend/                 # Backend (Node.js + Express)
│   ├── server.js            # Servidor principal
│   ├── database/            # Configuración de base de datos
│   │   ├── config.js        # Configuración SQLite
│   │   └── maze_bank.db     # Base de datos SQLite (se crea automáticamente)
│   ├── models/              # Modelos de datos
│   │   ├── Transaction.js   # Modelo de transacciones
│   │   ├── CustomCategory.js # Modelo de categorías
│   │   └── index.js         # Exportación de modelos
│   ├── routes/              # Rutas de la API
│   │   ├── transactions.js  # API de transacciones
│   │   ├── categories.js    # API de categorías
│   │   └── migration.js     # API de migración
│   └── middleware/          # Middleware personalizado
├── package.json             # Configuración del proyecto
└── README.md               # Este archivo
```

## 🔗 API Endpoints

### Transacciones
- `GET /api/transactions` - Obtener todas las transacciones
- `GET /api/transactions/:id` - Obtener transacción específica
- `POST /api/transactions` - Crear nueva transacción
- `PUT /api/transactions/:id` - Actualizar transacción
- `DELETE /api/transactions/:id` - Eliminar transacción
- `GET /api/transactions/stats/summary` - Obtener estadísticas

### Categorías
- `GET /api/categories` - Obtener categorías personalizadas
- `GET /api/categories/default` - Obtener categorías predeterminadas
- `GET /api/categories/available/:type` - Obtener categorías disponibles por tipo
- `POST /api/categories` - Crear nueva categoría
- `PUT /api/categories/:id` - Actualizar categoría
- `DELETE /api/categories/:id` - Eliminar categoría

### Migración
- `POST /api/migration/import-localstorage` - Importar datos del localStorage
- `GET /api/migration/export-localstorage` - Exportar datos para localStorage
- `POST /api/migration/clear-database` - Limpiar base de datos (solo desarrollo)

### Sistema
- `GET /api/health` - Estado del servidor

## 🎯 Cómo Usar

### 1. Primera Vez
1. Ejecuta `npm start`
2. Abre `http://localhost:5000` en tu navegador
3. Si tienes datos en localStorage, se migrarán automáticamente a la base de datos

### 2. Agregar una Transacción
1. Completa el formulario "Nueva Transacción"
2. Selecciona el tipo (Ingreso o Gasto)
3. Elige una categoría o crea una nueva
4. Haz clic en "Agregar Transacción"

### 3. Gestionar Categorías
1. Ve a la sección "Gestionar Categorías"
2. Escribe el nombre de la nueva categoría
3. Haz clic en "Agregar Categoría"
4. Puedes eliminar categorías personalizadas cuando quieras

### 4. Ver Estadísticas
1. Usa las pestañas para cambiar el período:
   - **Diario**: Transacciones del día actual
   - **Semanal**: Transacciones de la semana actual
   - **Mensual**: Transacciones del mes actual
   - **Total**: Todas las transacciones

### 5. Filtrar Transacciones
1. Usa los filtros en "Historial de Transacciones"
2. Filtra por tipo (Ingresos/Gastos) o categoría
3. Haz clic en "Limpiar filtros" para ver todo

## 🛠️ Tecnologías Utilizadas

### Frontend
- **HTML5** - Estructura semántica
- **CSS3** - Estilos modernos con Grid y Flexbox
- **JavaScript ES6+** - Lógica de la aplicación
- **Fetch API** - Comunicación con el backend

### Backend
- **Node.js** - Runtime de JavaScript
- **Express.js** - Framework web
- **SQLite** - Base de datos local
- **Sequelize** - ORM para SQLite
- **CORS** - Configuración de CORS

## 🔧 Características Técnicas

### Categorías Predeterminadas
**Ingresos**: Salario, Freelance, Inversiones, Bonos, Otros Ingresos
**Gastos**: Comida, Transporte, Entretenimiento, Servicios, Compras, Salud, Educación, Otros Gastos

### Base de Datos
- **Archivo**: `backend/database/maze_bank.db`
- **Tablas**: `transactions`, `custom_categories`
- **Formato**: SQLite (archivo local)
- **Backup**: Exportación automática disponible

### Formato de Datos
- **Moneda**: Pesos Mexicanos (MXN)
- **Fechas**: Formato ISO 8601
- **Almacenamiento**: Base de datos SQLite local

## 📱 Compatibilidad

- ✅ Chrome 60+
- ✅ Firefox 55+
- ✅ Safari 12+
- ✅ Edge 79+
- ✅ Dispositivos móviles
- ✅ Node.js 14.0.0+

## 🔒 Privacidad y Seguridad

- **Datos locales**: Toda la información se almacena en tu computadora
- **Sin servidor externo**: No se envían datos a ningún servidor externo
- **Control total**: Tú tienes control completo sobre tus datos financieros
- **Base de datos local**: SQLite funciona completamente offline

## 🐛 Solución de Problemas

### El servidor no inicia
- Verifica que Node.js esté instalado: `node --version`
- Verifica que las dependencias estén instaladas: `npm install`
- Revisa que el puerto 5000 esté disponible

### Error de conexión con la API
- Verifica que el servidor esté corriendo: `npm start`
- Abre `http://localhost:5000/api/health` en tu navegador
- Revisa la consola del navegador (F12) para errores

### Los datos no se guardan
- Verifica que el servidor backend esté funcionando
- Revisa la consola del navegador para errores de red
- Verifica que la base de datos se haya creado en `backend/database/`

### Error de migración
- Los datos del localStorage se migran automáticamente
- Si hay errores, puedes exportar manualmente desde la API
- Los datos originales se mantienen hasta migración exitosa

## 🚀 Desarrollo

### Estructura de la API
```javascript
// Ejemplo de uso de la API
const response = await fetch('http://localhost:5000/api/transactions', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        description: 'Compra de supermercado',
        amount: 150.50,
        type: 'expense',
        category: 'Comida'
    })
});
```

### Variables de Entorno
```bash
# Puerto del servidor (por defecto: 5000)
PORT=5000

# Entorno (development/production)
NODE_ENV=development
```

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:
1. Fork el proyecto
2. Crea una rama para tu feature
3. Commit tus cambios
4. Push a la rama
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 📞 Soporte

Si tienes problemas o sugerencias:
- Abre un issue en GitHub
- Revisa la documentación
- Verifica la consola del navegador para errores
- Revisa los logs del servidor en la terminal

---

**¡Disfruta gestionando tus finanzas con Maze Bank v2.0! 🏦💰**

### 🆕 Novedades en v2.0
- ✅ Backend completo con Node.js + Express
- ✅ Base de datos SQLite local
- ✅ API REST para todas las operaciones
- ✅ Migración automática de localStorage
- ✅ Mejor escalabilidad y rendimiento
- ✅ Sistema de backup y exportación
- ✅ Arquitectura más robusta y mantenible