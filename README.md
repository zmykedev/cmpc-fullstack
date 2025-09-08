# 📚 CMPC-Libros - Sistema de Gestión de Inventario

<div align="center">

![CMPC-Libros Logo](https://img.shields.io/badge/CMPC-Libros-blue?style=for-the-badge&logo=book&logoColor=white)

### *Sistema Empresarial de Gestión de Inventario de Libros*

[![Frontend](https://img.shields.io/badge/Frontend-React-61dafb?style=for-the-badge&logo=react&logoColor=white)](./cmcp-front)
[![Backend](https://img.shields.io/badge/Backend-NestJS-e0234e?style=for-the-badge&logo=nestjs&logoColor=white)](./cmpc-back)
[![Database](https://img.shields.io/badge/Database-PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](./DATABASE_MODEL.md)
[![Documentation](https://img.shields.io/badge/Docs-Swagger-green?style=for-the-badge&logo=swagger&logoColor=white)](./ARCHITECTURE.md)

</div>

## 🎯 Descripción General

**CMPC-Libros** es un sistema empresarial completo para la gestión de inventario de libros, desarrollado con tecnologías modernas y arquitectura escalable. El sistema incluye una aplicación web responsiva, una API REST robusta, sistema de auditoría completo y documentación exhaustiva.

### 🚀 **Instalación Rápida con Docker**

```bash
git clone <repository-url> && cd CMPC-Libros
docker-compose up -d
# ¡Listo! Aplicación disponible en http://localhost
```

**Todo incluido:** Base de datos PostgreSQL, Backend NestJS, Frontend React, configuración automática, y documentación en http://localhost:3000/docs

> 📦 **¿Nuevo en Docker?** No te preocupes, las instrucciones incluyen comandos detallados, solución de problemas comunes, y verificación paso a paso.

## ✨ Características Principales

### 🖥️ **Frontend (React SPA)**
- ✅ **Interfaz Moderna**: React 18 + TypeScript + Ant Design
- ✅ **Responsive Design**: Optimizado para móviles y desktop
- ✅ **Modo Oscuro**: Soporte completo para temas claro/oscuro
- ✅ **Gestión de Estado**: Zustand para estado global
- ✅ **Animaciones**: Framer Motion para transiciones suaves
- ✅ **PWA Ready**: Progressive Web App capabilities
- ✅ **Lazy Loading**: Componentes y rutas cargados bajo demanda
- ✅ **Code Splitting**: Bundle optimizado por vendor
- ✅ **Image Optimization**: Lazy loading y fallbacks automáticos
- ✅ **SEO Optimized**: Meta tags, Open Graph, preconnect

### ⚙️ **Backend (NestJS API)**
- ✅ **Arquitectura Modular**: NestJS con TypeScript
- ✅ **Autenticación JWT**: Sistema seguro con refresh tokens
- ✅ **Base de Datos**: PostgreSQL con TypeORM
- ✅ **Validaciones**: class-validator para validación robusta
- ✅ **Documentación**: Swagger/OpenAPI integrado
- ✅ **Testing**: Jest + Supertest con alta cobertura
- ✅ **Arquitectura Simplificada**: Campos directos para mejor rendimiento
- ✅ **UUIDs**: Claves primarias UUID para escalabilidad
- ✅ **Filtrado Híbrido**: JOIN + metadata para auditoría optimizada

### 📊 **Sistema de Auditoría**
- ✅ **Logging Completo**: Todas las operaciones auditadas
- ✅ **Trazabilidad**: IP, User-Agent, timestamps
- ✅ **Métricas**: Tiempo de respuesta y rendimiento
- ✅ **Exportación**: Logs exportables en CSV
- ✅ **Dashboard**: Interfaz para monitoreo de operaciones
- ✅ **Filtrado Inteligente**: Por género, editorial y autor de libros
- ✅ **Filtros Dinámicos**: Opciones obtenidas de la base de datos
- ✅ **Estrategia Híbrida**: Combina JOIN con metadata para máxima compatibilidad

### 🔐 **Seguridad**
- ✅ **Autenticación JWT**: Tokens seguros con expiración
- ✅ **Validación de Datos**: Sanitización y validación exhaustiva
- ✅ **Soft Delete**: Eliminación lógica para auditoría
- ✅ **CORS**: Configuración segura de cross-origin
- ✅ **Rate Limiting**: Protección contra ataques

## ⚡ Optimizaciones de Rendimiento

### 🚀 **Frontend Optimizations**
- **Lazy Loading**: Componentes y rutas cargados bajo demanda
- **Code Splitting**: Bundle dividido por vendor (React, Ant Design, Framer Motion, Zustand)
- **Image Optimization**: Lazy loading, async decoding, fallback automático
- **Bundle Optimization**: Terser minification, tree shaking, eliminación de console.log
- **SEO Enhancement**: Meta tags, Open Graph, Twitter Cards, preconnect, DNS prefetch

### 🗄️ **Backend Optimizations**
- **Query Optimization**: JOIN híbrido con metadata para auditoría
- **Index Strategy**: Índices compuestos para consultas frecuentes
- **Response Caching**: Headers de cache apropiados
- **Database Pooling**: Conexiones optimizadas
- **Error Handling**: Manejo eficiente de errores con fallbacks

### 📊 **Database Optimizations**
- **UUID Primary Keys**: Mejor escalabilidad y seguridad
- **Simplified Schema**: Campos directos en lugar de relaciones complejas
- **Strategic Indexing**: Índices en campos de búsqueda frecuente
- **Soft Delete**: Mantenimiento de historial sin impacto en performance
- **Hybrid Filtering**: Combina JOIN y metadata según disponibilidad

## 🏗️ Arquitectura del Sistema

```mermaid
graph TB
    subgraph "🖥️ Frontend"
        UI[React SPA]
        PWA[Progressive Web App]
    end
    
    subgraph "⚙️ Backend"
        API[NestJS API]
        AUTH[Authentication]
        AUDIT[Audit System]
    end
    
    subgraph "🗄️ Database"
        DB[(PostgreSQL)]
        LOGS[(Audit Logs)]
    end
    
    UI --> API
    PWA --> API
    API --> AUTH
    API --> AUDIT
    API --> DB
    AUDIT --> LOGS
```

## 📁 Estructura del Proyecto

```
📂 CMPC-Libros/
├── 📂 cmcp-front/              # Frontend React
│   ├── 📂 src/
│   │   ├── 📂 components/      # Componentes reutilizables
│   │   ├── 📂 pages/          # Páginas principales
│   │   ├── 📂 services/       # Servicios de API
│   │   ├── 📂 hooks/          # Custom hooks
│   │   └── 📂 types/          # Definiciones TypeScript
│   ├── 📄 package.json
│   └── 📄 README.md
├── 📂 cmpc-back/               # Backend NestJS
│   ├── 📂 src/
│   │   ├── 📂 auth/           # Módulo de autenticación
│   │   ├── 📂 books/          # Módulo de libros
│   │   ├── 📂 users/          # Módulo de usuarios
│   │   ├── 📂 common/         # Módulos compartidos
│   │   └── 📂 migrations/     # Migraciones de BD
│   ├── 📄 package.json
│   └── 📄 README.md
├── 📄 ARCHITECTURE.md          # Documentación de arquitectura
├── 📄 DATABASE_MODEL.md        # Modelo de base de datos
└── 📄 README.md               # Este archivo
```

## 🚀 Inicio Rápido

> 🎯 **Recomendación**: Usa Docker Compose para la instalación más rápida y sin complicaciones

### **🐳 Opción 1: Docker Compose (Recomendado) - Listo en 3 minutos** ⭐

**Prerrequisitos:**
- Docker Engine 20.10+
- Docker Compose 2.0+

```bash
# 1. Clonar y acceder al directorio
git clone <repository-url>
cd CMPC-Libros

# 2. [OPCIONAL] Configurar variables de entorno personalizadas
# Si quieres usar tus propias credenciales de BD, JWT secrets, etc.
cp env.production.template .env
# Editar .env con tus valores personalizados

# 3. Levantar toda la aplicación con un comando
docker-compose up -d

# 4. Esperar a que todos los servicios estén listos (1-2 minutos)
# Verificar estado de servicios
docker-compose ps

# 5. ¡Listo! Acceder a la aplicación
```

**⚠️ Nota importante**: El archivo `docker-compose.yml` incluye valores por defecto que funcionan inmediatamente. Solo necesitas crear un archivo `.env` si quieres personalizar la configuración (como usar tu propia base de datos externa, cambiar JWT secrets, etc.).

**URLs de acceso:**
- **🖥️ Aplicación Web**: http://localhost (puerto 80)
- **⚙️ Backend API**: http://localhost:3000
- **📖 Documentación API**: http://localhost:3000/docs
- **🗄️ Base de datos**: PostgreSQL en puerto 5432

### **💻 Opción 2: Instalación Manual (Desarrollo)**

**Prerrequisitos:**
- **Node.js** >= 18.0.0
- **PostgreSQL** >= 13.0
- **npm** o **pnpm**

#### **2.1. Clonar el Repositorio**
```bash
git clone <repository-url>
cd CMPC-Libros
```

#### **2.2. Configurar Backend**
```bash
cd cmpc-backend-clean
npm install
cp env.example .env
# Configurar variables de entorno en .env
npm run migration:run
npm run start:dev
```

#### **2.3. Configurar Frontend**
```bash
cd cmcp-front
npm install
# Configurar variables de entorno si es necesario
npm run dev
```

#### **2.4. Acceder a la Aplicación**
- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:3000
- **Documentación**: http://localhost:3000/docs

## 📚 Documentación Completa

### **📖 1. Documentación Técnica**

#### **📋 Guías de Proyecto**
- **[Frontend README](./cmcp-front/README.md)** - Guía completa del frontend React
- **[Backend README](./cmpc-backend/README.md)** - Guía completa del backend NestJS
- **[Arquitectura del Sistema](./ARCHITECTURE.md)** - Diseño y decisiones arquitectónicas
- **[Modelo de Base de Datos](./DATABASE_MODEL.md)** - Esquema relacional y optimizaciones

#### **🛠️ 2. Instalación y Configuración**

##### **Prerrequisitos del Sistema**
```bash
# Versiones requeridas
Node.js >= 18.0.0
PostgreSQL >= 13.0
npm >= 8.0.0 o pnpm >= 7.0.0
Git >= 2.30.0
```

##### **🔧 Configuración del Backend**
```bash
# 1. Navegar al directorio del backend
cd cmpc-backend

# 2. Instalar dependencias
npm install

# 3. Configurar variables de entorno
cp env.example .env

# 4. Configurar la base de datos en .env
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_USERNAME=cmpc_user
DATABASE_PASSWORD=your_password
DATABASE_NAME=cmpc_books
JWT_SECRET=your-super-secret-jwt-key
JWT_EXPIRES_IN=1h
JWT_REFRESH_EXPIRES_IN=7d

# 5. Crear la base de datos
createdb cmpc_books

# 6. Ejecutar migraciones
npm run migration:run

# 7. Semilla inicial (opcional)
npm run seed:run

# 8. Iniciar en modo desarrollo
npm run start:dev

# ✅ Backend disponible en: http://localhost:3000
# ✅ Documentación API: http://localhost:3000/docs
```

##### **🎨 Configuración del Frontend**
```bash
# 1. Navegar al directorio del frontend
cd cmcp-front

# 2. Instalar dependencias
npm install

# 3. Configurar variables de entorno
cp .env.example .env.local

# 4. Configurar la API en .env.local
VITE_API_URL=http://localhost:3000/api/v1
VITE_APP_NAME=CMPC Libros
VITE_APP_VERSION=1.0.0

# 5. Iniciar en modo desarrollo
npm run dev

# ✅ Frontend disponible en: http://localhost:5173
```

##### **🐳 Configuración con Docker Compose (Recomendado)**

**Prerrequisitos:**
- Docker Engine 20.10+ 
- Docker Compose 2.0+

```bash
# 1. Clonar el repositorio
git clone <repository-url>
cd CMPC-Libros

# 2. Configurar variables de entorno (opcional - valores por defecto incluidos)
cp env.production.template .env

# 3. Construir y ejecutar todos los servicios
docker-compose up -d

# 4. Verificar que todos los servicios estén corriendo
docker-compose ps

# 5. Ver logs en tiempo real (opcional)
docker-compose logs -f

# ✅ Aplicación completa disponible:
# Frontend: http://localhost (puerto 80)
# Backend API: http://localhost:3000
# Documentación API: http://localhost:3000/docs
# Base de datos: PostgreSQL en puerto 5432
```

**Comandos útiles de Docker Compose:**
```bash
# Parar todos los servicios
docker-compose down

# Reconstruir servicios después de cambios en código
docker-compose up -d --build

# Ver logs de un servicio específico
docker-compose logs -f backend
docker-compose logs -f frontend
docker-compose logs -f database

# Ejecutar comandos dentro de un contenedor
docker-compose exec backend npm run migration:run
docker-compose exec database psql -U postgres -d railway

# Limpiar volúmenes (¡CUIDADO: elimina datos de BD!)
docker-compose down -v

# Monitorear recursos
docker-compose top
```

**Arquitectura de contenedores:**
- **frontend**: Nginx sirviendo React SPA (puerto 80)
- **backend**: NestJS API (puerto 3000)  
- **database**: PostgreSQL 15 (puerto 5432)
- **Redes**: Todos los servicios en red privada `cmpc-network`
- **Volúmenes**: Persistencia de datos PostgreSQL
- **Health checks**: Verificación automática de estado de servicios

### **🔧 Variables de Entorno Personalizables**

Si quieres personalizar la configuración, crea un archivo `.env` en la raíz del proyecto:

```bash
# Copiar template y personalizar
cp env.production.template .env
```

**Variables principales que puedes personalizar:**
```env
# Base de datos (si usas BD externa)
DATABASE_HOST=tu-host-externo.com
DATABASE_PORT=5432
DATABASE_USER=tu-usuario
DATABASE_PASSWORD=tu-password
DATABASE_NAME=tu-base-de-datos

# JWT Secrets (recomendado cambiar en producción)
JWT_SECRET=tu-jwt-secret-super-seguro
JWT_REFRESH_SECRET=tu-refresh-secret-super-seguro

# Configuración de aplicación
NODE_ENV=production
CORS=true

# Frontend (si cambias la URL del backend)
VITE_API_URL=http://localhost:3000
```

**⚠️ Importante:** Si no creas un archivo `.env`, se usarán los valores por defecto incluidos en `docker-compose.yml` que funcionan perfectamente para desarrollo y testing local.

### **✅ Verificación de la Instalación**

Después de ejecutar `docker-compose up -d`, verifica que todo funcione correctamente:

```bash
# 1. Verificar que todos los servicios estén corriendo
docker-compose ps
# Deberías ver: database (healthy), backend (healthy), frontend (healthy)

# 2. Verificar logs por si hay errores
docker-compose logs --tail=20

# 3. Probar endpoints principales
curl http://localhost:3000/api/v1/books          # Backend API
curl http://localhost                            # Frontend web

# 4. Acceder a la documentación de la API
# Abrir en navegador: http://localhost:3000/docs
```

**Estado esperado:**
- ✅ Base de datos PostgreSQL corriendo en puerto 5432
- ✅ Backend NestJS corriendo en puerto 3000
- ✅ Frontend React servido por Nginx en puerto 80
- ✅ Health checks pasando para todos los servicios
- ✅ API accesible en http://localhost:3000/docs

#### **📖 3. Guía de Uso de la Aplicación**

##### **🚀 Primeros Pasos**
1. **Acceso inicial**: Navega a http://localhost:5173
2. **Crear cuenta**: Registra un nuevo usuario desde la página de registro
3. **Iniciar sesión**: Utiliza tus credenciales para acceder al dashboard
4. **Explorar funciones**: Navega por las diferentes secciones

##### **👥 Gestión de Usuarios**
```typescript
// Roles disponibles
enum UserRole {
  ADMIN = 'admin',      // Acceso completo al sistema
  EDITOR = 'editor',    // Puede crear y editar libros
  VIEWER = 'viewer'     // Solo lectura
}

// Permisos por rol
ADMIN: {
  - Gestión completa de libros (CRUD)
  - Administración de usuarios
  - Acceso a auditoría completa
  - Exportación de datos
  - Configuración del sistema
}

EDITOR: {
  - Crear y editar libros
  - Ver inventario
  - Acceso limitado a auditoría
  - Exportar reportes básicos
}

VIEWER: {
  - Solo lectura de inventario
  - Búsqueda de libros
  - Ver estadísticas básicas
}
```

##### **📚 Gestión de Libros**
```markdown
## Crear un Libro
1. Ir a "Libros" → "Agregar Libro"
2. Completar información obligatoria:
   - Título
   - Autor
   - Editorial
   - Género
   - Precio
3. Información opcional:
   - ISBN/ISBN13
   - Año de publicación
   - Número de páginas
   - Descripción
   - Imagen de portada
4. Configurar inventario:
   - Cantidad en stock
   - Stock mínimo
5. Guardar libro

## Buscar y Filtrar
- **Búsqueda general**: Texto libre en título, autor o editorial
- **Filtros avanzados**:
  - Por género
  - Por editorial
  - Por rango de precios
  - Por disponibilidad
- **Ordenamiento**: Título, autor, precio, fecha de creación

## Gestión de Stock
- **Actualización manual**: Editar cantidad desde el formulario
- **Alertas automáticas**: Notificación cuando stock < stock mínimo
- **Historial**: Trazabilidad completa en auditoría
```

##### **📊 Sistema de Auditoría**
```markdown
## Dashboard de Auditoría
- **Estadísticas generales**: Total de operaciones, usuarios activos
- **Actividad reciente**: Últimas 50 operaciones
- **Métricas de rendimiento**: Tiempo promedio de respuesta

## Filtros de Auditoría
- **Por usuario**: Ver actividad de usuario específico
- **Por acción**: CREATE, UPDATE, DELETE, LOGIN, etc.
- **Por fecha**: Rango de fechas personalizable
- **Por entidad**: Libros, usuarios, sesiones
- **Por estado**: Exitoso, fallido, pendiente

## Exportación de Logs
- **Formato CSV**: Exportar logs filtrados
- **Campos incluidos**: Usuario, acción, fecha, IP, detalles
- **Uso**: Auditoría externa, cumplimiento, análisis
```

#### **🔧 4. Documentación de API (Swagger/OpenAPI)**

##### **📡 Acceso a la Documentación**
- **Swagger UI**: http://localhost:3000/docs
- **OpenAPI JSON**: http://localhost:3000/docs-json
- **ReDoc**: http://localhost:3000/redoc (alternativa)

##### **🔐 Autenticación en Swagger**
```typescript
// 1. Obtener token JWT
POST /api/v1/auth/login
{
  "email": "user@example.com",
  "password": "password123"
}

// 2. Usar token en Swagger
// Hacer clic en "Authorize" en Swagger UI
// Formato: Bearer <token>
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

##### **📊 Endpoints Principales**

###### **🔐 Autenticación**
```http
POST   /api/v1/auth/login           # Iniciar sesión
POST   /api/v1/auth/register        # Registrar usuario
POST   /api/v1/auth/refresh         # Renovar token
GET    /api/v1/auth/me             # Perfil del usuario
POST   /api/v1/auth/logout         # Cerrar sesión
PATCH  /api/v1/auth/update-role    # Actualizar rol (admin)
```

###### **📚 Gestión de Libros**
```http
GET    /api/v1/books               # Listar libros (paginado)
POST   /api/v1/books               # Crear nuevo libro
GET    /api/v1/books/:id           # Obtener libro por ID
PATCH  /api/v1/books/:id           # Actualizar libro
DELETE /api/v1/books/:id           # Eliminar libro (soft delete)
POST   /api/v1/books/search        # Búsqueda avanzada
GET    /api/v1/books/genres        # Obtener géneros disponibles
GET    /api/v1/books/publishers    # Obtener editoriales
POST   /api/v1/books/upload-image  # Subir imagen de portada
GET    /api/v1/books/export/csv    # Exportar libros en CSV
```

###### **👥 Gestión de Usuarios**
```http
GET    /api/v1/users               # Listar usuarios (admin)
POST   /api/v1/users               # Crear usuario (admin)
GET    /api/v1/users/:id           # Obtener usuario por ID
PATCH  /api/v1/users/:id           # Actualizar usuario
DELETE /api/v1/users/:id           # Eliminar usuario (admin)
```

###### **📊 Auditoría y Logs**
```http
GET    /api/v1/audit-logs          # Listar logs de auditoría
GET    /api/v1/audit-logs/stats    # Estadísticas de auditoría
GET    /api/v1/audit-logs/inventory # Logs específicos de inventario
GET    /api/v1/audit-logs/inventory/filter-options # Opciones de filtrado
GET    /api/v1/audit-logs/export   # Exportar logs en CSV
DELETE /api/v1/audit-logs/delete-all # Limpiar logs (admin)
```

##### **📝 Ejemplos de Uso de API**

###### **Crear un Libro**
```typescript
// POST /api/v1/books
{
  "title": "Clean Code",
  "author": "Robert C. Martin",
  "publisher": "Prentice Hall",
  "genre": "Programming",
  "price": 45.99,
  "isbn": "978-0132350884",
  "publication_year": 2008,
  "pages": 464,
  "language": "en",
  "description": "A handbook of agile software craftsmanship",
  "stock_quantity": 50,
  "minimum_stock": 10
}

// Respuesta
{
  "status": "success",
  "data": {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "title": "Clean Code",
    "author": "Robert C. Martin",
    // ... otros campos
    "created_at": "2024-01-15T10:30:00Z",
    "updated_at": "2024-01-15T10:30:00Z"
  },
  "message": "Libro creado exitosamente"
}
```

###### **Búsqueda Avanzada**
```typescript
// POST /api/v1/books/search
{
  "query": {
    "title": "Clean",
    "genre": "Programming", 
    "price_min": 20,
    "price_max": 60,
    "in_stock": true,
    "sortBy": "title",
    "sortDir": "asc",
    "page": 1,
    "limit": 10
  }
}
```

#### **🏗️ 5. Diagrama de Arquitectura del Sistema**

##### **📊 Arquitectura de Alto Nivel**
```mermaid
graph TB
    subgraph "🌐 Capa de Presentación"
        UI[React SPA]
        PWA[Progressive Web App]
        MOBILE[Mobile Responsive]
    end

    subgraph "⚙️ Capa de Aplicación"
        NGINX[Load Balancer]
        API[NestJS API Server]
        
        subgraph "🔐 Seguridad"
            AUTH[JWT Authentication]
            GUARD[Auth Guards]
            VALID[Validation Pipes]
        end
        
        subgraph "📚 Dominio de Negocio"
            BOOKS[Books Module]
            USERS[Users Module] 
            AUDIT[Audit Module]
        end
        
        subgraph "🛡️ Infraestructura"
            INTERCEPT[Interceptors]
            FILTER[Exception Filters]
            PIPE[Transform Pipes]
        end
    end

    subgraph "🗄️ Capa de Datos"
        DB[(PostgreSQL)]
        REDIS[(Redis Cache)]
        GCS[Google Cloud Storage]
    end

    subgraph "📊 Monitoreo"
        LOGS[Application Logs]
        METRICS[Performance Metrics]
        ALERTS[Alert System]
    end

    UI --> NGINX
    PWA --> NGINX
    MOBILE --> NGINX
    
    NGINX --> API
    API --> AUTH
    API --> BOOKS
    API --> USERS
    API --> AUDIT
    
    BOOKS --> DB
    USERS --> DB
    AUDIT --> DB
    
    API --> REDIS
    API --> GCS
    
    API --> LOGS
    API --> METRICS
    METRICS --> ALERTS

    classDef frontend fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef backend fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef database fill:#e8f5e8,stroke:#1b5e20,stroke-width:2px
    classDef monitoring fill:#fff3e0,stroke:#e65100,stroke-width:2px
    
    class UI,PWA,MOBILE frontend
    class NGINX,API,AUTH,GUARD,VALID,BOOKS,USERS,AUDIT,INTERCEPT,FILTER,PIPE backend
    class DB,REDIS,GCS database
    class LOGS,METRICS,ALERTS monitoring
```

##### **🔄 Flujo de Datos Principal**
```mermaid
sequenceDiagram
    participant User as 👤 Usuario
    participant UI as 🖥️ React SPA
    participant API as ⚙️ NestJS API
    participant Auth as 🔐 Auth Service
    participant DB as 🗄️ PostgreSQL
    participant Audit as 📊 Audit Service

    User->>UI: Acción (ej: crear libro)
    UI->>API: HTTP Request + JWT
    API->>Auth: Validar token
    Auth-->>API: Usuario autenticado
    API->>DB: Operación CRUD
    DB-->>API: Resultado
    API->>Audit: Registrar operación
    Audit->>DB: Guardar log
    API-->>UI: Respuesta exitosa
    UI-->>User: Interfaz actualizada
```

#### **🗄️ 6. Modelo Relacional de Base de Datos**

##### **📊 Diagrama Entidad-Relación**
```mermaid
erDiagram
    USERS {
        uuid id PK
        string email UK
        string password
        string first_name
        string last_name
        int role_id FK
        boolean is_active
        timestamp last_login
        timestamp created_at
        timestamp updated_at
        timestamp deleted_at
    }

    BOOKS {
        uuid id PK
        string title
        string isbn UK
        string isbn13
        int publication_year
        string edition
        int pages
        string language
        text description
        string cover_image
        decimal price
        int stock_quantity
        int minimum_stock
        string genre
        string publisher
        string author
        boolean is_active
        timestamp created_at
        timestamp updated_at
        timestamp deleted_at
    }

    AUDIT_LOGS {
        uuid id PK
        string user_id
        string user_email
        string user_name
        string action
        string entity_type
        string entity_id
        text description
        jsonb request_data
        jsonb response_data
        string status
        string level
        string ip_address
        string user_agent
        string endpoint
        string http_method
        int response_time_ms
        text error_message
        jsonb metadata
        boolean is_active
        timestamp created_at
        timestamp updated_at
        timestamp deleted_at
    }

    AUTH_SESSIONS {
        uuid id PK
        uuid user_id FK
        string access_token
        string refresh_token
        string token_type
        timestamp expires_at
        string ip_address
        text user_agent
        boolean is_active
        timestamp created_at
        timestamp updated_at
        timestamp deleted_at
    }

    USERS ||--o{ AUTH_SESSIONS : "mantiene"
    USERS ||--o{ AUDIT_LOGS : "genera"
    BOOKS ||--o{ AUDIT_LOGS : "audita"
```

##### **🔍 Características del Modelo**
- **UUIDs**: Claves primarias UUID para mejor escalabilidad
- **Soft Delete**: Eliminación lógica en todas las entidades
- **Auditoría Completa**: Trazabilidad de todas las operaciones
- **Índices Estratégicos**: Optimización para consultas frecuentes
- **JSONB**: Datos flexibles para auditoría y metadata
- **Constraints**: Validación de integridad a nivel de base de datos

##### **📈 Optimizaciones de Performance**
```sql
-- Índices para búsquedas frecuentes
CREATE INDEX idx_books_title ON books(title);
CREATE INDEX idx_books_author ON books(author);
CREATE INDEX idx_books_genre ON books(genre);
CREATE INDEX idx_audit_user_created ON audit_logs(user_id, created_at);

-- Índices para soft delete
CREATE INDEX idx_books_active ON books(is_active, deleted_at);
CREATE INDEX idx_audit_active ON audit_logs(is_active, deleted_at);

-- Índices para texto completo
CREATE INDEX idx_books_search ON books USING gin(to_tsvector('spanish', title || ' ' || author));
```

#### **📊 7. Métricas y Monitoreo**

##### **📈 KPIs del Sistema**
- **Performance**: Tiempo promedio de respuesta < 200ms
- **Disponibilidad**: Uptime > 99.5%
- **Errores**: Tasa de error < 1%
- **Usuarios**: Sesiones activas, nuevos registros
- **Inventario**: Libros añadidos, actualizaciones, búsquedas

##### **🔍 Logs y Auditoría**
- **Formato estructurado**: JSON con campos estándar
- **Niveles**: ERROR, WARN, INFO, DEBUG
- **Rotación**: Automática con retención de 90 días
- **Alertas**: Notificaciones en tiempo real para errores críticos

#### **🚀 8. Deployment y DevOps**

##### **🐳 Containerización**
```dockerfile
# Backend Dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "run", "start:prod"]

# Frontend Dockerfile  
FROM node:18-alpine as builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

##### **🔄 CI/CD Pipeline**
```yaml
# .github/workflows/deploy.yml
name: Deploy to Production
on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
      - run: npm ci
      - run: npm run test
      - run: npm run lint

  deploy:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to Railway
        run: railway deploy
```

### **📖 Recursos Adicionales**

#### **🎓 Tutoriales y Guías**
- **[Video Tutorial Completo](https://youtube.com/watch?v=cmpc-tutorial)** - Guía paso a paso
- **[Postman Collection](./docs/CMPC-Books.postman_collection.json)** - Colección de API
- **[Casos de Uso](./docs/use-cases.md)** - Ejemplos prácticos
- **[FAQ](./docs/faq.md)** - Preguntas frecuentes

#### **🛠️ Herramientas de Desarrollo**
- **TypeScript**: Tipado estático para mejor desarrollo
- **ESLint + Prettier**: Código consistente y formateado
- **Jest**: Testing unitario y de integración
- **Swagger**: Documentación interactiva de API
- **Mermaid**: Diagramas como código

#### **🔗 Enlaces Útiles**
- **[Repositorio GitHub](https://github.com/cmpc-books)**
- **[Issues y Bugs](https://github.com/cmpc-books/issues)**
- **[Roadmap del Proyecto](https://github.com/cmpc-books/projects)**
- **[Contribuciones](./CONTRIBUTING.md)**

## 🛠️ Stack Tecnológico

### **Frontend**
| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| React | 18.3.1 | Biblioteca de UI con Lazy Loading |
| TypeScript | 5.3.3 | Tipado estático |
| Ant Design | 5.27.2 | Componentes UI |
| Tailwind CSS | 4.1.10 | Framework CSS |
| Framer Motion | 11.0.3 | Animaciones |
| Zustand | 5.0.8 | Gestión de estado |
| Vite | 5.0.0 | Build tool con optimizaciones |
| React Router | 6.8.0 | Routing con code splitting |

### **Backend**
| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| NestJS | 10.0.0 | Framework Node.js |
| TypeScript | 4.9.5 | Tipado estático |
| PostgreSQL | 13+ | Base de datos con UUIDs |
| TypeORM | 0.3.20 | ORM con migraciones |
| JWT | 9.0.2 | Autenticación |
| Swagger | 7.0.0 | Documentación |
| Jest | 30.0.0 | Testing |
| bcrypt | 5.1.0 | Encriptación de passwords |

## 🧪 Testing y Calidad

### **Comandos de Testing**
```bash
# Frontend
cd cmcp-front
npm run test              # Tests unitarios
npm run test:coverage     # Con cobertura
npm run lint              # Linting
npm run type-check        # Verificación de tipos

# Backend
cd cmpc-back
npm run test              # Tests unitarios
npm run test:e2e          # Tests e2e
npm run test:cov          # Con cobertura
npm run lint              # Linting
```

### **Métricas de Calidad**
- 🎯 **Cobertura de Tests**: 95%+
- ✅ **TypeScript Strict**: Habilitado
- 🔍 **ESLint**: Configurado con reglas estrictas
- 📝 **Prettier**: Formateo automático
- 🛡️ **Security**: Dependencias auditadas

## 🚀 Deployment

### **Desarrollo Local**
```bash
# Backend
cd cmpc-back
npm run start:dev

# Frontend
cd cmcp-front
npm run dev
```

### **Producción con Docker**
```bash
# Backend
cd cmpc-back
docker build -t cmpc-backend .
docker run -p 3001:3001 cmpc-backend

# Frontend
cd cmcp-front
docker build -t cmpc-frontend .
docker run -p 5173:5173 cmpc-frontend
```

### **🐳 Docker Compose (Producción)**
```bash
# Levantar todos los servicios
docker-compose up -d

# Ver estado de servicios
docker-compose ps

# Ver logs en tiempo real
docker-compose logs -f

# Parar servicios
docker-compose down

# Reconstruir después de cambios
docker-compose up -d --build
```

### **🔧 Comandos útiles Docker**
```bash
# Solo base de datos
docker-compose up -d database

# Ejecutar migraciones
docker-compose exec backend npm run migration:run

# Acceder a la base de datos
docker-compose exec database psql -U postgres -d railway

# Monitorear recursos
docker-compose top

# Limpiar sistema (¡CUIDADO!)
docker-compose down -v --remove-orphans
```

## 🔧 Solución de Problemas (Docker)

### **❌ Problemas Comunes**

#### **1. Error: "Port already in use"**
```bash
# Ver qué procesos usan los puertos
sudo lsof -i :80    # Frontend
sudo lsof -i :3000  # Backend  
sudo lsof -i :5432  # Database

# Matar proceso específico
sudo kill -9 <PID>

# O cambiar puertos en docker-compose.yml
```

#### **2. Error: "Database connection failed"**
```bash
# Verificar que la BD esté ejecutándose
docker-compose ps

# Ver logs de la base de datos
docker-compose logs database

# Reiniciar solo la base de datos
docker-compose restart database

# Verificar salud del contenedor
docker-compose exec database pg_isready -U postgres
```

#### **3. Error: "Backend health check failed"**
```bash
# Ver logs detallados del backend
docker-compose logs backend

# Verificar variables de entorno
docker-compose exec backend env | grep DATABASE

# Probar conexión manual
docker-compose exec backend node -e "console.log('Backend running')"

# Reconstruir solo el backend
docker-compose up -d --build backend
```

#### **4. Error: "Frontend not loading"**
```bash
# Verificar nginx está corriendo
docker-compose exec frontend nginx -t

# Ver logs de nginx
docker-compose logs frontend

# Verificar archivos compilados
docker-compose exec frontend ls -la /usr/share/nginx/html/
```

### **🔄 Comandos de Diagnóstico**
```bash
# Estado completo del sistema
docker-compose ps
docker system df
docker system prune

# Logs por tiempo
docker-compose logs --since=10m
docker-compose logs --tail=50

# Información detallada de contenedores
docker-compose exec backend cat /proc/version
docker-compose exec backend df -h
docker-compose exec backend free -h
```

### **🚨 Comandos de Emergencia**
```bash
# Reinicio completo limpio
docker-compose down
docker system prune -f
docker-compose up -d --build

# Reset completo (¡PIERDE DATOS!)
docker-compose down -v
docker system prune -a -f
docker-compose up -d --build
```

## 🔒 Seguridad

### **Implementaciones de Seguridad**
- ✅ **JWT Authentication** con refresh tokens
- ✅ **Password Hashing** con bcrypt (12 salt rounds)
- ✅ **Input Validation** con class-validator
- ✅ **SQL Injection Protection** con TypeORM
- ✅ **CORS Configuration** configurable
- ✅ **Rate Limiting** para prevenir ataques
- ✅ **Audit Logging** de todas las operaciones
- ✅ **Soft Delete** para auditoría completa

### **Mejores Prácticas**
- Validación de entrada en frontend y backend
- Sanitización de datos de usuario
- Headers de seguridad configurados
- Tokens JWT con expiración apropiada
- Logs de seguridad y monitoreo

## 📊 Monitoreo y Observabilidad

### **Sistema de Logging**
- **Niveles**: ERROR, WARN, INFO, DEBUG
- **Formato**: JSON estructurado
- **Rotación**: Automática de logs
- **Métricas**: Tiempo de respuesta, errores, uso

### **Dashboard de Auditoría**
- Visualización de logs en tiempo real
- Filtros por usuario, acción, fecha
- Exportación de datos en CSV
- Estadísticas de uso del sistema

## 🤝 Contribución

### **Proceso de Contribución**
1. Fork del repositorio
2. Crear rama feature: `git checkout -b feature/nueva-funcionalidad`
3. Commit cambios: `git commit -m 'feat: agregar nueva funcionalidad'`
4. Push a la rama: `git push origin feature/nueva-funcionalidad`
5. Crear Pull Request

### **Estándares de Código**
- **TypeScript strict mode**
- **ESLint + Prettier** configurados
- **Conventional Commits**
- **Tests obligatorios** para nuevas features
- **Documentación actualizada**

## 📈 Roadmap

### **Fase 1 (Actual) ✅**
- ✅ Sistema básico de gestión de libros
- ✅ Autenticación JWT
- ✅ Sistema de auditoría
- ✅ Documentación completa
- ✅ Testing y CI/CD

### **Fase 2 (Próxima) 🔄**
- 🔄 Microservicios por dominio
- 🔄 Caché con Redis
- 🔄 Notificaciones en tiempo real
- 🔄 Reportes avanzados
- 🔄 API GraphQL

### **Fase 3 (Futuro) 📋**
- 📋 Machine Learning para recomendaciones
- 📋 Integración con sistemas externos
- 📋 Mobile app nativa
- 📋 Analytics avanzados
- 📋 Multi-tenancy

## 📄 Licencia

Este proyecto está bajo la **Licencia MIT**. Ver el archivo [LICENSE](LICENSE) para más detalles.

## 🆘 Soporte

### **Canales de Comunicación**
- 🐛 **Issues**: [GitHub Issues](https://github.com/cmpc-books/issues)
- 💡 **Feature Requests**: [GitHub Discussions](https://github.com/cmpc-books/discussions)
- 📧 **Email**: dev@cmpc-books.com
- 📖 **Wiki**: [Documentación del Proyecto](https://github.com/cmpc-books/wiki)

### **Recursos Adicionales**
- [📖 Guía de Usuario](https://github.com/cmpc-books/wiki/user-guide)
- [🎥 Video Tutoriales](https://youtube.com/cmpc-books)
- [📝 Blog Técnico](https://blog.cmpc-books.com)

## 🙏 Agradecimientos

- [React](https://reactjs.org/) por la biblioteca de UI
- [NestJS](https://nestjs.com/) por el framework backend
- [PostgreSQL](https://www.postgresql.org/) por la base de datos
- [Ant Design](https://ant.design/) por los componentes UI
- [TypeORM](https://typeorm.io/) por el ORM
- [Swagger](https://swagger.io/) por la documentación

---

<div align="center">

### **✨ Desarrollado con ❤️ por el equipo de CMPC**

*"Code is poetry written in TypeScript"*

[![Made with Love](https://img.shields.io/badge/Made%20with-❤️-red?style=for-the-badge)](https://github.com/cmpc-books)
[![Powered by NestJS](https://img.shields.io/badge/Powered%20by-NestJS-E0234E?style=for-the-badge&logo=nestjs)](https://nestjs.com/)
[![Built for Developers](https://img.shields.io/badge/Built%20for-Developers-blue?style=for-the-badge)](https://github.com/cmpc-books)

</div>
