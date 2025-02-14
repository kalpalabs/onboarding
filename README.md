# AI assisted programming
Install [Cursor](cursor.com) and configure it with our private API keys for GPT4o. (Ask Prashant)
* Cursor does incredibly well at programming until the project grows and it just stops working. We usually need to understand & restructure the project a bit to make it work again. 
* When you're learning something new, it's okay to use Cursor, but try to not blindly use it - which will impair learning. 
* LLMs also sometimes silently fail, and / or misdirect into a completely wrong direction. Try to proof read the generated code as much as possible. 
* You can also use Gemini 2.0 from aistudio.google.com. Note that the models on gemini.google.com aren't the same as aistudio.google.com even though their names are same. 


## Using GPUs
### Setting up SSH 
Install [Remote SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) extension in Cursor/VScode. 

Copy .sshconfig to ~/.ssh/config, i.e, 
```
cat .sshconfig >> ~/.sshconfig
```

Add the private key to ~/.ssh/azure-key-rsa.pem (Prashant will provide the private key) and make it readonly. 

```
chmod 400 ~/.ssh/azure-key-rsa.pem
```

**DO NOT PROVIDE THE PRIVATE KEY TO ANYONE** : This key provides access to all our VMs, so do not provide it to anyone for any reason. 


CMD+Shift+P to see names for all the VMs. Choose the right VM based on the guidelines in [compute_details.md](https://github.com/kalpalabs/onboarding/blob/main/compute_details.md)

### Setup your work directory
SSH will take you to `/home/azureuser`, please create a root directory with your username like `/home/azureuser/pshishodia` and only work inside this directory. Do all git-clones inside this directory as well. 

### Use virtual environments. 
You can either use vanilla virtual environments with pip, or you can use [uv](https://github.com/astral-sh/uv) - a superfast python package manager. 

Vanilla virtual environments
```
python3 -m venv .venv
pip install -r requirements.txt
```

uv virtual environments
```
pip install uv
uv venv 
uv venv -python 3.12.0 # (alternatively)
uv pip install -r requirements.txt
```




