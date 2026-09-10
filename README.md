# BYU-I Formula Hybrid VCM Design

This Repository holds all appropriate pcb files for the BYU-I Formula Hybrid teams Vehicle Control Module pcb board design.

The Microcontroller being built around is the STM32-F767ZI




## KiCad Project Template

PCB projects in this repository should be created using the BYU-I Formula Hybrid KiCad project template. The template provides the standard schematic drawing sheet and documentation fields used by the team.

### Initial KiCad Template Setup

The following setup only needs to be completed once on each computer.

1. Clone this repository to your computer using Git or GitHub Desktop.

2. Open the KiCad Project Manager.

3. Go to **Preferences → Configure Paths**.

4. Find `KICAD_USER_TEMPLATE_DIR`. If it does not exist, add it.

5. Set `KICAD_USER_TEMPLATE_DIR` to the `templates` directory in your local copy of this repository. For example:

   ```text
   C:\Users\<username>\Documents\GitHub\VCM-Design\templates
   ```

   Point KiCad to the `templates` directory, **not** directly to the `FHR_PCB_Template` directory.

6. Click **OK** to save the path.

The Formula Hybrid template should now be available when creating a new KiCad project.

### Creating a New PCB Project

1. Open the KiCad Project Manager.

2. Select **File → New Project...**

3. Select the Formula Hybrid PCB template from the **User Templates** section.

4. Choose the appropriate location in this repository and give the project a descriptive name.

5. Open the new project's Schematic Editor.

6. Go to **File → Schematic Setup → Project → Text Variables** and update the following fields:

   | Variable | Description | Example |
   | --- | --- | --- |
   | `DESIGNER` | Person responsible for the design | `Jane Smith` |
   | `CHECKED_BY` | Person who independently reviewed the design | `NOT CHECKED` |
   | `DOCUMENT_NUMBER` | Team document identifier | `FHR-EL-001-SCH` |
   | `STATUS` | Current document status | `DRAFT` |
   | `VEHICLE` | Vehicle associated with the design | `2027 Formula Hybrid` |

7. Open **File → Page Settings** and update:

   | Field | Usage |
   | --- | --- |
   | **Title** | Descriptive name of the PCB/schematic |
   | **Company** | `BYU-I Formula Hybrid Racing` |
   | **Revision** | Hardware/document revision |
   | **Issue Date** | Date the current revision was issued |

### Document Status and Revision

Use the following document statuses:

- `DRAFT` — design is actively being developed.
- `REVIEW` — design is ready for independent review.
- `RELEASED` — design has been reviewed and released.
- `OBSOLETE` — design is no longer intended for use.

During initial development, use:

```text
STATUS: DRAFT
REVISION: -
CHECKED_BY: NOT CHECKED
```

When a design is formally released, assign a revision and issue date. For example:

```text
STATUS: RELEASED
REVISION: A
ISSUE DATE: 2026-09-09
```

Use `YYYY-MM-DD` for issue dates.

`CHECKED_BY` should identify an independent reviewer. Leave it as `NOT CHECKED` until another team member has reviewed the design.

### Template Files

The master KiCad resources are stored under:

```text
templates/
├── FHR_Drawing_Sheet.kicad_wks
└── FHR_PCB_Template/
    ├── FHR_PCB_Template.kicad_pro
    ├── FHR_PCB_Template.kicad_sch
    ├── FHR_PCB_Template.kicad_pcb
    └── meta/
        └── info.html
```

Do not use the files inside `FHR_PCB_Template` as an active PCB project. Create a new project from the template instead.

Changes to the master template should be intentional, as they affect the starting configuration of future PCB projects.


## STM32 pins to be exposed by the pcb
```
PD0      ------> CAN1_RX
PD1      ------> CAN1_TX
PB12     ------> CAN2_RX
PB6      ------> CAN2_TX
PD8      ------> USART3_TX
PD9      ------> USART3_RX
PA8      ------> USB_OTG_FS_SOF
PA9      ------> USB_OTG_FS_VBUS
PA10     ------> USB_OTG_FS_ID
PA11     ------> USB_OTG_FS_DM
PA12     ------> USB_OTG_FS_DP
PA5      ------> SPI1_SCK
PA6      ------> SPI1_MISO
PD7      ------> SPI1_MOSI
PA4      ------> SPI1_CS
```

* CAN1 - Primary CAN Bus
* CAN2 - Backup CAN Bus
* USART3 - External Communication
* USB_OTG - For flashing updates
* SPI - External Communication
