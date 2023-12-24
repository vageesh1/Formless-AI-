# Formless-AI-
My approach for making a miniature replica of a formless AI is a form that can interact with user and extract information from any string of answers.

## Files
- **(Info Given Or Not Given)**- Checks for the Sentiment of the user's answer, if he has provided the asked information or not.
- **(Named Entity Recognition)**- Does the named entity recognition like name, Date, address, or any Specific Information.
- **(LLM For Convincing)**- Fine-Tuned LLAMAv2 7B 4-bit on synthetically generated data using ChatGPT using PEFT technique and pushed to HuggingFace Hub for Inferencing
- **(Convincing LLM Inference)**- I loaded the model from HuggingFace Hub, made a Langchain out of it, provided the prompt, and then inferred it to see the results.
- **(Chat InterFace)**- The main file combines all these: checking the sentiment, doing the named entity recognition, responding to the user using LLM, and saving the results.

## Data Format
- The data is generated using ChatGPT by providing prompts like some question-answering format dataset in which what questions can a user ask according to the situation, how would any average bot respond to it? It generated about 120 examples like this for all tasks.
- The Data had two columns: User Input and Bot Answer
- The second Data consists of two columns: the user input and the corresponding input provided or not for sentiment analysis.
- Here is a screenshot of the Data Format
  ![Alt Text](https://github.com/vageesh1/Formless-AI-/blob/main/Data%20ScreenShot.png)

## Training 
- I used LLAMAv2 7B 4-bit quantization version for the fine-tuning purposes
- PEFT and TRL were the helper libraries for training of our LLM
- I trained it for 80 epochs, which took around 30 minutes for training, and the lowest loss was recorded for 0.47
- Here is the Model link-![Alt Text](https://huggingface.co/Vageesh1/convincing_LLM)

## Example Usage- 
- Load the ChatInterface File in a Google Colab notebook and set runtime to T4 GPU
- Run all the cells until the final function and provide an empty CSV file to store the final results.
- Here are some screenshots to show the final results.
- Chat Function
  ![Alt Text](https://github.com/vageesh1/Formless-AI-/blob/main/Sample%20Chat%20ScreenShot.png)
- Stored File
  ![Alt Text](https://github.com/vageesh1/Formless-AI-/blob/main/Sample%20Saved%20File%20ScreenShot.png)


**Thanks for Reading**
  

