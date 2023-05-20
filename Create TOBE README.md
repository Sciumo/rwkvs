# rwkvs

RWKV Chat simplified :one: :two: :three: :thumbsup: 

* Goal is to be the simplest :relieved: and fastest :zap: way to use [RWKV](https://github.com/BlinkDL/RWKV-LM) local, well-performing ChatGPT-like language model.

No package. Just clone.

Includes preconfigured:
* Command line chat ```python chat.py```
* Training from scratch ```python train.py mydata.jsonl```
* Simple web service (openapi) ```python server.py```

# Setup

1. Clone this repo  ```git clone https://github.com/Sciumo/rwkvs```
    1. If you want *batteries included* then ```git clone --recurse-submodules https://github.com/Sciumo/rwkvs```
    2. This will also clone a small recent model, the 700mb [169m pile](https://huggingface.co/RWKV/rwkv-4-169m-pile)
2. Install required libs  ```cd rwkvs```  ```pip install -r requirements```
    1. For some, this will be where most issues come from.
    2. Make an environment using [venv](https://docs.python.org/3/library/venv.html) or [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/)
4. Now play with it. ```python chat.py```

# Config
***rwkvs*** uses few parameters: model, data, config. 

Instead of a list of complex paramters, ***rwkvs*** uses a [YAML](https://yaml.org/) config file ```config.yaml```

## Config settings in [YAML](https://yaml.org/)
```yaml
model: rwkv-4-169m-pile  # default model
model_dir: ./models      # default models dir, should change this
chat_language: english   # also chinese

```

# Adding models

1. Best to keep models together in another directory, and not in rwks. let's say ```../models```
2. For now, search on [huggingface almost all models will be there](https://huggingface.co/models?search=rwkv) 
3. Choose a model, and clone into whever you put ```../models```
4. Pass model in as a parameter ```python chat.py ../model/cool-7b```
    1. Better yet edit the ```config.yaml``` 
    2. Set default model ```model:cool-7b```
    3. Set default model directory ```model_dir:../model```


