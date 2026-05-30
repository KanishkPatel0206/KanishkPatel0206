# Point Cloud Data Visualisation & Path

A collection of Python scripts for loading and visualising 3D point cloud data (`.ply` files) using multiple libraries — Open3D, PyVista, and PyntCloud. The sample dataset used is a **Patchwork Chair** PLY file from the IITH LiDAR ground dataset.

---

## 📁 Project Structure

```
point_cloud_data_visualise_and_path/
│
├── open3d_visualise.py        # Visualise point cloud using Open3D
├── open3d_voxelization.py     # Voxel grid downsampling and visualisation using Open3D
├── pyvista_visualise.py       # Visualise point cloud using PyVista
├── pyntcloud_visualise.py     # Load with PyntCloud, render with PyVista
│
├── patchwork_chair_ply_0/
│   ├── Patchwork chair.ply    # Sample 3D point cloud file
│   ├── Patchwork chair_0.jpg  # Reference image of the chair
│   └── license.txt
│
└── README.md
```

---

## 🛠️ Scripts Overview

### 1. `open3d_visualise.py`
Loads a `.ply` point cloud file and renders it in an interactive Open3D window.

- Reads the point cloud using `open3d.io.read_point_cloud()`
- Validates that points were loaded successfully
- Opens an 800×600 interactive viewer window

### 2. `open3d_voxelization.py`
Demonstrates **voxel grid downsampling** — converting a dense point cloud into a structured grid of cubes.

- Downsamples the cloud with a configurable `voxel_size` (default: `0.5`)
- Creates a `VoxelGrid` object from the downsampled cloud
- Prints voxel count info and renders the voxel grid interactively

> 💡 Change `voxel_size` to control the resolution. Smaller = more detail, larger = fewer cubes.

### 3. `pyvista_visualise.py`
Reads and visualises the point cloud directly using **PyVista**.

- Loads the `.ply` file via `pv.read()`
- Renders points as spheres with configurable `point_size`
- Opens an 800×600 interactive plotter window

### 4. `pyntcloud_visualise.py`
Loads the point cloud using **PyntCloud**, extracts XYZ coordinates as a NumPy array, then renders using **PyVista**.

- Uses PyntCloud for loading and pandas-based point access
- Converts to a `pv.PolyData` object for rendering
- Renders points as spheres in a PyVista plotter

---

## ⚙️ Setup

### Prerequisites
- Python 3.8+
- Windows (file paths use raw Windows strings)

### 1. Clone the repository
```bash
git clone https://github.com/KanishkPatel0206/point_cloud_data_visualise_and_path.git
cd point_cloud_data_visualise_and_path
```

### 2. Create a virtual environment
```bash
python -m venv .venv
.venv\Scripts\Activate.ps1      # PowerShell
# or
.venv\Scripts\activate.bat      # Command Prompt
```

### 3. Install dependencies
```bash
pip install open3d pyvista pyntcloud
```

---

## ▶️ Usage

Update the `file_path` variable in each script to point to your local `.ply` file, then run:

```bash
python open3d_visualise.py
python open3d_voxelization.py
python pyvista_visualise.py
python pyntcloud_visualise.py
```

---

## 📦 Dependencies

| Library      | Purpose                                      |
|--------------|----------------------------------------------|
| `open3d`     | Point cloud I/O, visualisation, voxelization |
| `pyvista`    | 3D mesh and point cloud rendering            |
| `pyntcloud`  | Point cloud loading with pandas integration  |
| `numpy`      | Array operations (used by pyntcloud script)  |

---

## 📄 Dataset

The sample dataset is a **Patchwork Chair** 3D scan in PLY format, sourced from the IITH LiDAR ground dataset. The dataset is included under its original license — see `patchwork_chair_ply_0/license.txt`.

---

## 🙋 Author

**Kanishk Patel** — [GitHub](https://github.com/KanishkPatel0206)
