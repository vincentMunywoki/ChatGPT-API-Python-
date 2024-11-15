## Learn how to get OpenAI Key Token

Register for openai account

Create google colab file and install openai python library using this command
## Two different methods of using ChatGPT API in Python
## Method 1 - using OpenAI Python Package

## !pip install -q openai
##-q is for quiet installation

## tell the ai what to do.

messages = [
    {"role": "system", "content": "You are a kind helpful assistant."}
]

so that it can know how to behave and what not to do.

## create an infinite loop.
while True:
    message = input("user: ")  # Get user input
    if message:  # Check if the input is not empty
        messages.append(
            {"role": "user", "content": message},
        )
        
        # Create a chat completion
        chat = openai.ChatCompletion.create(
            model="gpt-3.5-turbo",
            messages=messages
        )
        
        reply = chat.choices[0].message.content  # Get the assistant's reply
        
        print(f"ChatGPT: {reply}")  # Print the reply
        messages.append({"role": "assistant", "content": reply})  # Add the reply to the messages

## import openai
