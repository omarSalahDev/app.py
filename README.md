import streamlit as st

# 1. إعدادات الصفحة (نخليها Apple Style)
st.set_page_config(page_title="Omar's Data Roadmap", page_icon="🧭")

# إضافة بعض اللمسات الجمالية بـ CSS
st.markdown("""
    <style>
    .stButton>button { width: 100%; border-radius: 10px; height: 3em; font-weight: bold; }
    .title { text-align: center; color: #1e1e1e; }
    .subheader { text-align: center; color: #555; }
    </style>
    """, unsafe_allow_html=True)

# 2. هيكل البيانات (هنا التعديل السهل!)
# ده القاموس اللي فيه كل اللينكات، كل ما تنزل بوست، بس غير اللينك هنا
chapters = {
    "01": {"title": "Understanding Data", "link": "https://linkedin.com/posts/omarsaleh-cs_%D9%82%D8%B5%D8%A9-%D9%83%D8%B1%D8%B3%D9%8A-%D9%82%D8%AF%D9%8A%D9%85-%D8%A3%D8%B8%D9%87%D8%B1%D8%AA-%D8%B3%D8%B1-%D8%A3%D8%BA%D9%84%D9%89-%D9%85%D8%AC%D8%A7%D9%84-%D9%81%D9%8A-%D8%A7%D9%84%D8%B9%D8%A7%D9%84%D9%85-activity-7491739030548664320-wMk4?rcm=ACoAAFfGkf4Bchnn1vdJPOkg2UryBOqvABwrOGk"},
    "02": {"title": "Data Science Fundamentals", "link": "ضع_لينك_المنشور_الثاني_هنا"},
    "03": {"title": "Think Like a Data Analyst", "link": None},
    "04": {"title": "Data Ecosystem", "link": None},
    "05": {"title": "Data Analytics Toolbox", "link": None},
    "06": {"title": "Big Data", "link": None},
    "07": {"title": "Data Visualization", "link": None},
    "08": {"title": "Machine Learning Basics", "link": None},
    "09": {"title": "Data Career Roadmap", "link": None},
}

# 3. واجهة المستخدم
st.markdown("<h1 class='title'> Data Analytics Roadmap</h1>", unsafe_allow_html=True)
st.markdown("<p class='subheader'>رحلتي في مجال عالم البيانات من الصفر حتى الاحتراف</p>", unsafe_allow_html=True)
st.divider()

# عرض الأزرار
for ch, info in chapters.items():
    col1, col2 = st.columns([1, 4])
    with col1:
        st.button(f"Chapter {ch}", disabled=True)
    with col2:
        if info["link"] and info["link"] != "https://linkedin.com/posts/omarsaleh-cs_%D9%82%D8%B5%D8%A9-%D9%83%D8%B1%D8%B3%D9%8A-%D9%82%D8%AF%D9%8A%D9%85-%D8%A3%D8%B8%D9%87%D8%B1%D8%AA-%D8%B3%D8%B1-%D8%A3%D8%BA%D9%84%D9%89-%D9%85%D8%AC%D8%A7%D9%84-%D9%81%D9%8A-%D8%A7%D9%84%D8%B9%D8%A7%D9%84%D9%85-activity-7491739030548664320-wMk4?rcm=ACoAAFfGkf4Bchnn1vdJPOkg2UryBOqvABwrOGk":
            st.link_button(f"Read: {info['title']}", url=info["link"])
        else:
            st.button(f"{info['title']} - قريباً ⏳", disabled=True)

st.divider()
st.caption("صُمم بحب بواسطة عمر | Data Enthusiast")
