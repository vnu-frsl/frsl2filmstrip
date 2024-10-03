# PurchaseProduct example evaluation guide

## Prerequisites

This guide assumes you have already read the [README](../../../README.md) and have the necessary tools installed.

You can use the provided files in this folder to evaluate this example.

## Evaluation

### Step 1. Defining an application model for use cases (Eclipse/FRSL)

- Import the `frsl` and `frsl2filmstrip` projects into Eclipse.
- Run the runtime environment: *Right click to any project -> Run As -> Eclipse Application*.
- In the runtime environment, load the example projects (examples/org.eclipse.sme.frsl2filmstrip.examples/).
- Generate the *.frslas* file from the *.frsl* file:
  - Open the `purchaseProduct.frsl` file -> Right click on white space in file -> FRSLCS -> Save As -> FRSLAS.

![FRSLAS generation](images/genFRSLAS.png)

- Generate the Filmstrip model (the two files: *.use* and *.properties*) from the *.frslas* file:
  - Open the `purchaseProduct.frslas` file -> Right click on file icon -> Frslas2Filmstrip -> Generate Filmstrip Model.

![Filmstrip generation](images/genFilmstrip.png)

- After the generation, you will see the two files in the `filmstrip-gen` folder (which are equivalent to the files in the `USE_purchaseProduct` folder).

![Filmstrip generation (output)](images/filmstripGenOutput.png)

### Step 2. Generating the filmstrip model (USE/Filmstrip)

- TODO!

### Step 3. Generating Test Cases by Model Finding (USE/Model Validator)

- TODO!