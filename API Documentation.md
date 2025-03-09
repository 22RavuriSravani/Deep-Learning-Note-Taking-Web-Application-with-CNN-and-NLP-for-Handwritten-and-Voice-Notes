# Google Gemini 1.5 Pro API Documentation

## 1. Introduction to Gemini 1.5 Pro
**Gemini 1.5 Pro** is a powerful generative AI model developed by Google. It excels in **natural language understanding, multimodal processing, and generating contextual responses across various modalities (text, video, and audio)**.

### Features Integrated in This Project:
✅ Text Extraction from Images (Handwritten Notes)

✅ Speech-to-Text Conversion

✅ Intelligent Chatbot Capabilities

✅ Context-Aware Conversations

---

## 2. Why Gemini 1.5 Pro Over Other Models?

| Feature                | Gemini 1.5 Pro                          | GPT-4             | Claude 3       | Mistral       |
|------------------------|--------------------------------|-----------------|---------------|--------------|
| **Multimodal Support** | ✅ (Text, Images, Video, Audio) | ✅ (Text & Images) | ❌ (Only Text) | ❌ (Only Text) |
| **Context Length**     | ✅ Up to 1 Million Tokens      | ❌ 128K Tokens  | ❌ 200K Tokens | ❌ 32K Tokens |
| **Speed & Efficiency** | ✅ Fast & Optimized           | ❌ Medium Speed | ❌ Slower      | ❌ Slower     |
| **Fine-Tuning Support**| ✅ Yes                        | ❌ Limited      | ❌ Limited    | ✅ Yes       |

### 🔥 Advantages Over Other AI Models:
- **Multimodal Capabilities**: Unlike OpenAI’s GPT models, **Gemini 1.5 Pro** processes and generates responses based on text and images.
- **Optimized Performance**: Efficient for real-time chatbot interactions.
- **Cost-Effective API Usage**: Accessible via **Google AI API** with competitive pricing.
- **Seamless Google Cloud Integration**: Enhances AI functionalities with direct connectivity.
- **Extended Token Support**: Processes **up to 32,768 tokens**, ideal for long-context tasks.
- **Flexible Rate Limits**:
  - Free plan: **15 requests per minute (RPM)**
  - Pay-as-you-go: **2,000 RPM** and **4 million tokens per minute (TPM)**

---

## 3. How To Integrate Gemini 1.5 Pro

### 🔑 Step 1: Get API Key
1. Visit [Google AI Studio](https://aistudio.google.com/).
2. Generate an API Key.
3. Copy and store the API Key securely.

### 📦 Step 2: Install Required Libraries
```bash
pip install google-generativeai
```

### 🔧 Step 3: Authenticate & Configure API
```python 
import google.generativeai as genai 
# Set up the API key 
genai.configure(api_key="YOUR_API_KEY") 
```

### 🚀 Step 4: Accessing the Model
```python
model = genai.GenerativeModel("gemini-1.5-pro")
```

---

## 4. How Gemini 1.5 Pro is Created & Called in Code

### 4.1. 🎯 Creation Process
Gemini 1.5 Pro is built using:
- **Google TPUs (Tensor Processing Units)** for faster inference.
- **Transformer-based architecture** with enhanced attention mechanisms.
- **Optimized tokenization** for efficient handling of long contexts.
- **Fine-tuned multimodal dataset training** for text, images, video, and audio.

### 4.2. 🏗️ How It is Called in Code
The API processes inputs and generates responses using `genai.generate_content()`:
- **Text-only input**: Utilizes **Natural Language Processing (NLP)**.
- **Multimodal input (text + image)**: Uses **vision-language models**.
- **Accelerated processing**: **Google TPUs** enhance response speed and accuracy.

### 4.3. 📌 Model Usage in This Project

#### 🤖 Chatbot Integration
```python
def query_gemini_model(question, context):
    try:
        if "chat" not in st.session_state:
            st.session_state.chat = model.start_chat(history=[])
        
        response = st.session_state.chat.send_message(f"Context: {context}\nQuestion: {question}")
        st.session_state["chat_history"].append(("User", question))
        st.session_state["chat_history"].append(("Bot", response.text.strip()))
        
        return response.text.strip()
    except Exception as e:
        st.error(f"Error querying Gemini model: {e}")
        return None
```

#### ✍️ Extracting Handwritten Text from Images
```python
from PIL import Image

def extract_handwritten_text(image_path, prompt="Extract text from this image"):
    try:
        image = Image.open(image_path)
        response = model.generate_content([image, prompt])
        return response.text
    except Exception as e:
        print(f"Error extracting text: {e}")
        return None
```

#### 🖼️ Preparing Images for Analysis
```python
def prep_image(image_path):
    try:
        sample_file = genai.upload_file(path=image_path, display_name="Diagram")
        return sample_file
    except Exception as e:
        print(f"Error preparing image: {e}")
        return None
```

---

## 5. How the API Works in the Project (Process Flow)

1️⃣ **User Inputs Query or Uploads File**:
   - The user asks a chatbot question or uploads an image.

2️⃣ **Data Processing**:
   - If **text query** → `model.start_chat().send_message(question)` processes it.
   - If **image** → Uploaded via `genai.upload_file(path=image_path)`, processed with `model.generate_content([image, prompt])`.

3️⃣ **API Call to Gemini 1.5 Pro**:
   - The model analyzes the request and generates a response.
   - **Chat history is maintained** for context-aware interactions.

4️⃣ **Response Output**:
   - Extracted text, chatbot responses, or speech transcriptions are displayed in the UI.

---

## 6. Conclusion

Gemini 1.5 Pro API is a powerful AI model for text, image, and multimodal processing. It is chosen over GPT-4, Claude 3, and Mistral due to its longer context processing, better multimodal support, and faster performance. By integrating this model, your project enhances AI-driven interactions, text extraction, and chatbot efficiency.


