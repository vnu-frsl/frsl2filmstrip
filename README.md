# Functional Requirements Specification Language (FRSL)

## Plugin frsl2filmstrip

## Prerequisites

- Install Eclipse DSL Tools 2024-03
- Install the repo `frsl` ([git@github.com:vnu-sme/frsl.git](https://github.com/vnu-sme/frsl))
- Install Acceleo by the update site: <https://download.eclipse.org/releases/2024-03>
- Clone this repo.
- Import this repository as Eclipse projects:
  - *File -> Open Project From File System -> Specify to folder 'frsl' -> Deselect the 'frsl' checkbox -> Select 'Search for nested projects' -> Finish*.
  - *File -> Open Project From File System -> Specify to folder 'frsl2filmstrip' -> Select 'Search for nested projects' -> Finish*.
- In *Problem* section (in Eclipse):
  - If any project is missing *src-gen* (*xtend-gen*), add manually folder *src-gen* (*xtend-gen*) to that project.
  - Fix the error 'An API baseline has not been set for the current workspace": (1) Click the menu: Windows\Preferences\Plug-in Development\API Baselines; (2) Update the option "Missing API baseline": Error -> Warning

## Note

- JavaSE-21 is recommended.

## Usage

### Step 1. Defining an application model for use cases (Eclipse/FRSL)

- Run runtime: *Right click to any project -> Run As -> Eclipse Application*.
- In the runtime environment, create a general project: *File -> New Project -> General -> Project -> Next ...*
- In the general project, create a .frsl file: *Right click -> New -> File -> Set name "anyFrslModel.frsl" -> Finish*
  - You can also load a given example in `examples/org.eclipse.sme.frsl2filmstrip.example`
- Generate the *.frslas* file from the *.frsl* file:
  - Open the *.frsl* file -> Right click on white space in file -> FRSLCS -> Save As -> FRSLAS.
- Generate the Filmstrip model (the two files: *.use* and *.properties*) from the *.frslas* file:
  - Open the *.frslas* file -> Right click on file icon -> Frslas2Filmstrip -> Generate Filmstrip Model.

### Step 2. Generating the filmstrip model (USE/Filmstrip)

- Install the USE tool: <https://github.com/useocl/use>.
- Replace the files for the USE plugins (Filmstrip and Model Validator) located in the folder `use-7.1.1/lib/plugins` with the two files `filmstrip-7.1.1.jar` and `validator-7.1.1.jar` in the folder `/examples/org.eclipse.sme.frsl2filmstrip.examples/USE-plugins/`.
- Load the application model corresponding to the generated .use file from Step 1.
- Invoke the USE Filmstrip plugin by selecting the menu item `Plugins -> Filmstrip`, indicated by a film-like icon.
- Save the .use file for the Filmstrip model that was generated from the application model.
  
### Step 3. Generating Test Cases by Model Finding (USE/Model Validator)

- Using the USE model validator plugin to load the configuration (after manually tuning the bound constraints).
- Performing test cases generation by model finding.
