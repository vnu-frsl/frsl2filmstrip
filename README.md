# Functional Requirements Specification Language (FRSL)
# Plugin frsl2filmstrip

## Prerequisites
- Install Eclipse DSL Tools 2024-03 (untested with latest versions).
- Install the repository `frsl`: https://github.com/vnu-sme/frsl.
- Install Acceleo by the update site: https://download.eclipse.org/releases/2024-03.
  - *Help -> Install New Software...*
  - Note: `frsl` requires UML2 Extender SDK from this update site, too.
- Clone this repository.
- Inside Eclipse, import this repository as Eclipse projects:
  - *File -> Open Project From File System -> Specify to folder 'frsl' -> Select 'Search for nested projects' -> Finish*.
  - *File -> Open Project From File System -> Specify to folder 'frsl2filmstrip' -> Select 'Search for nested projects' -> Finish*.
    - Note: The IDE may ask for installing OCL as the projects have "OCL Nature", but the projects have their OCL dependencies bundled.
- In *Problem* section (in Eclipse):
  - If any project is missing *src-gen* (*xtend-gen*), add manually folder *src-gen* (*xtend-gen*) to that project.
  - Fix the error 'An API baseline has not been set for the current workspace":
    - (1) Click the menu: Windows\Preferences\Plug-in Development\API Baselines
    - (2) Update the option "Missing API baseline": Error -> Warning
  - Other issues: To be reported.

## Note
  - JavaSE-21 is recommended.

## Usage

### 1. Eclipse
- Install Eclipse and load the projects, following the Prerequisites.
- Run runtime: *Right click to any project -> Run As -> Eclipse Application*.
- In the runtime environment, create a general project: *File -> New Project -> General -> Project -> Next ...*
- In the general project, create a .frsl file: *Right click -> New -> File -> Set name "something.frsl" -> Finish*
  - You can also load a given example in examples/org.eclipse.sme.frsl2filmstrip.examples
- Generate the *.frslas* file from the *.frsl* file:
  - Open the *.frsl* file -> *Right click on white space in file -> FRSLCS -> Save As -> FRSLAS.*
- Generate the Filmstrip model (the two files: *.use* and *.properties*) from the *.frslas* file:
  - Open the *.frslas* file -> *Right click on file icon -> Frslas2Filmstrip -> Generate Filmstrip Model.*

### 2. USE

- Install the USE tool: https://github.com/useocl/use.
- Load the generated .use file using the tool.
- Select Plugins/Filmstrip to use the use-filmstrip plugin (which has a film-like icon).
- Generate a Filmstrip model from the original USE model.
- TODO: Finish this guide.
  - Using the USE model validator plugin to load the configuration (after manually tuning the bound constraints).
  - Performing test cases generation by model finding.
