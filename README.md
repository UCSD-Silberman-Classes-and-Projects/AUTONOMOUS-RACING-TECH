# <div align="center">Autonomous Racing Tech</div>
### <div align="center">[Lab / Organization Name]</div>
#### <div align="center">UC San Diego [Department / Institute Name]</div>

Master repository for the UC San Diego Autonomous Racing Tech project group.

This repository is intentionally organized as a submodule-based workspace. The top-level repository provides the project overview, integration map, and contributor workflow, while the implementation, documentation, firmware, and setup assets remain in their dedicated component repositories.

## Abstract

[Describe the platform: what it is, what it is used for, and the major subsystems it combines (compute, actuation, sensing, perception, planning, control).]

[Describe the design philosophy: modularity, reproducibility, and how the master workspace helps future contributors understand and reproduce the full stack.]

- **Team Members List**: [`Current + Alumni`](./CONTRIBUTORS.md)
- **Faculty Sponsors**: [Faculty Sponsor Name]

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
├── software/
│   ├── README.md
│   ├── [software-repo-1]/
│   ├── [software-repo-2]/
│   └── [planned-repo]/            # planned
└── hardware/
    ├── README.md
    ├── [hardware-repo-1]/
    └── [hardware-repo-2]/
```

## Submodules

GitHub displays each committed submodule path as a folder-like link to the exact submodule commit. The folder indexes in [`software/`](./software) and [`hardware/`](./hardware) also provide direct links to each upstream repository.

| Submodule | Purpose | Upstream |
| --- | --- | --- |
| [`software/[software-repo-1]`](./software/[software-repo-1]) | [Purpose] | `[add repository link]` |
| [`software/[software-repo-2]`](./software/[software-repo-2]) | [Purpose] | `[add repository link]` |
| [`hardware/[hardware-repo-1]`](./hardware/[hardware-repo-1]) | [Purpose] | `[add repository link]` |
| [`hardware/[hardware-repo-2]`](./hardware/[hardware-repo-2]) | [Purpose] | `[add repository link]` |

## Planned Submodules

| Path | Intended purpose | Status |
| --- | --- | --- |
| `software/[planned-repo]/` | [Intended purpose] | Planned |

## System Overview

Autonomous Racing Tech brings together four major development areas:

1. Vehicle platform and hardware integration
   - [Chassis / base platform]
   - [Motor controllers / drivetrain]
   - [Steering and drive actuation]
   - [Electrical mounting, wiring, and safety architecture]

2. Embedded and remote-control interfaces
   - [Radio / teleoperation controller]
   - [Receiver / microcontroller integration]
   - [Manual-control test workflows]

3. Onboard compute and software stack
   - [Onboard compute platform]
   - [Runtime environment / middleware]
   - [Setup and hardware test scripts]
   - [Autonomous-control integration points]

4. Perception, planning, and autonomy
   - [Camera integration]
   - [LiDAR / additional sensors]
   - [Localization and mapping]
   - [Path planning and closed-loop racing control]

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
git submodule add <repo-url> software/<component-repo>
# or
git submodule add <repo-url> hardware/<component-repo>
```

## Recommended Reading Order

1. Start with [`hardware/[hardware-repo-1]/README.md`](./hardware/[hardware-repo-1]/README.md) for [high-level background, hardware revisions, and system architecture].
2. Review [`hardware/[hardware-repo-2]/README.md`](./hardware/[hardware-repo-2]/README.md) for [setup guide details].
3. Use [`software/[software-repo-1]/README.md`](./software/[software-repo-1]/README.md) when [use case].
4. Use [`software/[software-repo-2]/README.md`](./software/[software-repo-2]/README.md) when [use case].

## Development Workflow

Because this is a submodule workspace, most code and documentation changes should be made inside the relevant submodule repository.

Typical workflow:

```bash
cd software/<component-repo>
# or
cd hardware/<component-repo>
git checkout <branch-name>
# make changes
git add .
git commit -m "Describe component change"
git push

cd ../..
git add software/<component-repo>
# or
git add hardware/<component-repo>
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

- Firmware changes
- Setup scripts
- Hardware documentation
- CAD and media assets
- Detailed subsystem documentation

## Safety Notes

[Platform name] includes moving mechanical systems, high-current motor controllers, batteries, and software-controlled actuation. Before running any control script or firmware against the physical vehicle:

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
