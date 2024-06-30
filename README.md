# UAVCAN Project Setup Guidelines

## Folder Structure

    .
    ├── API_doc.docx                     # General development information
    ├── Readme.md                        # This readme
    ├── General                          # Some general files like: diagrams, architecture...
    ├── Autonomous                       # Setup for kr_autonomous_flight
    │   ├── IMX8                         # Setup i.MX8NavQPlus
    │   ├── Intel_Realsense              # Build the librealsense and the realsense ros wrapper
    │   └── kr_autonomous_flight_stack   # Build and setup the kr autonomous flight stack
    ├── ESC                              # Setup for ESC
    │   ├── Record                       # Images and videos
    │   ├── Config                       # Configuration files for the component
    │   └── Readme.md                    # Guidelines content here
    ├── BMS                              # Setup for BMS
    │   ├── Record
    │   ├── Config
    │   └── Readme.md
    ├── GNSS                             # Setup for GNSS
    │   ├── Record
    │   ├── Config
    │   └── Readme.md
    ├── FMU                              # Guidelines for FMU (IMU data included in this part)
    │   ├── Record
    │   ├── Config
    │   └── Readme.md
    ├── HITL                             # Guidelines for HITL (Working in progress)
    │   ├── Record
    │   ├── Config
    │   └── Readme.md
    ├── Test                             # Testing results
    │   ├── Test_report.xlsx
    │   └── Logs

## Architecture design

`<a style="padding:100px"><img src="./General/architecture-design.png" width="1000px"/>``</a>`

## Hardware connection diagram

`<a style="padding:100px"><img src="./General/hardware-diagram.png" width="1000px"/>``</a>`

## Video recording (Demo, testing)

Refer to link: https://git3.fsoft.com.vn/GROUP/DAP1UAVFP/management/management/-/tree/master/Project_Recording
