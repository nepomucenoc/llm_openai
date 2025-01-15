# Blood Test Data Formatter using OpenAI API

This LLM project utilizes the OpenAI API to process and format blood test data according to specific requirements. By leveraging AI-powered language models, it transforms raw blood test data into a structured and standardized format, making it easier to analyze and interpret.

![image](https://github.com/user-attachments/assets/f1a58c24-e511-4bd6-853a-e5a4d5013ee7)

## Features

- **Data Transformation**: The project uses the OpenAI API to prompt and reformat blood test data into the required structure.
- **Customizable Prompts**: The system allows for customizing the prompts used by the OpenAI API, ensuring flexibility in formatting different types of blood test data.
- **Easy Integration**: You can easily integrate this system into your existing data processing pipeline for automatic data formatting.

## Requirements

- Python 3.x
- OpenAI API key
- Required Python libraries: `openai`, `pandas`, `json`, etc.

## How to Use

1. Install the required libraries by running:

    ```bash
    pip install openai pandas
    ```

2. Set up your OpenAI API key:

    - Obtain your API key from [OpenAI](https://platform.openai.com/signup) and set it in your environment or directly in the script.

3. Prepare your blood test data as a dataset (e.g., CSV or Excel).

4. Use the provided Python script to send the data to the OpenAI API and retrieve the formatted result.

5. Analyze and utilize the transformed data in your research or application.

## Example Usage

```python
import openai
import pandas as pd

openai.api_key = "your-openai-api-key"

# Load your blood test data
data = pd.read_excel("data.xlsx")

# Process and format the data using the OpenAI API
response = openai.Completion.create(
  engine="text-davinci-003",
  prompt="Transform the following blood test data into the required format: " + str(data.head()),
  max_tokens=500
)

print(response.choices[0].text.strip())
