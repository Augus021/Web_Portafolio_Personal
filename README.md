# 🚀 DevPortfolio — Página Web Personal

![Estado](https://img.shields.io/badge/estado-activo-brightgreen)
![Docker](https://img.shields.io/badge/docker-ready-blue)
![Nginx](https://img.shields.io/badge/servidor-nginx%3Aalpine-009639)


 ---
 


## 📝 Descripción

DevPortfolio es una página web estática de presentación personal orientada a desarrolladores de software. Como podran observar es un buen modelo de Pagina Portfolio para poder destacar nuestras habilidades. Cuenta con un diseño moderno de tema oscuro, animaciones fluidas y secciones completas para mostrar habilidades, proyectos y experiencia profesional.

El proyecto está completamente **dockerizado** usando **Nginx** como servidor web, lo que permite desplegarlo en cualquier entorno de forma rápida, portable y sin dependencias adicionales.

### ✨ Características principales

- Diseño dark mode con paleta eléctrica (azul, violeta, verde neón)
- Animación typewriter en el título del hero
- Partículas flotantes animadas en el fondo (canvas)
- Secciones: Inicio, Sobre Mí, Habilidades, Proyectos, Experiencia y Contacto
- Barras de progreso animadas al hacer scroll
- Timeline de experiencia profesional
- Formulario de contacto con feedback visual
- Navegación fija con indicador de sección activa
- Diseño 100% responsive (mobile-friendly)

---

## 🛠️ Tecnologías Utilizadas

### Frontend
| Tecnología | Uso |
|---|---|
| HTML5 | Estructura y semántica de la página |
| CSS3 | Estilos, animaciones, variables CSS, Grid y Flexbox |
| JavaScript (ES6+) | Partículas, typewriter, scroll reveal, nav activa |
| Google Fonts | Tipografías: Space Grotesk, Inter, JetBrains Mono |

### Infraestructura
| Tecnología | Uso |
|---|---|
| Docker | Contenerización de la aplicación |
| Nginx (Alpine) | Servidor web para archivos estáticos |
| Docker Hub | Registro de imágenes base |

---

## ✅ Requisitos Previos

Antes de comenzar, asegurate de tener instalado:

- **Docker Desktop** (versión 20.x o superior)
  - Windows/Mac: [docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)
  - Linux: seguir la guía oficial de [docs.docker.com](https://docs.docker.com/engine/install/)

- **Git** (opcional, para clonar el repositorio)
  - [git-scm.com/downloads](https://git-scm.com/downloads)

### Verificar instalación de Docker

Abrí una terminal y ejecutá:

```bash
docker --version
```

Deberías ver algo como:
```
Docker version 24.0.5, build ced0996
```

---

## 📂 Estructura del Proyecto

```
mi-portfolio/
├── index.html       # Estructura HTML de la página
├── styles.css       # Estilos, animaciones y diseño responsive
├── script.js        # Lógica: partículas, typewriter, scroll reveal
├── Dockerfile       # Instrucciones para construir la imagen Docker
└── README.md        # Este archivo
```

---

## ⚙️ Pasos de Instalación

### 1. Clonar o descargar el proyecto

**Opción A — Con Git:**
```bash
git clone https://github.com/tu-usuario/mi-portfolio.git
cd mi-portfolio
```

**Opción B — Descarga manual:**
Descargá los archivos y copiá `index.html`, `styles.css`, `script.js`, `Dockerfile` y `README.md` dentro de una carpeta llamada `mi-portfolio`.

### 2. Verificar que todos los archivos estén presentes

```bash
# En Windows (CMD o PowerShell)
dir

# En Linux/Mac
ls -la
```

Deberías ver:
```
Dockerfile
index.html
README.md
script.js
styles.css
```

---

## 🐳 Construcción de la Imagen Docker

Dentro de la carpeta del proyecto, ejecutá el siguiente comando para construir la imagen:

```bash
docker build -t mi-portfolio:v1 .
```

### ¿Qué hace este comando?

| Parte | Descripción |
|---|---|
| `docker build` | Construye una imagen a partir del Dockerfile |
| `-t mi-portfolio:v1` | Asigna el nombre `mi-portfolio` con la etiqueta `v1` |
| `.` | Usa el Dockerfile de la carpeta actual |

### Salida esperada

```
[+] Building 4.1s (8/8) FINISHED
 => [internal] load build definition from Dockerfile
 => [1/3] FROM docker.io/library/nginx:alpine
 => [2/3] COPY index.html /usr/share/nginx/html/index.html
 => [3/3] COPY styles.css + script.js ...
 => exporting to image
 => naming to docker.io/library/mi-portfolio:v1  ✓
```

### Verificar que la imagen se creó

```bash
docker images
```

```
REPOSITORY       TAG       IMAGE ID       CREATED         SIZE
mi-portfolio     v1        a1b2c3d4e5f6   2 minutes ago   43MB
```

---

## ▶️ Ejecución del Contenedor

### Iniciar el contenedor

```bash
docker run -d -p 8080:80 --name portfolio-app mi-portfolio:v1
```

### ¿Qué hace este comando?

| Parte | Descripción |
|---|---|
| `docker run` | Crea y ejecuta un nuevo contenedor |
| `-d` | Modo detached (corre en segundo plano) |
| `-p 8080:80` | Mapea el puerto 8080 de tu PC al puerto 80 del contenedor |
| `--name portfolio-app` | Nombre amigable para identificar el contenedor |
| `mi-portfolio:v1` | Imagen que se utiliza |

### Verificar que el contenedor está activo

```bash
docker ps
```

```
CONTAINER ID   IMAGE              STATUS         PORTS                  NAMES
a3f9c12b7e1d   mi-portfolio:v1   Up 2 minutes   0.0.0.0:8080->80/tcp   portfolio-app
```

### 🌐 Acceder a la aplicación

Abrí tu navegador y entrá a:

```
http://localhost:8080
```

Si ves el portfolio funcionando correctamente, ¡la dockerización fue exitosa! ✅

---

## 🖼️ Capturas de Pantalla

### Sección de inicio
> Título animado con efecto typewriter, avatar con borde giratorio y estadísticas.

![Inicio](https://github.com/Augus021/Web_Portafolio_Personal/blob/70f533779b8dd10647582ee9e19585001aed0404/screen-1.png)



### Habilidades
> Cards con barras de progreso animadas al hacer scroll.

![Habilidades](https://github.com/Augus021/Web_Portafolio_Personal/blob/70f533779b8dd10647582ee9e19585001aed0404/screen-2.png)

### Proyectos
> Cards con hover effects mostrando tecnologías y links a demo/GitHub.

![Proyectos](https://github.com/Augus021/Web_Portafolio_Personal/blob/70f533779b8dd10647582ee9e19585001aed0404/screen-3.png)


---

## 🔧 Comandos Docker Útiles

```bash
# Ver contenedores activos
docker ps

# Detener el contenedor
docker stop portfolio-app

# Volver a iniciarlo
docker start portfolio-app

# Ver los logs del servidor
docker logs portfolio-app

# Entrar dentro del contenedor
docker exec -it portfolio-app sh

# Eliminar el contenedor
docker stop portfolio-app
docker rm portfolio-app

# Eliminar la imagen
docker rmi mi-portfolio:v1

# Reconstruir tras cambios en los archivos
docker stop portfolio-app
docker rm portfolio-app
docker build -t mi-portfolio:v1 .
docker run -d -p 8080:80 --name portfolio-app mi-portfolio:v1
```

---

## 📄 Dockerfile

```dockerfile
# Imagen base: Nginx sobre Alpine Linux (liviana y segura)
FROM nginx:alpine

# Metadato del mantenedor
LABEL maintainer="Alex Dev <alex@email.com>"

# Copiar archivos estáticos al directorio raíz de Nginx
COPY index.html  /usr/share/nginx/html/index.html
COPY styles.css  /usr/share/nginx/html/styles.css
COPY script.js   /usr/share/nginx/html/script.js

# Exponer el puerto HTTP estándar
EXPOSE 80

# Iniciar Nginx en primer plano
CMD ["nginx", "-g", "daemon off;"]
```

---

## 🧠 ¿Por qué Nginx + Alpine?

- **Nginx** es uno de los servidores web más usados del mundo, ideal para servir archivos estáticos con alto rendimiento.
- **Alpine Linux** es una distribución minimalista de solo ~5MB, lo que resulta en imágenes Docker muy pequeñas y seguras.
- La imagen final `nginx:alpine` pesa aproximadamente **43MB**, perfecta para despliegues rápidos.

---

## 👤 Autor

**Augusto Levanti**
- GitHub: [@Augus021](https://github.com/Augus021)
- LinkedIn: [linkedin.com/in/augusto-levanti](https://linkedin.com/in/augusto-levanti)
- Email: augusto.levanti@istea.com.ar
- Portfolio: [localhost:8080](http://localhost:8080)
