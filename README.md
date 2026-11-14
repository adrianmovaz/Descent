
# Descent
 
**Simulación educativa que visualiza en 3D las aproximaciones a una pista**
 
[English](README.en.md) · **Español** · [日本語](README.ja.md)
 
![Unity](https://img.shields.io/badge/Unity-LTS-000000?logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?logo=csharp&logoColor=white)
![Platform](https://img.shields.io/badge/Windows-10%2B-0078D6?logo=windows&logoColor=white)
 
</div>
---
 
## Descripción
 
Descent es una simulación 3D en Unity para comparar aproximaciones correctas e incorrectas desde el mismo punto de vista.
Muestra en tiempo real cómo desviaciones pequeñas, de 1 a 2°, cambian lo que ve el piloto, la clasificación de la aproximación y las luces PAPI.
 
Proyecto de la materia Graficación por Computadora en ESCOM-IPN.
 
## Características
 
- **5 escenarios** — correcta, alta, baja, desviación izquierda y derecha
- **Clasificación en dos ejes** — vertical (en senda / alta / baja) y lateral (centrada / izquierda / derecha), evaluados por separado
- **Luces PAPI** — 4 luces que cambian entre blanco y rojo según la posición de la aeronave
- **5 cámaras** — cabina, persecución, perfil lateral, planta y libre
- **Modo comparación** — dos trayectorias sincronizadas lado a lado
- **Controles de reproducción** — velocidad de 0.5× a 4×, pausa y reinicio
- **Accesibilidad** — cada estado se muestra con icono y texto, no solo con color
## Stack
 
| Uso | Tecnología |
|---|---|
| Motor | Unity [versión LTS] · URP |
| Lenguaje | C# |
| Matemática del núcleo | System.Numerics |
| Cámaras | Cinemachine |
| Interfaz | uGUI + TextMeshPro |
| Modelado | Blender |
| Pruebas | Unity Test Framework (NUnit) |
| Diagramas | PlantUML |
| Versiones | Git + Git LFS |
 
## Cómo empezar
 
### Requisitos
 
- Unity [versión LTS]
- Git LFS
- Windows 10 o superior (WebGL opcional)
### Instalación
 
```bash
git lfs install
git clone [URL del repositorio]
```
 
1. Abre la carpeta del proyecto en Unity Hub
2. Abre `Assets/_Project/Scenes/Boot`
3. Presiona ▶ para ejecutar
## Controles
 
| Tecla | Acción |
|:---:|---|
| `Espacio` | Reproducir / pausar |
| `R` | Reiniciar |
| `+` / `−` | Cambiar velocidad |
| `1` – `5` | Cambiar de cámara |
| `T` | Mostrar u ocultar senda y traza |
| `I` | Mostrar u ocultar panel educativo |
| `H` | Ayuda |
| `Esc` | Volver al menú |
 
## Arquitectura
 
```
Datos → Simulación → Orquestación → Presentación / Interfaz
```
 
El núcleo de simulación está escrito en **C# puro, sin depender de UnityEngine**,
así que el modelo matemático se prueba sin abrir una escena.
 
```
Assets/_Project/
├── Scenes/                 Boot, MainMenu, Simulation
├── Scripts/
│   ├── Core/               Trayectorias, desviaciones y clasificación (C# puro)
│   ├── Data/               ScenarioData
│   ├── Orchestration/      SimulationManager, ComparisonManager
│   ├── Presentation/       Aeronave, trazas, PAPI y cámaras
│   └── UI/                 HUD, menús y panel educativo
├── ScriptableObjects/
│   └── Scenarios/          Escenarios (se agregan sin cambiar código)
└── Tests/EditMode/
```
 
## Pruebas
 
Unity → **Window › General › Test Runner › EditMode › Run All**
 
Comparan alturas de la senda, desviaciones angulares y lecturas PAPI contra valores calculados a mano.
 
## Documentación
 
El documento técnico (requerimientos, arquitectura 4+1, modelo matemático y diseño de interfaz) está en [`docs/`](docs/), en español, inglés y japonés.
 
## Aviso
 
Proyecto educativo. No sustituye entrenamiento de vuelo ni usa datos aeronáuticos certificados.
 
## Autor
