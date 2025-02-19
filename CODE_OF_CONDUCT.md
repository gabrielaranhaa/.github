!pip install streamlit
!pip install streamlit_extras

import streamlit as st

st.set_page_config(page_title="Calculadora de Idade", page_icon="🕰️")

# Layout do app
st.title("🎂 Qual a sua idade?")

# Inputs do usuário
ano_de_nascimento = st.number_input("Qual ano você nasceu?", min_value=1900, max_value=2025, step=1)
ano_atual = st.number_input("Em que ano estamos?", min_value=1900, max_value=2025, step=1, value=2024)

if ano_de_nascimento and ano_atual:
    idade = ano_atual - ano_de_nascimento
    st.subheader(f"🕰️ Você tem {idade} anos!")

    # Exibir mensagem com cores diferentes
    if idade <= 25:
        st.success("🎉 Você é novo! Aproveite a vida! 🚀")
    else:
        st.warning("😎 Você é velho! Mas isso é só um número! 🔥")

# Rodar o Streamlit
st.write("📌 Para rodar o app, copie o código e execute no **Streamlit Cloud** ou localmente no terminal com `streamlit run nome_do_arquivo.py`.")

