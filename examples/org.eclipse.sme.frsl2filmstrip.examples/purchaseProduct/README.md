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

  - Select `Open specification` button under `File` menu or you can use `Open specification` button right in the toolbar.

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

# KSE_2024_Draft

Generating Test Cases by Model Finding (USE/Model Validator

As you successfully go through Step 2, you will obtain a filmstrip model file `PurchaseProductFilmstrip.use`. 

- Open the `PurchaseProductFilmstrip.use` file. It will be loaded as in the below image.

![PurchaseProductFilmstrip.use](images/purchaseProductFilmstrip_open.png)

- Select `Configuration` under `Plugin > Model Validator`.

![Selecting `Configuration`](images/Selecting_Configuration.png)

- A Configuration window should appear like this:

![`Configuration` window](images/Config_window.png)

- Load the properties file (the `.properties` file) automatically generated along with the filmstrip model in Step 1 by selecting `File > Open`, then navigate to where the properties file is.
![Loading properties file](images/Loading_property.png)

- Choose a scenario (which corresponds to a search configuration) you want to generate test case for.  Once the configuration is loaded, you can update the configuration or add other constraints as needed before generating test data for the chosen scenario.

![Choosing a scenario to generate test case for](images/Choosing_scenarios.png)

- Hit the `Validate` button at the bottom-left corner of the configuration window to let the USE Model Validator find an approriate test case. This process may take some time. After that, the result will be shown in the Log window at the bottom of the USE window. 
  - In our example, the result is `SATISFIABLE`, which means that the Model Validator is able to find a test case for the chosen scenario. On the other hand, if the plugin failed to find a test case for the chosen scenario, the result `UNSATISFIABLE` will be shown in the Log.

![Showing results](images/Results.png)

- You can then select `View > Object diagram` to have a view of the object model corresponding to the test case the USE Model Validator generate. Below is a part of the test case generated in our example.

![Part of test case](images/part_of_scenario.png)
