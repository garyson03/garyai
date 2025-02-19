git clone https://github.com/garyai/my-ai-agent.git
cd my-ai-agent
import openai

openai.api_key = "JOUW-API-SLEUTEL"

def chat_with_ai(prompt):
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role": "user", "content": prompt}]
    )
    return response["choices"][0]["message"]["content"]

if __name__ == "__main__":
    while True:
        vraag = input("Jij: ")
        if vraag.lower() in ["stop", "exit"]:
            break
        antwoord = chat_with_ai(vraag)
        print("AI: " + antwoord)
