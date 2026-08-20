import streamlit as st
import google.generativeai as genai

st.set_page_config(page_title="Viora AI Assistant", page_icon="🤖")

st.title("🤖 Viora AI Assistant")
st.write("Welcome! Yeh aapka apna AI app hai jo Gemini se powered hai.")

# Gemini API Key input
api_key = st.text_input("Enter your Gemini API Key:", type="password")

if api_key:
    genai.configure(api_key=api_key)
    model = genai.GenerativeModel('gemini-1.5-flash')

    user_input = st.text_input("Apna sawal yahan likhein:")

    if st.button("Ask AI"):
        if user_input:
            with st.spinner("AI is thinking..."):
                try:
                    response = model.generate_content(user_input)
                    st.success("AI Response:")
                    st.write(response.text)
                except Exception as e:
                    st.error(f"Error: {e}")
        else:
            st.warning("Pehle kuch type karein!")
else:
    st.info("Kripya apna Gemini API key enter karein taake app chalu ho sake.")
