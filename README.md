# ChatGPT-API-linux-terminal-
The wondrous Python script that unlocks the full potential of ChatGPT API and lets you experience the glory of a simulated Linux Terminal.

## Prerequisites

```pip install openai```

Now, to get your hands on an OpenAI API key, you’ll need to pop over to the OpenAI homepage and log in to your account. Once you’re in, make your way to the membership page and look for the option to create an API key.

## Python Script

```
import openai

openai.api_key = "YOUR_OPENAI_API_KEY"

impersonated_role = "I want you to act as a Linux terminal, " \
                    "I will type commands and you will reply with what the terminal should show. " \
                    "I want you to reply with the terminal output inside a unique code block and nothing else." \
                    "do not write explanations." \
                    "do not type commands unless I instruct you to do so." \
                    "When I need to tell you something in English I will do so by putting text inside curly brackets {something like this}."

command_history = ""
while True:
    command_prompt = input("Input command: ")
    output = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[
            {"role": "system", "content": f"{impersonated_role}. based on this command history: {command_history}"},
            {"role": "user", "content": f"{command_prompt}"},
        ]
    )

    for item in output['choices']:
        print(item['message']['content'])
        command_history = f"{command_history}command:{command_prompt}\noutput:{item['message']['content']}\n"
```

## Output Examples

![alt text](https://github.com/janfilips/ChatGPT-API-linux-terminal/blob/main/example-output/1.png?raw=true)

![alt text](https://github.com/janfilips/ChatGPT-API-linux-terminal/blob/main/example-output/2.png?raw=true)

![alt text](https://github.com/janfilips/ChatGPT-API-linux-terminal/blob/main/example-output/3.png?raw=true)

![alt text](https://github.com/janfilips/ChatGPT-API-linux-terminal/blob/main/example-output/4.png?raw=true)

![alt text](https://github.com/janfilips/ChatGPT-API-linux-terminal/blob/main/example-output/5.png?raw=true)

Whoa, hold the phone! The Linux Terminal simulation with the ChatGPT API is like, totally blowing my mind! And the Python interpreter simulation within the Terminal is straight-up mind-boggling!
