# Functional Requirements Specification Language (FRSL)
# Plugin frsl2filmstrip

**Prerequisites:**
- Install Eclipse DSL Tools 2024-03
- Install the repo `frsl` (git@github.com:vnu-sme/frsl.git) 
- Install Acceleo by the update site: https://download.eclipse.org/releases/2024-03
- Clone this repo.
- Open repo:  
  - *File -> Open Project From File System -> Specify to folder 'frsl' -> Deselect the 'frsl' checkbox -> Select 'Search for nested projects' -> Finish*.
  - *File -> Open Project From File System -> Specify to folder 'frsl2filmstrip' -> Select 'Search for nested projects' -> Finish*.
- In *Problem* section (in Eclipse):
  - If any project is missing *src-gen* (*xtend-gen*), add manually folder *src-gen* (*xtend-gen*) to that project.
  - Fix the error 'An API baseline has not been set for the current workspace": (1) Click the menu: Windows\Preferences\Plug-in Development\API Baselines; (2) Update the option "Missing API baseline": Error -> Warning
  - ...

**Note:**
  - JavaSE-21 is recommended.

**Usage\:**

- Run runtime: *Right click to any project -> Run As -> Eclipse Application*.
- In runtime environment, create general project: *File -> New Project -> General -> Project -> Next ...*
- In general project, create .frsl file: *Right click -> New -> File -> Set name "test.frsl" -> Finish*
- Generate the *.frslas* file from the *.frsl* file:
  - Open the *.frsl* file -> Right click on white space in file -> FRSLCS -> Save As -> FRSLAS.
- Generate the Filmstrip model (the two files: *.use* and *.properties*) from the *.frslas* file:
  - Open the *.frslas* file -> Right click on file icon -> Frslas2Filmstrip -> Generate Filmstrip Model.
