# 🧠 LangChain Output Parsing Examples

This repository demonstrates various **output parsing techniques** using **LangChain** with both **HuggingFace** and **OpenAI** models.  
It includes examples of how to process text inputs (like topics on *black holes* or *fictional persons*) and structure outputs using parsers such as **JSON**, **Pydantic**, **Structured**, and **String Output Parsers**.

---

## 📂 Project Structure

| File | Description |
|------|--------------|
| **`jsonoutputparser.py`** | Uses `JsonOutputParser` with a HuggingFace model (`Gemma-2-2B`) to generate 5 facts about a topic (e.g., *black holes*) in JSON format. |
| **`pydanticoutputparser.py`** | Uses `PydanticOutputParser` with a Pydantic `Person` model (`name`, `age`, `city`) to generate structured data for a fictional person (e.g., from *Sri Lanka*). |
| **`stroutputparser.py`** | Chains two prompts using HuggingFace: first generates a detailed report on a topic, then summarizes it in **5 lines**. |
| **`stroutputparser1.py`** | Similar to `stroutputparser.py` but uses an **OpenAI model (`ChatOpenAI`)** for report and summary generation. |
| **`structuredoutputparser.py`** | Uses `StructuredOutputParser` with a custom schema to generate 3 structured facts about a topic using HuggingFace. |

---

## ⚙️ Prerequisites

- **Python 3.8+**

### 🧩 Install Dependencies
```bash
pip install langchain langchain-openai langchain-huggingface langchain-core python-dotenv
