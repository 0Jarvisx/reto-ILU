# reto-ILU
Full-stack app con React + Node.js API + PostgreSQL, orquestada con Docker Compose.

## Requisitos
- [Docker](https://www.docker.com/) con Docker Compose
- [Git](https://git-scm.com/)

## Primeros pasos

1. Clona el repositorio con sus submódulos:
   ```bash
   git clone --recurse-submodules https://github.com/0Jarvisx/reto-ILU.git
   cd reto-ILU
   ```

   > Si ya clonaste el repositorio sin submódulos, ejecuta:
   > ```bash
   > git submodule update --init --recursive
   > ```

2. Crea el archivo `.env` (ver sección [Configuración](#configuración)).

3. Inicia los servicios:
   ```bash
   docker compose up -d
   ```

La app estará disponible en `http://localhost:8080`

## Configuración

Crea un archivo `.env` en la raíz del proyecto:

```env
POSTGRES_USER=ilu
POSTGRES_PASSWORD=ilu
POSTGRES_DB=ilu_db
CLIENT_ORIGIN=http://localhost:8080
```

## Servicios

| Servicio     | Descripción                  |
|--------------|------------------------------|
| `nginx`      | Proxy inverso (puerto 8080)  |
| `react-app`  | Frontend React               |
| `api-server` | API REST (Node.js)           |
| `db`         | PostgreSQL 16                |

## Comandos útiles

```bash
# Ver logs
docker compose logs -f

# Detener
docker compose down

# Detener y eliminar volúmenes (borra la BD)
docker compose down -v

# Actualizar submódulos a su último commit
git submodule update --remote --recursive
```
