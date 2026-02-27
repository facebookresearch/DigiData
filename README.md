# DigiData: Training and Evaluating General-Purpose Mobile Control Agents
[![Code License](https://img.shields.io/badge/Code_License-CC_BY--NC_4.0-blue)](https://creativecommons.org/licenses/by-nc/4.0/)

This repo is the home to DigiData paper.

> [!TIP]
> Click to Navigate!
> 
> [Dataset Release](#dataset-release)
> 
> [Running DigiData-Bench](#running-digidata-bench)

## Updates 

* **[Feb-27-26]:** DigiData dataset is released on Hugging Face: https://huggingface.co/datasets/facebook/DigiData
* **[Nov-10-25]:** DigiData [paper](https://arxiv.org/abs/2511.07413) is released. :fire::fire:

## Dataset Release

[![Dataset License](https://img.shields.io/badge/Dataset_License-CC_BY_4.0-olive)](https://creativecommons.org/licenses/by/4.0/)

The DigiData dataset is available on Hugging Face: https://huggingface.co/datasets/facebook/DigiData

## Running DigiData-Bench

> [!NOTE]
> We will release the full task set and scaffolding code soon, allowing you to create your own agent and evaluate it on the complete DigiData-Bench suite. For now, you can run the end-to-end benchmark using the provided demo set with either GPT-4o or Llama4 by following the instructions below.

### Step 1: Install the Required Packages

Create a conda environment by running

`conda create --name digidata_bench python=3.12`

then activate it with

`conda activate digidata_bench`

finally install the required packages by running

`pip install -r requirements.txt`.

### Step 2: Set up the Environment


Follow the instructions [here](./env/README.md) to set up the environment. After this step, you should have an running emulator as well as a terminal window open and have the Appium server running.

### Step 3: Set up Model API Key

In our default driver, we are using OpenAI's API to generate the model. You will need to set up an API key for this.

To use OpenAI model, get api key from [here](https://platform.openai.com/account/api-keys) and set it as an environment variable called `OPENAI_API_KEY`
```
export OPENAI_API_KEY=<YOUR_API_KEY>
```

To use Llama4 model, get api key from [here](https://llama.developer.meta.com/api-keys) and set it as an environment variable called `LLAMA_API_KEY`. Also set `api_key_name` in the configuration file to be `LLAMA_API_KEY`
```
export LLAMA_API_KEY=<YOUR_API_KEY>
```


### Step 4: Run the Benchmark

We provide a script to run the benchmark end-to-end. You can run it as follows:

```
python benchmark.py --config_filepath "configs/demo_3_bench_gpt4o.json"
```

This script will run a subset of the benchmark containing only 3 tasks, for demonstration purposes. Full task list will be released soon.


## License

The Data is released under CC-by 4.0. The CoT and descriptions are outputs of Llama 4, and subject to the Llama 4 license (https://github.com/meta-llama/llama-models/tree/main/models/llama4). if you use of this portion of the data to create, train, fine tune, or otherwise improve an AI model, which is distributed or made available, you shall also include “Llama” at the beginning of any such AI model name. Third party content pulled from other locations are subject to its own licenses and you may have other legal obligations or restrictions that govern your use of that content.

## Citation

```BibTeX
@misc{sun2025digidatatrainingevaluatinggeneralpurpose,
      title={DigiData: Training and Evaluating General-Purpose Mobile Control Agents}, 
      author={Yuxuan Sun and Manchen Wang and Shengyi Qian and William R. Wong and Eric Gan and Pierluca D'Oro and Alejandro Castillejo Munoz and Sneha Silwal and Pedro Matias and Nitin Kamra and Satwik Kottur and Nick Raines and Xuanyi Zhao and Joy Chen and Joseph Greer and Andrea Madotto and Allen Bolourchi and James Valori and Kevin Carlberg and Karl Ridgeway and Joseph Tighe},
      year={2025},
      eprint={2511.07413},
      archivePrefix={arXiv},
      primaryClass={cs.AI},
      url={https://arxiv.org/abs/2511.07413}, 
}
```