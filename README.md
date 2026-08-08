
Single-GPU Model Water Savings Dashboard

This repository contains an interactive research dashboard for comparingrepresentative language models using model size, measured inferenceenergy, and estimated operational water consumption. The interface isdesigned to make sustainability information visible during AI modelselection.

Dashboard Overview

The dashboard compares five representative benchmark entries withsubstantially different model sizes while keeping the reported GPU countfixed at one:

Model                Parameters GPU                           Energy per prompt

Llama-3.2-1B              1.24B 1 × NVIDIA L4                         0.0028 WhGemma-2B                  2.51B 1 × NVIDIA A100-SXM4-40GB             0.0048 WhOPT-6.7B                  6.66B 1 × NVIDIA A100-SXM4-40GB             0.0147 WhOPT-13B                  12.85B 1 × NVIDIA H100 80GB HBM3             0.0235 WhQwen1.5-32B-Chat         32.51B 1 × NVIDIA H100 80GB HBM3             0.0356 Wh

GPU count is fixed at one, but GPU type differs across entries. Thedashboard therefore presents a benchmark comparison rather than acontrolled comparison of parameter count alone.

Features

Select a larger/current model and a smaller alternative.

Compare parameter count and measured inference energy per prompt.

Enter a workload size or use 100, 1K, and 10K prompt presets.

View estimated operational water use.

View estimated energy and water savings for the selected workload.

View model-size reduction.

Inspect and modify the water-estimation assumptions.

Compare models through side-by-side visual indicators.

Energy Data

The dashboard uses measured inference-energy values associated with theselected benchmark entries. Energy is displayed in watt-hours (Wh) perprompt. It is not estimated from parameter count.

Operational Water Estimation

Operational water consumption is estimated from inference energy usingthe methodology of Li et al. The dashboard uses the followingrelationship:

Water = E × [WUE_on-site + (PUE × EWIF)]

where:

E = inference energy in kWh

WUE_on-site = onsite water usage effectiveness (L/kWh)

PUE = power usage effectiveness

EWIF = electricity water intensity (L/kWh)

The dashboard currently uses these default parameters:

Onsite WUE = 0.550 L/kWh

PUE = 1.170

Electricity water intensity = 3.142 L/kWh

The parameters can be changed in the interface.

Water values are estimates, not direct measurements. Actual operationalwater consumption can vary with data-center location, coolingtechnology, weather, electricity source, infrastructure efficiency, andoperating conditions.

How to Run

Download or clone the project.

Open single_gpu_model_water_dashboard_li_updated(1).html in amodern web browser.

No installation, server, build process, or external package isrequired.

How to Use

Choose the larger/current model.

Choose a smaller alternative.

Enter the number of prompts or select a workload preset.

Review energy savings, estimated water savings, and model-sizereduction.

Inspect the side-by-side comparison.

Click Show Li et al. assumptions to inspect or modify thewater-estimation parameters.

Intended Use

This dashboard is a research prototype for illustratingsustainability-aware AI model selection. It does not determine whether asmaller model is suitable for a specific task and does not evaluatemodel quality or task performance. A smaller model should notautomatically be interpreted as the preferred model for every use case.

Limitations

The models are representative benchmark entries rather than resultsfrom a new controlled experiment.

GPU count is fixed at one, but GPU type is not identical across allmodels.

Operational water consumption is estimated rather than directlymeasured.

Water estimates depend on the PUE, onsite WUE, and electricitywater-intensity assumptions.

The dashboard does not currently incorporate task accuracy, modelquality, latency, carbon emissions, or monetary cost.

The prototype has not yet been evaluated through a user study.

References

Inference-energy benchmark

Caravaca, F., Cuevas, Á., & Cuevas, R. (2025). From Prompts to Power:Measuring the Energy Footprint of LLM Inference. arXiv:2511.05597.

Operational water estimation

Li, P., Yang, J., Islam, M. A., & Ren, S. (2025). Making AI Less"Thirsty". Communications of the ACM, 68(7), 54--61. DOI:10.1145/3724499.

Research Context

The dashboard supports research on sustainability-aware AI modelselection, particularly in organizational and public-sector settings.Its contribution is not a new energy benchmark or water-footprint model.Instead, it demonstrates how existing sustainability measurements can betranslated into an interactive decision-support interface that makesresource implications visible during model selection.
