# 🏙️ Modular Building Generator (UE5 C++)

A procedural tool for generating modular buildings in Unreal Engine 5.  
Built entirely in C++, this system is designed for fast iteration, high performance via Instanced Static Meshes, and flexible customization.

## 🔧 Key Features

- **Procedural Generation** of buildings based on width, depth, and height parameters
- Supports:
  - Variable **wall types** (large, small, windowed, with door)
  - **Balconies** (configurable, spawn only on upper floors)
  - **Trim Bands** between floors for extra visual detail
  - **Roofs and Roof Corners** with automatic placement
  - **Corners** and smart wall tiling
- **Randomization Support** with seeded values
- **Instanced Static Mesh System** for efficient runtime or editor usage
- **Conversion Button**: Convert all ISMs to individual StaticMeshActors for vertex painting or manual tweaking

## 🎮 Built With

- 💠 **Unreal Engine 5** (C++)
- 🧱 Modular mesh system
- 🎲 Deterministic random seed for repeatable layouts
- 🧠 Smart placement logic (windows, balconies, corners, doors)

## 🚀 Usage

Inside the editor:
- Drop the `AModularBuildingGenerator` actor into your level
- Set desired **Width, Depth, Height**, and options like `bEnableBalconies`
- Hit the ✅ `GenerateBuilding()` or 🎲 `RandomizeAndGenerate()` button
- Convert to StaticMeshActors (for light baking, vertex paint, etc.) with 🧱 `ConvertAllISMsToStaticMeshActors()`

## 📸 Showcase
![ezgif-1ad5d6011971b4](https://github.com/user-attachments/assets/53fa3eb9-22e2-4715-a350-22be1cd06dfb)
![ezgif-1b9e233991122c](https://github.com/user-attachments/assets/d0b61864-f713-46b1-b959-b4323835816d)
![ezgif-128761ab98fa43](https://github.com/user-attachments/assets/e3782c4f-6d23-478f-9203-75d707c8f688)



## 🧠 Technical Highlights

- **Instanced Mesh Management** via `GetOrCreateISM()` for runtime performance
- **Balcony Logic**: Only spawns under valid windows on upper floors
- **Custom Offsets & Rotations** for each element (e.g. door, band, roof piece)
- Easy to extend: Add new wall styles or roof types by updating the `LoadMeshes()` method
