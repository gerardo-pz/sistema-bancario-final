# 💳 Sistema Bancario

Sistema web desarrollado con **Django** para la gestión de operaciones bancarias básicas como creación de cuentas, envío de transacciones, auditoría y administración de usuarios. Diseñado para simular el comportamiento de una plataforma bancaria real.

---

## 📚 Tabla de Contenidos

- [🎯 Objetivo](#-objetivo)
- [🚀 Funcionalidades Principales](#-funcionalidades-principales)
- [🛠️ Tecnologías Utilizadas](#️-tecnologías-utilizadas)
- [⚙️ Instalación y Ejecución](#️-instalación-y-ejecución)
- [🌐 Despliegue en Render](#-despliegue-en-render)
- [📁 Estructura del Proyecto](#-estructura-del-proyecto)

---

## 🎯 Objetivo

Este proyecto tiene como propósito simular un sistema bancario básico que permita registrar usuarios, gestionar sus cuentas, realizar transacciones entre ellas y mantener un historial auditable de todas las operaciones.

---

## 🚀 Funcionalidades Principales

- 🧑 Registro y autenticación de usuarios
- 💼 Creación y gestión de cuentas bancarias
- 💸 Transferencias entre cuentas
- 📬 Gestión de solicitudes (autorizaciones, revisiones)
- 📜 Auditoría de eventos y operaciones del sistema
- 📚 Implementación de estructuras de datos clásicas (pila, cola, árbol binario, lista enlazada)

---

## 🛠️ Tecnologías Utilizadas

- **Lenguaje:** Python 3.x
- **Framework:** Django
- **Base de datos:** PostgreSQL 
- **Frontend:** Tailwind CSS v4 (CDN)
- **Servidor:** Gunicorn
- **Otros:** 
  - Django Admin
  - Django ORM
  - Virtualenv
  - WhiteNoise (servir archivos estáticos)

---

## ⚙️ Instalación y Ejecución

Sigue estos pasos para correr el proyecto localmente:

### 1. Clona el repositorio

```bash
git clone https://github.com/gerardo-pz/sistema-bancario-final.git
cd sistema-bancario-final
```

### 2. Crea un entorno virtual

```bash
# En Windows
python -m venv venv
venv\Scripts\activate
```

### 3. Instala las dependencias

```bash
pip install -r requirements.txt
```

### 4. Configura la base de datos PostgreSQL

Asegúrate de tener PostgreSQL instalado y crea una base de datos llamada `django_sistema_bancario`.

### 5. Ejecuta las migraciones

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Crea un superusuario (opcional)

```bash
python manage.py createsuperuser
```

### 7. Ejecuta el servidor

```bash
python manage.py runserver
```

### 8. Accede a la aplicación

Abre tu navegador y ve a `http://localhost:8000`

---

## 🌐 Despliegue en Render

### Opción 1: Despliegue Automático (Recomendado)

1. **Fork o clona este repositorio** en tu cuenta de GitHub

2. **Ve a [Render.com](https://render.com)** y crea una cuenta

3. **Crea un nuevo Web Service**:
   - Conecta tu repositorio de GitHub
   - Selecciona el repositorio `sistema-bancario-final`
   - Render detectará automáticamente que es un proyecto Django

4. **Configura las variables de entorno**:
   ```
   SECRET_KEY = [generar una clave secreta]
   DEBUG = false
   ALLOWED_HOSTS = .onrender.com
   DATABASE_URL = [se configurará automáticamente]
   ```

5. **Haz clic en "Create Web Service"**

### Opción 2: Despliegue Manual

1. **Sube los cambios a GitHub**:
   ```bash
   git add .
   git commit -m "Configuración para Render"
   git push origin main
   ```

2. **En Render, crea un nuevo Web Service** con estas configuraciones:
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn sistema_bancario.wsgi:application`
   - **Python Version**: 3.11.0

3. **Configura la base de datos PostgreSQL** en Render

### 📁 Estructura del Proyecto
```text
sistema-bancario-final/
├── auditoria/         # Módulo de auditoría de operaciones
├── cuentas/           # Lógica para cuentas bancarias
├── solicitudes/       # Gestión de solicitudes entre usuarios/cuentas
├── transacciones/     # Envío y recepción de dinero
├── usuarios/          # Registro y autenticación de usuarios
├── utils/             # Implementaciones de estructuras de datos
├── sistema_bancario/  # Configuración global del proyecto Django
├── manage.py          # Script de gestión del proyecto
├── requirements.txt   # Lista de dependencias
├── render.yaml        # Configuración para Render
└── build.sh           # Script de build para Render
```

---

## 🎨 Características del Frontend

- **Tailwind CSS v4**: Framework CSS moderno para un diseño responsive y atractivo
- **Diseño Responsive**: Se adapta a dispositivos móviles, tablets y desktop
- **Interfaz Moderna**: Componentes con efectos hover, transiciones suaves y sombras
- **Navegación Intuitiva**: Menú de navegación con diseño hamburguesa para móviles

---

## 🔧 Archivos de Configuración

- `render.yaml`: Configuración automática para Render
- `build.sh`: Script de construcción para el despliegue
- `requirements.txt`: Dependencias de Python actualizadas
- `sistema_bancario/settings.py`: Configuración optimizada para producción