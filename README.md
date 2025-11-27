# BreakMate

BreakMate es una aplicación de escritorio que ayuda a las personas que pasan largas horas frente a la computadora a mantener hábitos saludables. Su propósito principal es recordar al usuario beber agua, levantarse, estirarse y realizar pausas activas para evitar fatiga muscular, deshidratación y problemas posturales. La aplicación utiliza Electron + React para la interfaz y un backend ligero basado en Flask para manejar persistencia y estadísticas a nivel local.

------------------------------------------------------------

## Flujo general de BreakMate

El siguiente diagrama muestra cómo interactúan los componentes principales y cómo fluye la información desde el usuario hasta el almacenamiento local.

```mermaid
flowchart LR
    subgraph User
        U[Interacción del Usuario]
    end

    subgraph Electron
        A[Electron Shell]
        C[React Frontend]
    end

    subgraph Backend
        B[Flask API]
        D[(SQLite Database)]
    end

    U --> C
    C --> A
    C -- Solicitudes HTTP --> B
    B --> D
    A -- Notificaciones del Sistema --> U

    C <-. Datos y Estado .-> B
