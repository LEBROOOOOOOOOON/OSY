UNIX
flowchart TB

    User[Používateľ] --> Apps[Aplikácie / Shell]
    Apps --> Kernel[Jadro (Kernel)]
    Kernel --> HW[Hardvér]

MS-DOS
flowchart TB

    User[Používateľ] --> Apps[Aplikácie (DOS programy)]
    Apps --> DOS[MS-DOS Services]
    DOS --> BIOS[BIOS]
    BIOS --> HW[Hardvér]
