# Data Flow Codespaces Test

## 1. Open a Codespace in the browser

Open [this repository](https://github.com/zhen9910/dataflow-codespaces-test), select **Code > Codespaces**, and choose **Create codespace on main** to create a new Codespace. To reuse an existing Codespace, find it in the same menu and choose **Open in browser** from its three-dot menu.

Wait for the development container setup to finish before continuing.

## 2. Select a live AIO instance

Select the live Azure IoT Operations (AIO) instance to use.

## 3. Convert the Thing Description to a Thing Model

Run this prompt, then save the generated Thing Model as `Machines.Pump_1.TM.json`:

```text
@ot-dataflow /tmauthoring convert #input.td.json to a Thing Model, and add a new property OperationalDerivedMeasurementsPumpPowerOutput, which is calculated as OperationalMeasurementsPumpPowerInput multiplied by OperationalMeasurementsPumpEfficiency
```

## 4. Generate a dataflow

Select the reference files with the inline picker when entering this prompt:

```text
@ot-dataflow generate a dataflow from #input.td.json to #Machines.Pump_1.TM.json
```

## 5. Deploy the dataflow

Deploy the generated dataflow to the selected live AIO instance.
