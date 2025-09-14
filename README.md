LangChain Output Parsing Examples

This repository demonstrates various output parsing techniques using LangChain with HuggingFace and OpenAI models. The scripts show how to process text inputs (e.g., about black holes or fictional persons) and structure the output using different parsers such as JSON, Pydantic, Structured, and String Output Parsers.

📂 Project Structure

jsonoutputparser.py – Uses JsonOutputParser with a HuggingFace model (Gemma-2-2B) to generate 5 facts about a topic (e.g., black holes) in JSON format.

pydanticoutputparser.py – Uses PydanticOutputParser with a Pydantic Person model (name, age, city) to generate structured data for a fictional person from a place (e.g., Sri Lanka) using HuggingFace.

stroutputparser.py – Chains two prompts with HuggingFace: first generates a detailed report on a topic, then summarizes it in 5 lines.

stroutputparser1.py – Similar to stroutputparser.py but uses an OpenAI model (ChatOpenAI) for report + summary generation.

structuredoutputparser.py – Uses StructuredOutputParser with a custom schema to generate 3 facts about a topic (e.g., black holes) in structured format using HuggingFace.

⚙️ Prerequisites

Python 3.8+

Install dependencies:

pip install langchain langchain-openai langchain-huggingface langchain-core python-dotenv


API Keys (set in .env file):

For HuggingFace (used in most scripts):

HUGGINGFACEHUB_API_TOKEN=your_huggingface_api_token


For OpenAI (used in stroutputparser1.py):

OPENAI_API_KEY=your_openai_api_key

🚀 Usage
1. JSON Output Parser
python jsonoutputparser.py


Output: JSON with 5 facts, e.g.:

{"fact_1": "...", "fact_2": "...", "fact_3": "..."}

2. Pydantic Output Parser
python pydanticoutputparser.py


Output: Pydantic Person model instance, e.g.:

Person(name="Kamal Perera", age=25, city="Colombo")

3. String Output Parser (HuggingFace)
python stroutputparser.py


Output: A 5-line summary of the generated black hole report.

4. String Output Parser (OpenAI)
python stroutputparser1.py


Output: A 5-line summary of the generated black hole report (using OpenAI).

5. Structured Output Parser
python structuredoutputparser.py


Output: A structured dictionary with 3 facts, e.g.:

{"fact_1": "...", "fact_2": "...", "fact_3": "..."}

📝 Notes

Ensure .env contains valid API keys before running scripts.

HuggingFace model google/gemma-2-2b-it may differ in performance vs OpenAI.

The structuredoutputparser.py schema currently defines 3 facts, but it can be extended for more fields.

🔮 Future Improvements

Add error handling for API failures and invalid inputs.

Extend schemas in structuredoutputparser.py and pydanticoutputparser.py for complex data.

Add examples with more topics and models.

Include tests to validate output formats and parser behaviors.
