# <div align="center">Autonomous Racing Tech: Perception, Localization, Navigation</div>
### <div align="center">Dr. Jack Silberman's Lab Group</div>
#### <div align="center">UC San Diego, UC Berkeley, AI Racing Tech</div>

Master repository for the UC San Diego Autonomous Racing Tech project group.

This repository is intentionally organized as a submodule-based workspace. The top-level repository provides the project overview, integration map, and contributor workflow, while the implementation, documentation, firmware, and setup assets remain in their dedicated component repositories.

## Abstract

[Describe the platform: what it is, what it is used for, and the major subsystems it combines (compute, actuation, sensing, perception, planning, control).]

[Describe the design philosophy: modularity, reproducibility, and how the master workspace helps future contributors understand and reproduce the full stack.]

- **Team Members List**: [`Current + Alumni`](./CONTRIBUTORS.md)
- **Faculty Sponsors**: Dr. Jack Silberman

## Blue RoboCar ROS 2 Container

The [`BLUE-ROBOCAR-ROS2/`](./BLUE-ROBOCAR-ROS2) submodule is the ROS 2 container for the **Blue RoboCar**, the platform the team uses for its high-level software projects. Upstream: <https://github.com/UCSD-Silberman-Classes-and-Projects/BLUE-ROBOCAR-ROS2>

It provides the hardware layer, which includes the ROS 2 Jazzy drivers, bringup, and teleop for the Jetson Orin Nano, Livox Mid-360 LiDAR, OAK-D Pro camera, and VESC. The work in `sensor_fusion_ml/`, `localization_mapping/`, and `optimization_acceleration/` builds the higher-level autonomy on top of it. See [`BLUE-ROBOCAR-ROS2/README.md`](./BLUE-ROBOCAR-ROS2/README.md) for Docker and native setup instructions.

## Project Goals

- [Goal 1]
- [Goal 2]
- [Goal 3]
- [Goal 4]
- [Goal 5]

## Repository Structure

```text
AUTONOMOUS-RACING-TECH/
├── .gitmodules
├── README.md
├── CONTRIBUTORS.md
├── BLUE-ROBOCAR-ROS2/             # Blue RoboCar ROS 2 container
├── sensor_fusion_ml/
│   ├── README.md
│   ├── [sensor-fusion-repo-1]/
│   └── [sensor-fusion-repo-2]/
├── localization_mapping/
│   ├── README.md
│   ├── [localization-repo-1]/
│   └── [localization-repo-2]/
└── optimization_acceleration/
    ├── README.md
    ├── [optimization-repo-1]/
    └── [optimization-repo-2]/
```

## Submodules

GitHub displays each committed submodule path as a folder-like link to the exact submodule commit. The folder indexes in [`sensor_fusion_ml/`](./sensor_fusion_ml), [`localization_mapping/`](./localization_mapping), and [`optimization_acceleration/`](./optimization_acceleration) also provide direct links to each upstream repository.

| Submodule | Purpose | Upstream |
| --- | --- | --- |
| [`BLUE-ROBOCAR-ROS2`](./BLUE-ROBOCAR-ROS2) | ROS 2 container for the Blue RoboCar platform used for high-level software projects. | <https://github.com/UCSD-Silberman-Classes-and-Projects/BLUE-ROBOCAR-ROS2.git> |
| [`sensor_fusion_ml/[sensor-fusion-repo-1]`](./sensor_fusion_ml/[sensor-fusion-repo-1]) | [Purpose] | `[add repository link]` |
| [`sensor_fusion_ml/[sensor-fusion-repo-2]`](./sensor_fusion_ml/[sensor-fusion-repo-2]) | [Purpose] | `[add repository link]` |
| [`localization_mapping/[localization-repo-1]`](./localization_mapping/[localization-repo-1]) | [Purpose] | `[add repository link]` |
| [`localization_mapping/[localization-repo-2]`](./localization_mapping/[localization-repo-2]) | [Purpose] | `[add repository link]` |
| [`optimization_acceleration/[optimization-repo-1]`](./optimization_acceleration/[optimization-repo-1]) | [Purpose] | `[add repository link]` |
| [`optimization_acceleration/[optimization-repo-2]`](./optimization_acceleration/[optimization-repo-2]) | [Purpose] | `[add repository link]` |

## Planned Submodules

| Path | Intended purpose | Status |
| --- | --- | --- |
| `[area]/[planned-repo]/` | [Intended purpose] | Planned |

## System Overview

Autonomous Racing Tech brings together three major development areas:

1. Sensor fusion and machine learning (`sensor_fusion_ml/`)
   - [Camera / LiDAR / radar / IMU integration]
   - [Sensor calibration and time synchronization]
   - [Multi-sensor fusion]
   - [ML-based perception and object detection]

2. Localization and mapping (`localization_mapping/`)
   - [GPS / GNSS / RTK positioning]
   - [State estimation and odometry]
   - [Track mapping and map representation]
   - [SLAM / map-based localization]

3. Optimization and acceleration (`optimization_acceleration/`)
   - [Raceline and trajectory optimization]
   - [Real-time performance profiling]
   - [GPU / hardware acceleration of perception and planning]
   - [Latency reduction across the stack]

## Quick Start

Clone the master repository with all submodules:

```bash
git clone --recurse-submodules <master-repo-url>
cd AUTONOMOUS-RACING-TECH
```

If the repository was cloned without submodules:

```bash
git submodule update --init --recursive
```

To pull updates from the master repository and refresh submodules:

```bash
git pull
git submodule update --init --recursive
```

To update each submodule to its latest upstream branch:

```bash
git submodule update --remote --merge
```

To add a new submodule:

```bash
git submodule add <repo-url> <area>/<component-repo>
# <area> is one of: sensor_fusion_ml, localization_mapping, optimization_acceleration
```

## Recommended Reading Order

1. Start with [`BLUE-ROBOCAR-ROS2/README.md`](./BLUE-ROBOCAR-ROS2/README.md) to set up the Blue RoboCar ROS 2 container and bring up the hardware.
2. Review [`sensor_fusion_ml/README.md`](./sensor_fusion_ml/README.md) for [sensor suite, fusion pipeline, and perception models].
3. Review [`localization_mapping/README.md`](./localization_mapping/README.md) for [localization, state estimation, and mapping].
4. Use [`optimization_acceleration/README.md`](./optimization_acceleration/README.md) when [optimizing trajectories or accelerating the stack].
5. [Add component-specific READMEs as submodules are added.]

## Development Workflow

Because this is a submodule workspace, most code and documentation changes should be made inside the relevant submodule repository.

Typical workflow:

```bash
cd <area>/<component-repo>
git checkout <branch-name>
# make changes
git add .
git commit -m "Describe component change"
git push

cd ../..
git add <area>/<component-repo>
git commit -m "Update <component-repo> submodule pointer"
git push
```

Use the top-level repository for:

- Project overview and abstract
- Submodule coordination
- Integration notes
- Release snapshots
- Cross-subsystem documentation

Use individual submodules for:

- Algorithm and model implementation
- Datasets, training, and evaluation scripts
- Setup and launch scripts
- Benchmarks and profiling results
- Detailed subsystem documentation

## Safety Notes

The Blue RoboCar includes moving mechanical systems, high-current motor controllers, batteries, and software-controlled actuation. Before running any control script or firmware against the physical vehicle:

- Verify the vehicle is lifted, restrained, or in a safe test area.
- Confirm motor controller current limits and control settings.
- Confirm emergency-stop / deadman behavior before applying drive power.
- Keep a physical power disconnect available.
- Test steering and drive separately before combined operation.
- Use conservative speed and steering limits during early tests.
- [Add any track- or venue-specific safety requirements]

## Acknowledgments

[Describe the coursework, programs, sponsors, and student work that contributed to the project.]

[Special thanks.]

## Contacts

* [Name] - [email]
* [Name] - [email]
