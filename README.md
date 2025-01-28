import streamlit as st
import openai

# Set up OpenAI API key
openai.api_key = "YOUR_OPENAI_API_KEY"

# App title
st.title("AI Friend & Life Coach Chatbot")

# Chat input
user_input = st.text_input("Talk to me:")

if user_input:
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role": "system", "content": "You are a kind and supportive AI friend & life coach. Provide motivational advice and emotional support."},
                  {"role": "user", "content": user_input}]
    )
    st.write(response['choices'][0]['message']['content'])
    
