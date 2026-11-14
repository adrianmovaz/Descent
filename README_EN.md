# Descent
 
Educational 3D simulation in Unity that shows and compares runway approaches: correct, high, low and laterally offset. Each trajectory is classified in real time and reflected in the PAPI lights.
 
Computer Graphics course project — ESCOM-IPN.
 
## Stack
 
| Layer | Technology |
|---|---|
| Engine | Unity [LTS version] · URP |
| Language | C# |
| Core math | System.Numerics |
| Cameras | Cinemachine |
| UI | uGUI + TextMeshPro |
| Modeling | Blender |
| Testing | Unity Test Framework (NUnit) |
| Diagrams | PlantUML |
| Version control | Git + Git LFS |
 
## Requirements
 
- Unity [LTS version]
- Git LFS
- Windows 10+ (WebGL optional)
## Run
 
```bash
git lfs install
git clone [repository URL]
```
 
Open the folder in Unity Hub and load the `Assets/_Project/Scenes/Boot` scene.
 
## Controls
 
| Action | Key |
|---|---|
| Play / pause | `Space` |
| Restart | `R` |
| Speed (0.5× – 4×) | `+` / `−` |
| Camera (cockpit, chase, profile, top-down, free) | `1` – `5` |
| Path and track | `T` |
| Educational panel | `I` |
| Help | `H` |
| Menu | `Esc` |
 
## Structure
 
```
Assets/_Project/
  Scenes/              Boot, MainMenu, Simulation
  Scripts/
    Core/              Simulation and classification (pure C#, no UnityEngine)
    Data/              ScenarioData
    Orchestration/     SimulationManager, ComparisonManager
    Presentation/      Aircraft, trajectories, PAPI, cameras
    UI/                HUD, menu, educational panel
  ScriptableObjects/Scenarios/
  Tests/EditMode/
```
 
The core does not depend on Unity, so the math model is tested without opening a scene.
 
## Tests
 
Unity → **Window › General › Test Runner › EditMode › Run All**.
 
## Documentation
 
The full technical design (requirements, 4+1 architecture, math model and interface) is in `docs/`.
 
## Disclaimer
 
Educational project. It does not replace flight training and does not use certified aeronautical data.
