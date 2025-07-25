<!--Copyright 2022 The HuggingFace Team. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with
the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on
an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the
specific language governing permissions and limitations under the License.

⚠️ Note that this file is in Markdown but contain specific syntax for our doc-builder (similar to MDX) that may not be
rendered properly in your Markdown viewer.

-->

# OPT

<div class="flex flex-wrap space-x-1">
<img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-DE3412?style=flat&logo=pytorch&logoColor=white">
<img alt="TensorFlow" src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white">
<img alt="Flax" src="https://img.shields.io/badge/Flax-29a79b.svg?style=flat&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAC0AAAAtCAMAAAANxBKoAAAC7lBMVEUAAADg5vYHPVgAoJH+/v76+v39/f9JbLP///9+AIgAnY3///+mcqzt8fXy9fgkXa3Ax9709fr+///9/f8qXq49qp5AaLGMwrv8/P0eW60VWawxYq8yqJzG2dytt9Wyu9elzci519Lf3O3S2efY3OrY0+Xp7PT///////+dqNCexMc6Z7AGpJeGvbenstPZ5ejQ1OfJzOLa7ejh4+/r8fT29vpccbklWK8PVa0AS6ghW63O498vYa+lsdKz1NDRt9Kw1c672tbD3tnAxt7R6OHp5vDe7OrDyuDn6vLl6/EAQKak0MgATakkppo3ZK/Bz9y8w9yzu9jey97axdvHzeG21NHH4trTwthKZrVGZLSUSpuPQJiGAI+GAI8SWKydycLL4d7f2OTi1+S9xNzL0ePT6OLGzeEAo5U0qJw/aLEAo5JFa7JBabEAp5Y4qZ2QxLyKmsm3kL2xoMOehrRNb7RIbbOZgrGre68AUqwAqZqNN5aKJ5N/lMq+qsd8kMa4pcWzh7muhLMEV69juq2kbKqgUaOTR5uMMZWLLZSGAI5VAIdEAH+ovNDHuNCnxcy3qcaYx8K8msGplrx+wLahjbYdXrV6vbMvYK9DrZ8QrZ8tqJuFms+Sos6sw8ecy8RffsNVeMCvmb43aLltv7Q4Y7EZWK4QWa1gt6meZKUdr6GOAZVeA4xPAISyveLUwtivxtKTpNJ2jcqfvcltiMiwwcfAoMVxhL+Kx7xjdrqTe60tsaNQs6KaRKACrJ6UTZwkqpqTL5pkHY4AloSgsd2ptNXPvNOOncuxxsqFl8lmg8apt8FJcr9EbryGxLqlkrkrY7dRa7ZGZLQ5t6iXUZ6PPpgVpZeJCJFKAIGareTa0+KJod3H0deY2M+esM25usmYu8d2zsJOdcBVvrCLbqcAOaaHaKQAMaScWqKBXqCXMJ2RHpiLF5NmJZAdAHN2kta11dKu1M+DkcZLdb+Mcql3TppyRJdzQ5ZtNZNlIY+DF4+voCOQAAAAZ3RSTlMABAT+MEEJ/RH+/TP+Zlv+pUo6Ifz8+fco/fz6+evr39S9nJmOilQaF/7+/f38+smmoYp6b1T+/v7++vj189zU0tDJxsGzsrKSfv34+Pf27dDOysG9t6+n/vv6+vr59uzr1tG+tZ6Qg9Ym3QAABR5JREFUSMeNlVVUG1EQhpcuxEspXqS0SKEtxQp1d3d332STTRpIQhIISQgJhODu7lAoDoUCpe7u7u7+1puGpqnCPOyZvffbOXPm/PsP9JfQgyCC+tmTABTOcbxDz/heENS7/1F+9nhvkHePG0wNDLbGWwdXL+rbLWvpmZHXD8+gMfBjTh+aSe6Gnn7lwQIOTR0c8wfX3PWgv7avbdKwf/ZoBp1Gp/PvuvXW3vw5ib7emnTW4OR+3D4jB9vjNJ/7gNvfWWeH/TO/JyYrsiKCRjVEZA3UB+96kON+DxOQ/NLE8PE5iUYgIXjFnCOlxEQMaSGVxjg4gxOnEycGz8bptuNjVx08LscIgrzH3umcn+KKtiBIyvzOO2O99aAdR8cF19oZalnCtvREUw79tCd5sow1g1UKM6kXqUx4T8wsi3sTjJ3yzDmmhenLXLpo8u45eG5y4Vvbk6kkC4LLtJMowkSQxmk4ggVJEG+7c6QpHT8vvW9X7/o7+3ELmiJi2mEzZJiz8cT6TBlanBk70cB5GGIGC1gRDdZ00yADLW1FL6gqhtvNXNG5S9gdSrk4M1qu7JAsmYshzDS4peoMrU/gT7qQdqYGZaYhxZmVbGJAm/CS/HloWyhRUlknQ9KYcExTwS80d3VNOxUZJpITYyspl0LbhArhpZCD9cRWEQuhYkNGMHToQ/2Cs6swJlb39CsllxdXX6IUKh/H5jbnSsPKjgmoaFQ1f8wRLR0UnGE/RcDEjj2jXG1WVTwUs8+zxfcrVO+vSsuOpVKxCfYZiQ0/aPKuxQbQ8lIz+DClxC8u+snlcJ7Yr1z1JPqUH0V+GDXbOwAib931Y4Imaq0NTIXPXY+N5L18GJ37SVWu+hwXff8l72Ds9XuwYIBaXPq6Shm4l+Vl/5QiOlV+uTk6YR9PxKsI9xNJny31ygK1e+nIRC1N97EGkFPI+jCpiHe5PCEy7oWqWSwRrpOvhFzcbTWMbm3ZJAOn1rUKpYIt/lDhW/5RHHteeWFN60qo98YJuoq1nK3uW5AabyspC1BcIEpOhft+SZAShYoLSvnmSfnYADUERP5jJn2h5XtsgCRuhYQqAvwTwn33+YWEKUI72HX5AtfSAZDe8F2DtPPm77afhl0EkthzuCQU0BWApgQIH9+KB0JhopMM7bJrdTRoleM2JAVNMyPF+wdoaz+XJpGoVAQ7WXUkcV7gT3oUZyi/ISIJAVKhgNp+4b4veCFhYVJw4locdSjZCp9cPUhLF9EZ3KKzURepMEtCDPP3VcWFx4UIiZIklIpFNfHpdEafIF2aRmOcrUmjohbT2WUllbmRvgfbythbQO3222fpDJoufaQPncYYuqoGtUEsCJZL6/3PR5b4syeSjZMQG/T2maGANlXT2v8S4AULWaUkCxfLyW8iW4kdka+nEMjxpL2NCwsYNBp+Q61PF43zyDg9Bm9+3NNySn78jMZUUkumqE4Gp7JmFOdP1vc8PpRrzj9+wPinCy8K1PiJ4aYbnTYpCCbDkBSbzhu2QJ1Gd82t8jI8TH51+OzvXoWbnXUOBkNW+0mWFwGcGOUVpU81/n3TOHb5oMt2FgYGjzau0Nif0Ss7Q3XB33hjjQHjHA5E5aOyIQc8CBrLdQSs3j92VG+3nNEjbkbdbBr9zm04ruvw37vh0QKOdeGIkckc80fX3KH/h7PT4BOjgCty8VZ5ux1MoO5Cf5naca2LAsEgehI+drX8o/0Nu+W0m6K/I9gGPd/dfx/EN/wN62AhsBWuAAAAAElFTkSuQmCC
">
<img alt="FlashAttention" src="https://img.shields.io/badge/%E2%9A%A1%EF%B8%8E%20FlashAttention-eae0c8?style=flat">
<img alt="SDPA" src="https://img.shields.io/badge/SDPA-DE3412?style=flat&logo=pytorch&logoColor=white">
</div>

## Overview

The OPT model was proposed in [Open Pre-trained Transformer Language Models](https://huggingface.co/papers/2205.01068) by Meta AI.
OPT is a series of open-sourced large causal language models which perform similar in performance to GPT3.

The abstract from the paper is the following:

*Large language models, which are often trained for hundreds of thousands of compute days, have shown remarkable capabilities for zero- and few-shot learning. Given their computational cost, these models are difficult to replicate without significant capital. For the few that are available through APIs, no access is granted to the full model weights, making them difficult to study. We present Open Pre-trained Transformers (OPT), a suite of decoder-only pre-trained transformers ranging from 125M to 175B parameters, which we aim to fully and responsibly share with interested researchers. We show that OPT-175B is comparable to GPT-3, while requiring only 1/7th the carbon footprint to develop. We are also releasing our logbook detailing the infrastructure challenges we faced, along with code for experimenting with all of the released models.*

This model was contributed by [Arthur Zucker](https://huggingface.co/ArthurZ), [Younes Belkada](https://huggingface.co/ybelkada), and [Patrick Von Platen](https://huggingface.co/patrickvonplaten).
The original code can be found [here](https://github.com/facebookresearch/metaseq).

Tips:
- OPT has the same architecture as [`BartDecoder`].
- Contrary to GPT2, OPT adds the EOS token `</s>` to the beginning of every prompt.

> [!NOTE]
> The `head_mask` argument is ignored when using all attention implementation other than "eager". If you have a `head_mask` and want it to have effect, load the model with `XXXModel.from_pretrained(model_id, attn_implementation="eager")`

## Resources

A list of official Hugging Face and community (indicated by 🌎) resources to help you get started with OPT. If you're
interested in submitting a resource to be included here, please feel free to open a Pull Request and we will review it.
The resource should ideally demonstrate something new instead of duplicating an existing resource.

<PipelineTag pipeline="text-generation" />

- A notebook on [fine-tuning OPT with PEFT, bitsandbytes, and Transformers](https://colab.research.google.com/drive/1jCkpikz0J2o20FBQmYmAGdiKmJGOMo-o?usp=sharing). 🌎
- A blog post on [decoding strategies with OPT](https://huggingface.co/blog/introducing-csearch#62-example-two---opt).
- [Causal language modeling](https://huggingface.co/course/en/chapter7/6?fw=pt#training-a-causal-language-model-from-scratch) chapter of the 🤗 Hugging Face Course.
- [`OPTForCausalLM`] is supported by this [causal language modeling example script](https://github.com/huggingface/transformers/tree/main/examples/pytorch/language-modeling#gpt-2gpt-and-causal-language-modeling) and [notebook](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/language_modeling.ipynb).
- [`TFOPTForCausalLM`] is supported by this [causal language modeling example script](https://github.com/huggingface/transformers/tree/main/examples/tensorflow/language-modeling#run_clmpy) and [notebook](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/language_modeling-tf.ipynb).
- [`FlaxOPTForCausalLM`] is supported by this [causal language modeling example script](https://github.com/huggingface/transformers/tree/main/examples/flax/language-modeling#causal-language-modeling).

<PipelineTag pipeline="text-classification" />

- [Text classification task guide](sequence_classification.md)
- [`OPTForSequenceClassification`] is supported by this [example script](https://github.com/huggingface/transformers/tree/main/examples/pytorch/text-classification) and [notebook](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/text_classification.ipynb).

<PipelineTag pipeline="question-answering" />

- [`OPTForQuestionAnswering`] is supported by this [question answering example script](https://github.com/huggingface/transformers/tree/main/examples/pytorch/question-answering) and [notebook](https://colab.research.google.com/github/huggingface/notebooks/blob/main/examples/question_answering.ipynb).
- [Question answering](https://huggingface.co/course/chapter7/7?fw=pt) chapter
  of the 🤗 Hugging Face Course.

⚡️ Inference

- A blog post on [How 🤗 Accelerate runs very large models thanks to PyTorch](https://huggingface.co/blog/accelerate-large-models) with OPT.


## Combining OPT and Flash Attention 2

First, make sure to install the latest version of Flash Attention 2 to include the sliding window attention feature.

```bash
pip install -U flash-attn --no-build-isolation
```

Make also sure that you have a hardware that is compatible with Flash-Attention 2. Read more about it in the official documentation of flash-attn repository. Make also sure to load your model in half-precision (e.g. `torch.float16``)

To load and run a model using Flash Attention 2, refer to the snippet below:

```python
>>> import torch
>>> from transformers import OPTForCausalLM, GPT2Tokenizer
>>> device = "cuda" # the device to load the model onto

>>> model = OPTForCausalLM.from_pretrained("facebook/opt-350m", torch_dtype=torch.float16, attn_implementation="flash_attention_2")
>>> tokenizer = GPT2Tokenizer.from_pretrained("facebook/opt-350m")

>>> prompt = ("A chat between a curious human and the Statue of Liberty.\n\nHuman: What is your name?\nStatue: I am the "
              "Statue of Liberty.\nHuman: Where do you live?\nStatue: New York City.\nHuman: How long have you lived "
              "there?")

>>> model_inputs = tokenizer([prompt], return_tensors="pt").to(device)
>>> model.to(device)

>>> generated_ids = model.generate(**model_inputs, max_new_tokens=30, do_sample=False)
>>> tokenizer.batch_decode(generated_ids)[0]
'</s>A chat between a curious human and the Statue of Liberty.\n\nHuman: What is your name?\nStatue: I am the Statue of Liberty.\nHuman: Where do you live?\nStatue: New York City.\nHuman: How long have you lived there?\nStatue: I have lived here for about a year.\nHuman: What is your favorite place to eat?\nStatue: I love'
```

### Expected speedups

Below is an expected speedup diagram that compares pure inference time between the native implementation in transformers using `facebook/opt-2.7b` checkpoint and the Flash Attention 2 version of the model using two different sequence lengths.

<div style="text-align: center">
<img src="https://user-images.githubusercontent.com/49240599/281101546-d2fca6d2-ee44-48f3-9534-ba8d5bee4531.png">
</div>

Below is an expected speedup diagram that compares pure inference time between the native implementation in transformers using `facebook/opt-350m` checkpoint and the Flash Attention 2 version of the model using two different sequence lengths.

<div style="text-align: center">
<img src="https://user-images.githubusercontent.com/49240599/281101682-d1144e90-0dbc-46f4-8fc8-c6206cb793c9.png">
</div>


### Using Scaled Dot Product Attention (SDPA)
PyTorch includes a native scaled dot-product attention (SDPA) operator as part of `torch.nn.functional`. This function
encompasses several implementations that can be applied depending on the inputs and the hardware in use. See the
[official documentation](https://pytorch.org/docs/stable/generated/torch.nn.functional.scaled_dot_product_attention.html)
or the [GPU Inference](https://huggingface.co/docs/transformers/main/en/perf_infer_gpu_one#pytorch-scaled-dot-product-attention)
page for more information.

SDPA is used by default for `torch>=2.1.1` when an implementation is available, but you may also set
`attn_implementation="sdpa"` in `from_pretrained()` to explicitly request SDPA to be used.

```python
from transformers import OPTForCausalLM
model = OPTForCausalLM.from_pretrained("facebook/opt-350m", torch_dtype=torch.float16, attn_implementation="sdpa")
...
```

For the best speedups, we recommend loading the model in half-precision (e.g. `torch.float16` or `torch.bfloat16`).

On a local benchmark (L40S-45GB, PyTorch 2.4.0, OS Debian GNU/Linux 11) using `float16` with
[facebook/opt-350m](https://huggingface.co/facebook/opt-350m), we saw the
following speedups during training and inference.

### Training

|    batch_size |    seq_len |  Time per batch (eager - s)   |    Time per batch (sdpa - s) |  Speedup (%)   |  Eager peak mem (MB)   |    sdpa peak mem (MB) |  Mem saving (%)   |
|--------------:|-----------:|:------------------------------|-----------------------------:|:---------------|:-----------------------|----------------------:|:------------------|
|             1 |        128 | 0.047                         |                        0.037 | 26.360         | 1474.611               |               1474.32 | 0.019             |
|             1 |        256 | 0.046                         |                        0.037 | 24.335         | 1498.541               |               1499.49 | -0.063            |
|             1 |        512 | 0.046                         |                        0.037 | 24.959         | 1973.544               |               1551.35 | 27.215            |
|             1 |       1024 | 0.062                         |                        0.038 | 65.135         | 4867.113               |               1698.35 | 186.578           |
|             1 |       2048 | 0.230                         |                        0.039 | 483.933        | 15662.224              |               2715.75 | 476.718           |
|             2 |        128 | 0.045                         |                        0.037 | 20.455         | 1498.164               |               1499.49 | -0.089            |
|             2 |        256 | 0.046                         |                        0.037 | 24.027         | 1569.367               |               1551.35 | 1.161             |
|             2 |        512 | 0.045                         |                        0.037 | 20.965         | 3257.074               |               1698.35 | 91.778            |
|             2 |       1024 | 0.122                         |                        0.038 | 225.958        | 9054.405               |               2715.75 | 233.403           |
|             2 |       2048 | 0.464                         |                        0.067 | 593.646        | 30572.058              |               4750.55 | 543.548           |
|             4 |        128 | 0.045                         |                        0.037 | 21.918         | 1549.448               |               1551.35 | -0.123            |
|             4 |        256 | 0.044                         |                        0.038 | 18.084         | 2451.768               |               1698.35 | 44.361            |
|             4 |        512 | 0.069                         |                        0.037 | 84.421         | 5833.180               |               2715.75 | 114.791           |
|             4 |       1024 | 0.262                         |                        0.062 | 319.475        | 17427.842              |               4750.55 | 266.860           |
|             4 |       2048 | OOM                           |                        0.062 | Eager OOM      | OOM                    |               4750.55 | Eager OOM         |
|             8 |        128 | 0.044                         |                        0.037 | 18.436         | 2049.115               |               1697.78 | 20.694            |
|             8 |        256 | 0.048                         |                        0.036 | 32.887         | 4222.567               |               2715.75 | 55.484            |
|             8 |        512 | 0.153                         |                        0.06  | 154.862        | 10985.391              |               4750.55 | 131.245           |
|             8 |       1024 | 0.526                         |                        0.122 | 330.697        | 34175.763              |               8821.18 | 287.428           |
|             8 |       2048 | OOM                           |                        0.122 | Eager OOM      | OOM                    |               8821.18 | Eager OOM         |

### Inference

|    batch_size |    seq_len |    Per token latency eager (ms) |    Per token latency SDPA (ms) |    Speedup (%) |    Mem eager (MB) |    Mem BT (MB) |    Mem saved (%) |
|--------------:|-----------:|--------------------------------:|-------------------------------:|---------------:|------------------:|---------------:|-----------------:|
|             1 |        128 |                          11.634 |                          8.647 |         34.546 |           717.676 |        717.674 |            0     |
|             1 |        256 |                          11.593 |                          8.86  |         30.851 |           742.852 |        742.845 |            0.001 |
|             1 |        512 |                          11.515 |                          8.816 |         30.614 |           798.232 |        799.593 |           -0.17  |
|             1 |       1024 |                          11.556 |                          8.915 |         29.628 |           917.265 |        895.538 |            2.426 |
|             2 |        128 |                          12.724 |                         11.002 |         15.659 |           762.434 |        762.431 |            0     |
|             2 |        256 |                          12.704 |                         11.063 |         14.83  |           816.809 |        816.733 |            0.009 |
|             2 |        512 |                          12.757 |                         10.947 |         16.535 |           917.383 |        918.339 |           -0.104 |
|             2 |       1024 |                          13.018 |                         11.018 |         18.147 |          1162.65  |       1114.81  |            4.291 |
|             4 |        128 |                          12.739 |                         10.959 |         16.243 |           856.335 |        856.483 |           -0.017 |
|             4 |        256 |                          12.718 |                         10.837 |         17.355 |           957.298 |        957.674 |           -0.039 |
|             4 |        512 |                          12.813 |                         10.822 |         18.393 |          1158.44  |       1158.45  |           -0.001 |
|             4 |       1024 |                          13.416 |                         11.06  |         21.301 |          1653.42  |       1557.19  |            6.18  |
|             8 |        128 |                          12.763 |                         10.891 |         17.193 |          1036.13  |       1036.51  |           -0.036 |
|             8 |        256 |                          12.89  |                         11.104 |         16.085 |          1236.98  |       1236.87  |            0.01  |
|             8 |        512 |                          13.327 |                         10.939 |         21.836 |          1642.29  |       1641.78  |            0.031 |
|             8 |       1024 |                          15.181 |                         11.175 |         35.848 |          2634.98  |       2443.35  |            7.843 |

## OPTConfig

[[autodoc]] OPTConfig

<frameworkcontent>
<pt>

## OPTModel

[[autodoc]] OPTModel
    - forward

## OPTForCausalLM

[[autodoc]] OPTForCausalLM
    - forward

## OPTForSequenceClassification

[[autodoc]] OPTForSequenceClassification
    - forward

## OPTForQuestionAnswering

[[autodoc]] OPTForQuestionAnswering
    - forward

</pt>
<tf>

## TFOPTModel

[[autodoc]] TFOPTModel
    - call

## TFOPTForCausalLM

[[autodoc]] TFOPTForCausalLM
    - call

</tf>
<jax>

## FlaxOPTModel

[[autodoc]] FlaxOPTModel
    - __call__

## FlaxOPTForCausalLM

[[autodoc]] FlaxOPTForCausalLM
    - __call__

</jax>
</frameworkcontent>
