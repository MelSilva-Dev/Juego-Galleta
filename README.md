# Juego Galleta

Juego Galleta es un proyecto de juego de estrategia por turnos inspirado en **Dots and Boxes**. El jugador completa los lados de las celdas sobre un tablero; al cerrar una celda, suma un punto y conserva el turno. El paquete incluye una implementación del juego en C# y una interfaz web con Blazor.

## Características

- Representación del tablero, sus celdas, aristas y movimientos.
- Reglas de juego y estado encapsulados en una capa de dominio.
- Interfaz web interactiva construida con Blazor.
- Oponente de inteligencia artificial con búsqueda **Minimax y poda alfa-beta**.
- Evaluador de posiciones basado en el puntaje de las celdas.

## Tecnologías

- C# y .NET (el código fuente incluye proyectos dirigidos a .NET 8 y .NET 9).
- ASP.NET Core y Blazor para la aplicación web.
- Bootstrap y CSS para estilos de interfaz.

> Para ejecutar la aplicación web, instala el SDK de **.NET 9**. El proyecto de lógica de juego también tiene como destino .NET 8.

## Estructura del proyecto

```text
Juego_Galleta/
├── Juego_Galleta.sln
├── Juego_Galleta/                 # Dominio, lógica y componentes del juego
│   ├── Application/AI/            # Búsqueda y evaluación de la IA
│   ├── Domain/Entities/            # Tablero, celdas, aristas y movimientos
│   └── Presentation/              # Controlador y representación del tablero
├── Juego_Galleta.Web/             # Aplicación web Blazor
│   ├── Components/Pages/Game.razor # Página del juego
│   └── wwwroot/                   # Estilos y recursos estáticos
└── DOCUMENTACION_TECNICA.md       # Documentación técnica incluida en el paquete
```

## Requisitos

- Windows, macOS o Linux.
- SDK de .NET 9 instalado y disponible en `PATH`.
- WinRAR o una herramienta compatible para extraer el archivo del proyecto.

## Inicio rápido

1. Extrae `Juego_Galleta.rar`.
2. Abre una terminal en la carpeta extraída, en el nivel donde se encuentra `Juego_Galleta.sln`.
3. Restaura dependencias y ejecuta la aplicación web:

```bash
dotnet restore Juego_Galleta.sln
dotnet run --project Juego_Galleta.Web/Juego_Galleta.Web.csproj
```

4. Abre en el navegador la URL local que indique la terminal (por ejemplo, `https://localhost:xxxx` o `http://localhost:xxxx`).

También puedes abrir `Juego_Galleta.sln` con Visual Studio, seleccionar `Juego_Galleta.Web` como proyecto de inicio y ejecutar con **F5**.

## Cómo se juega

1. Selecciona un lado disponible entre dos puntos del tablero.
2. Cada lado completado permanece marcado.
3. Al cerrar los cuatro lados de una celda, obtienes un punto y juegas otra vez.
4. Si no cierras una celda, el turno pasa al oponente.
5. Gana quien haya cerrado más celdas cuando ya no queden movimientos.

## Arquitectura

El proyecto separa las reglas y los datos del juego de su presentación:

- **Domain:** entidades como `Board`, `Cell`, `Edge`, `Move` y `GameState`, además de interfaces para formas de tablero y evaluación.
- **Application:** lógica de decisión de la IA, con búsqueda Minimax y poda alfa-beta.
- **Presentation:** coordinación del juego y representación del tablero.
- **Web:** interfaz Blazor que presenta el juego en el navegador.

## Compilación

Desde la carpeta que contiene la solución:

```bash
dotnet build Juego_Galleta.sln
```

## Notas sobre el paquete

El repositorio contiene el archivo comprimido `Juego_Galleta.rar`. La estructura anterior describe el contenido identificado dentro del archivo. El ZIP mencionado en la solicitud no aparece en la carpeta actual. Al extraer el RAR, consulta `DOCUMENTACION_TECNICA.md` para los detalles adicionales del diseño.

## Licencia

No se identificó un archivo de licencia en el paquete. Añade una licencia antes de redistribuir el proyecto si corresponde.
