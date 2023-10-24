# Functional Requirements Specification Language (FRSL)
# Plugin frsl2filmstrip

**Prerequisites:**
- Install frsl-1.0.0
- Install Acceleo: *Help -> Eclipse Marketplace -> Search "Acceleo 3.7" -> Install -> Next ...* (or using "Install New Software" with the update site: https://download.eclipse.org/acceleo/updates/releases/3.7/)
- Clone this repo.
- Open repo: 
  - *File -> Open Project From File System -> Specify to the folder 'frsl2filmstrip' to import org.eclipse.sme.frsl2filmstrip. 
- In *Problem* section (in Eclipse):
  - If any project is missing *src-gen* (*xtend-gen*), add manually folder *src-gen* (*xtend-gen*) to that project.
  - Fix the error 'An API baseline has not been set for the current workspace": (1) Click the menu: Windows\Preferences\Plug-in Development\API Baselines; (2) Update the option "Missing API baseline": Error -> Warning
  - ...

**Note:**
  - ...

**Usage\:**

- Run runtime: *Right click to any project -> Run As -> Eclipse Application*.
- In runtime environment, create general project: *File -> New Project -> General -> Project -> Next ...*
- In general project, create .frsl file: *Right click -> New -> File -> Set name "test.frsl" -> Finish*
- Generate the *.frslas* file from the *.frsl* file:
  - Open the *.frsl* file -> Right click on white space in file -> FRSLCS -> Save As -> FRSLAS.
- Generate the Filmstrip model (the two files: *.use* and *.properties*) from the *.frslas* file:
  - Open the *.frslas* file -> Right click on file icon -> Frslas2Filmstrip -> Generate Filmstrip Model.
