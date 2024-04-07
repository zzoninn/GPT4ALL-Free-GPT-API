<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?color=%2336BCF7&lines=GPT4ALL&font=Fira%20Code&center=true&width=380&height=50&duration=4000&pause=1000" alt="GPT4All">
  Free GPT-4 API access
</p>

We provide free access to the GPT-3.5-Turbo, GPT-4, GPT-4-Turbo and many other models.
To familiarize yourself with the API usage please follow this link

[Docs](https://docs.gpt4all.pp.ua)

[How to receive a token](https://docs.gpt4all.pp.ua/main/receiving-a-api-token)

## Limits

When you sign up, you will have **free access to 4 dollars per month.** You can spend them when using GPT 4, GPT 3.5 and other models. 

But the prices for the models will be much lower than OpenAI and Anthropic. In the future there may be changes in price and starting balance, follow the news in our telegram channel. 

You can also buy tariffs, with which you will have access to limited models, as well as will be increased balance per month.

## Rate Limits
**Limit for /1v/chat/completions:**

***Free plan** 10 requests per minute* 

***Tier 1** 100 requests per minute* 

***Tier 2 250** requests per minute*

***Tier 3** 550 requests per minute*


**Limit for /1v/image/generations:**

***Free plan** 6 requests per minute* 

***Tier 1** 90 requests per minute*

***Tier 2** 230 requests per minute*

***Tier 3** 490 requests per minute*


**Limit for /1v/moderations:**

***Free plan** 15 requests per minute*

***Tier 1** 140 requests per minute* 

***Tier 2** 310 requests per minute*

***Tier 3** 650 requests per minute*

These limits are also subject to change

## Plans
|**Tier 1 (5$/month)**|**Tier 2 (10$/month)**|**Tier 3 (15$/month)**|
|-----------------|------------------|------------------|
|Balance 30$/month|Balance 80$/month |Balance 150$/month|
|Access to premium models|Access to premium models|Access to premium models|Access to premium models
|Lower limits|Lower limits|Lower limits|Lower limits

## Models
### OpenAI
- gpt-4-vision-preview from tier 1 (in future)
- gpt-4-0125-preview from tier 1
- gpt-4-1106-preview
- gpt-4-32k
- gpt-4
- gpt-3.5-turbo-16k
- gpt-3.5-turbo-0613
- gpt-3.5-turbo-1106
- gpt-3.5-turbo-0125
- gpt-3.5-turbo
- dall-e-3
- text-moderation-latest (Free)
- text-moderation-stable (Free)

### Open Source
- gemma-7b-it
- mixtral-8x7b
- llama2-70b

## API Endpoint
Endpoint

https://api.gpt4all.pp.ua

## Usage
# Python

Chat Completions
``` Python
import requests

def main():
    data = {
        "messages": [{"role": "user", "content": "Hello World!"}],
        "model": "gpt-3.5-turbo",
        "temperature": 0.7, # Default is 0.7
        "max_tokens": 1024, # Default is 512
        "token": "YOUR_TOKEN"
    }

    response = requests.post("https://api.gpt4all.pp.ua/v1/chat/completions", json=data, verify=False)

    return response.json()

print(main())
```

Images Generations
``` Python
import requests
import base64

def main():

    data = {
        "prompt": "Cat",
        "model": "dall-e-3",
        "quality": "hd", # Default standart
        "format": "base64", # Default url
        "token": "YOUR_TOKEN"
    }

    response = requests.post("https://api.gpt4all.pp.ua/v1/images/generations", json=data, verify=False)

    with open("imageToSave.png", "wb") as f:
        f.write(base64.b64decode(response.json()))

main()
```

Moderations
``` Python
import requests

def main():

    data = {
        "message": "Hi",
        "model": "text-moderation-latest",
        "token": "YOUR_TOKEN"
    }

    response = requests.post("https://api.gpt4all.pp.ua/v1/moderations", json=data, verify=False)
    
    return response.json()
    
main()
```

## Links
[Telegram Channel](https://t.me/gpt4alltg)

[Telegram bot](https://t.me/gpt4all_robot)

[Docs](https://docs.gpt4all.pp.ua)
