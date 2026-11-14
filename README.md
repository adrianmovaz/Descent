# Descent
 
Simulación 3D educativa en Unity que muestra y compara aproximaciones a una pista: correcta, alta, baja y con desviación lateral. Cada trayectoria se clasifica en tiempo real y se refleja en las luces PAPI.
 
Proyecto de Graficación por Computadora — ESCOM-IPN.
 
## Stack
 
| Capa | Tecnología |
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
 
## Requisitos
 
- Unity [versión LTS]
- Git LFS
- Windows 10+ (WebGL opcional)
## Ejecutar
 
```bash
git lfs install
git clone [URL del repositorio]
```
 
Abre la carpeta en Unity Hub y carga la escena `Assets/_Project/Scenes/Boot`.
 
## Controles
 
| Acción | Tecla |
|---|---|
| Reproducir / pausar | `Espacio` |
| Reiniciar | `R` |
| Velocidad (0.5× – 4×) | `+` / `−` |
| Cámara (cabina, persecución, perfil, planta, libre) | `1` – `5` |
| Senda y traza | `T` |
| Panel educativo | `I` |
| Ayuda | `H` |
| Menú | `Esc` |
 
## Estructura
 
```
Assets/_Project/
  Scenes/              Boot, MainMenu, Simulation
  Scripts/
    Core/              Simulación y clasificación (C# puro, sin UnityEngine)
    Data/              ScenarioData
    Orchestration/     SimulationManager, ComparisonManager
    Presentation/      Aeronave, trayectorias, PAPI, cámaras
    UI/                HUD, menú, panel educativo
  ScriptableObjects/Scenarios/
  Tests/EditMode/
```
 
El núcleo no depende de Unity, así que el modelo matemático se prueba sin abrir una escena.
 
## Pruebas
 
Unity → **Window › General › Test Runner › EditMode › Run All**.
 
## Documentación
 
El diseño técnico completo (requerimientos, arquitectura 4+1, modelo matemático e interfaz) está en `docs/`.
 
## Aviso
 
Proyecto educativo. No sustituye entrenamiento de vuelo ni usa datos aeronáuticos certificados.
