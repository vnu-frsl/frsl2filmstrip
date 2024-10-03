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

- Run the tool USE:
  - Navigate to `<USE_folder>/use-assembly/target/use-7.1.1/bin`.
  - On Windows: run the `use.bat` file.
  - On Linux: open terminal and run the command `./use`.
- First, we have to load the source model. In this example, the source model is specified in `PurchaseProduct.use` that we just generated:

![Load source model](./images/1_loadSourceModel.png)

- Choose `PurchaseProduct.use`.

![Load source model window](./images/2_chooseModel.png)

A successful model load should look like this:

![Successful model load](./images/3_successfulModelLoad.png)

- Invoke the filmstrip plugin by selecting the menu item `Plugins -> Filmstrip`.

![Invoke filmstrip plugin](./images/4_invokeFilmstripPlugin.png)

- Save the .use file for Filmstrip model:

  - Hit `Select` to specify a save file.

![transformation options](./images/5_transformationOptions.png)

  - You do not have to select a file, just write the file name that you want. In this case, we will name it `PurchaseProductFilmstrip.use` and hit `Save`.

![naming file](./images/6_namingFile.png)

  - Hit `Ok` to start the transformation process.

![hit ok](./images/7_hitOk.png)

  - If the transformation is successful, it should show a window like this:

![successful window](./images/8_success.png)

### Step 3. Generating Test Cases by Model Finding (USE/Model Validator)

- TODO!
