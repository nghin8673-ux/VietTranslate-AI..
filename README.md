# VietTranslate AI

Ứng dụng dịch thuật thông minh hỗ trợ tiếng Việt sử dụng Streamlit.

## Hướng dẫn cài đặt và chạy

1. Cài đặt các thư viện cần thiết:
   ```bash
   pip install -r requirements.txt
   
streamlit run app.py
### 3. **`app.py`**
```python
import streamlit as st

st.set_page_config(
    page_title="VietTranslate AI",
    page_icon="🤖",
    layout="wide"
)

st.title("🤖 VietTranslate AI - Trợ lý Dịch Thuật")

# Giao diện người dùng
col1, col2 = st.columns(2)

with col1:
    st.subheader("Văn bản gốc")
    source_text = st.text_area("Nhập văn bản cần dịch:", height=200)
    source_lang = st.selectbox("Ngôn ngữ nguồn:", ["Tiếng Anh", "Tiếng Việt", "Tiếng Trung", "Tiếng Nhật"])

with col2:
    st.subheader("Bản dịch")
    target_lang = st.selectbox("Ngôn ngữ đích:", ["Tiếng Việt", "Tiếng Anh", "Tiếng Trung", "Tiếng Nhật"])
    
    if st.button("Dịch ngay", type="primary"):
        if source_text:
            # Mô phỏng quá trình dịch
            st.info("Đang xử lý dịch thuật...")
            st.text_area("Kết quả:", value=f"[Bản dịch mẫu cho]: {source_text}", height=200)
        else:
            st.warning("Vui lòng nhập văn bản cần dịch!")
