# Tailspin Space Game — ASP.NET Core y Azure Pipelines

Repositorio de práctica basado en el proyecto **Tailspin Space Game** de Microsoft Learn, utilizado para trabajar conceptos de **ASP.NET Core**, **.NET 6** y **CI/CD con Azure Pipelines**.

El proyecto implementa una aplicación web que muestra clasificaciones de jugadores, perfiles y puntuaciones, y sirve como base para practicar compilación automatizada y procesos de integración continua en Azure DevOps.

> Este repositorio procede de material de Microsoft Learn. No es un proyecto original de Silverio Marín; se conserva como entorno de aprendizaje y práctica técnica.

## Tecnologías utilizadas

- **C#**
- **.NET 6**
- **ASP.NET Core MVC**
- **Razor Views**
- **Azure Pipelines**
- **Azure DevOps**
- **YAML**
- **JavaScript**
- **Bootstrap**
- **Gulp**
- **JSON**
- **Visual Studio / Visual Studio Code**

## Funcionalidades de la aplicación

La aplicación web incluye:

- Tabla de clasificación de jugadores.
- Filtrado por modo de juego.
- Filtrado por región.
- Paginación de resultados.
- Consulta de perfiles de usuario.
- Datos de ejemplo almacenados en archivos JSON.
- Arquitectura MVC con controladores, modelos y vistas.

## Estructura principal

```text
mslearn-tailspin-spacegame-web/
├── Tailspin.SpaceGame.Web/
│   ├── Controllers/
│   ├── Models/
│   ├── Views/
│   ├── SampleData/
│   ├── wwwroot/
│   ├── Program.cs
│   ├── Startup.cs
│   └── Tailspin.SpaceGame.Web.csproj
├── azure-pipelines.yml
├── gulpfile.js
├── package.json
└── Tailspin.SpaceGame.Web.sln
```

## Aplicación ASP.NET Core

El proyecto principal utiliza **ASP.NET Core MVC sobre .NET 6**.

`HomeController` se encarga de recuperar y filtrar las puntuaciones y perfiles utilizados en la clasificación.

Los datos de ejemplo se encuentran en:

```text
Tailspin.SpaceGame.Web/SampleData/
├── profiles.json
└── scores.json
```

La clase `LocalDocumentDBRepository<T>` proporciona una abstracción sencilla de repositorio para consultar esos datos de forma asíncrona.

## Azure Pipelines

El repositorio contiene el archivo:

```text
azure-pipelines.yml
```

que define un pipeline de integración continua.

La configuración incluida:

- Se activa sobre la rama `main`.
- Utiliza un agente `ubuntu-latest`.
- Compila el proyecto en configuración `Release`.
- Ejecuta la compilación mediante `dotnet build`.

Ejemplo de la tarea principal:

```yaml
steps:
- script: dotnet build --configuration $(buildConfiguration)
  displayName: 'dotnet build $(buildConfiguration)'
```

Este pipeline permite practicar los fundamentos de **CI/CD**, automatización de compilaciones y configuración de pipelines como código en Azure DevOps.

## Puesta en marcha local

### Requisitos

- **.NET 6 SDK**
- Node.js y npm si se van a utilizar las tareas de frontend.
- Visual Studio, Visual Studio Code o un IDE compatible con .NET.

### Clonar el repositorio

```bash
git clone https://github.com/smarinwm/mslearn-tailspin-spacegame-web.git
cd mslearn-tailspin-spacegame-web
```

### Restaurar dependencias .NET

```bash
dotnet restore
```

### Ejecutar la aplicación

```bash
dotnet run --project Tailspin.SpaceGame.Web
```

La consola mostrará la URL local en la que queda disponible la aplicación.

## Dependencias frontend

El proyecto también incluye herramientas de frontend gestionadas mediante npm y Gulp.

Para instalar las dependencias:

```bash
npm install
```

Entre las herramientas de desarrollo incluidas se encuentran:

- Gulp
- gulp-clean-css
- gulp-concat
- gulp-uglify
- node-sass

## Objetivo didáctico

Este repositorio resulta útil para practicar:

- Desarrollo con ASP.NET Core MVC.
- Organización de aplicaciones .NET.
- Inyección de dependencias.
- Patrón Repository.
- Operaciones asíncronas en C#.
- Lectura y consulta de datos JSON.
- Razor Views.
- Automatización con Azure Pipelines.
- Pipelines definidos mediante YAML.
- Integración continua.
- Fundamentos de Azure DevOps.

## Procedencia y licencias

El código y los contenidos originales forman parte del material de **Microsoft Learn / Microsoft**.

El repositorio incluye los archivos de licencia originales:

- `LICENSE`
- `LICENSE-CODE`

El contenido documental original se distribuye bajo **Creative Commons Attribution 4.0** y el código bajo **MIT License**, según los términos incluidos en el propio repositorio.

Microsoft, Azure y otros nombres de productos mencionados son marcas de sus respectivos propietarios.

## Sobre este repositorio

Esta copia se mantiene como material de **formación y práctica en ASP.NET Core, Azure DevOps y automatización CI/CD**.

No pretende atribuir la autoría del proyecto original, sino documentar el trabajo realizado sobre material formativo público de Microsoft.

## Perfil

**Silverio Marín** — Docente TIC en Valencia, con experiencia en programación, cloud y tecnologías Microsoft.

Más contenidos sobre **cloud computing, Azure y automatización**:

**[silveriomarin.com/cloud](https://silveriomarin.com/cloud/)**

GitHub: **[@smarinwm](https://github.com/smarinwm)**

---

Proyecto base: **Microsoft Learn — Tailspin Space Game**.
