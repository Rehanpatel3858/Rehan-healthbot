# Rehan-healthbot 
from openai import OpenAI

client= OpenAI(
    api_key=" your_api",
    base_url="https://api.groq.com/openai/v1"
)
while True:
    user_input= input("you:")
    if user_input=="quit":
        print("bot: GOOD BY")
        break
    response = client.chat.completions.create(
        model= "llama3-70b-8192",
        messages= [
            {"role": "system","content": "you are a health bot,provide information all type of cooking and healt  related question and also provide personal opinion"},
            {"role": "user", "content": user_input}
        ]
    )
    print("bot:", response.choices[0].message.content) 
