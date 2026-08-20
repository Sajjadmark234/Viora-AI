import streamlit as st

st.set_page_config(page_title="AI Assistant Pro", page_icon="🤖")

st.title("🤖 My All-in-One AI App")
st.write("Welcome! Yeh aapka apna AI app hai jo mobile se chal raha hai.")

# Simple Chat Input
user_input = st.text_input("Apna sawal yahan likhein:")

if st.button("Send"):
    if user_input:
        st.success(f"Aapne kaha: {user_input}")
        st.info("AI Response: Yeh ek test response hai. Jald hi isme Gemini AI connect hoga!")
    else:
        st.warning("Pehle kuch type karein!")
