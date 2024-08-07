## [EXAONE 3.0](EXAONE.md)

### Installation using Docker

supposed [Docker](https://www.docker.com/products/docker-desktop/) is installed.

```
# Powershell, use ${pwd} instead of %CD%
> docker run -it --rm --gpus all -v %CD%:/workspace pytorch/pytorch:2.4.0-cuda12.1-cudnn9-devel

# inside container
root@473c7bb9aa01:/workspace# pip install transformers accelerate
```

### Hugging Face login

Before starting, need a hugging face ID and access to the [repository](https://huggingface.co/LGAI-EXAONE/EXAONE-3.0-7.8B-Instruct). <br>

Receive an access token with `Read` privileges in the `Hugging Face`'s setting. <br>
Token starts with `hf_`

```
root@473c7bb9aa01:/workspace# huggingface-cli login
~
    To login, `huggingface_hub` requires a token generated from https://huggingface.co/settings/tokens .
Enter your token (input will not be visible): **TYPE TOKEN HERE**
Add token as git credential? (Y/n) n
~~
Login successful
```

### Try it out

At first time, it may take time to download related files. <br>
Test it by changing the `prompt` in the python file (line 13:14). <br>

```
root@473c7bb9aa01:/workspace# python quickstart.py
```

> Note that it's inefficient to load the model every time.
