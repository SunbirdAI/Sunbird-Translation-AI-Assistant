# Sunbird AI Translation Assistant

Sunbird AI Translation Assistant is an interactive tool built using Streamlit that translates text between English and Ugandan languages or between Ugandan languages themselves. The assistant leverages the OpenAI GPT-3.5 model for conversational interactions and Sunbird AI Translation API for performing the actual translations.

<video width="320" height="240" controls>
  <source src="./streamlit-sunbirdai_translator-2024-08-04-18-08-42.webm" type="video/webm">
  Your browser does not support the video tag.
</video>

## Features

- Translate between English and Ugandan languages: Luganda, Runyankole, Acholi, Ateso, and Lugbara.
- Translate from any Ugandan language to English.
- User-friendly, conversational interface.
- Streamlit-based web app for easy deployment and interaction.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/SunbirdAI/Sunbird-Translation-AI-Assistant.git
   cd Sunbird-Translation-AI-Assistant
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up your Streamlit secrets:
   Create a file called `secrets.toml` in the `.streamlit` directory:
   ```toml
   [secrets]
   OPENAI_API_KEY = "your_openai_api_key"
   SB_API_AUTH_TOKEN = "your_sunbird_ai_api_token"
   ```

## Usage

1. Run the Streamlit app:
   ```bash
   streamlit run sunbirdai_translator.py
   ```

2. Open your web browser and navigate to `http://localhost:8501`.

3. Interact with the assistant:
   - Greet the assistant and provide the source language of the text you want to translate.
   - Enter the text you wish to translate.
   - Specify the target language for the translation.
   - Click the "Translate" button to perform the translation.

## Example

Here is an example of how to interact with the assistant:

1. **Greeting**:
   - User: "Hello!"
   - Assistant: "Hi there! How can I help you with translation today?"

2. **Specify Source Language**:
   - User: "The source language is English."

3. **Enter Text to Translate**:
   - User: "Are we going for soccer this evening?"

4. **Specify Target Language**:
   - User: "Translate to Luganda."

5. **Translation**:
   - Click the "Translate" button.
   - The assistant displays: "Translation in process..."
   - Upon completion: "Translation completed from English to Luganda: 'Tugenda kusamba omupiira akawungeezi kano.'"

## Code Explanation

The main components of the application are:

- **API Setup**:
  - `OpenAI` and Sunbird AI API keys are set up using Streamlit secrets.
  
- **Language Codes**:
  - A dictionary that maps language names to their respective codes.

- **Functions**:
  - `get_language()`: Retrieves the language name corresponding to a given code.
  - `extract_dictionary_from_response()`: Extracts the dictionary part from a response string.
  - `translate()`: Sends a translation request to Sunbird AI and returns the translated text.
  - `get_completion_from_messages()`: Interacts with OpenAI to get a response from the assistant.
  - `get_translation_task()`: Creates a JSON summary of the translation request.

- **Streamlit Interface**:
  - Initializes chat history and displays previous messages.
  - Accepts user input and appends it to the chat history.
  - Displays the assistant's response and performs the translation upon clicking the "Translate" button.

## Contributing

Feel free to submit issues or pull requests if you have any improvements or suggestions.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
