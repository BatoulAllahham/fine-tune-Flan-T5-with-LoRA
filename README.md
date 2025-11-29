# fine-tune-Flan-T5-with-LoRA

This is the final project to fine-tune Flan-T5 with LoRA

Fine Tuning Flan T5 Base Using LoRA for Dialogue Summarization
________________________________________
 Description
This project demonstrates how to fine tune the Flan T5 base model using LoRA (Low Rank Adaptation) to generate summaries from dialogue text.
The project guides you through:
•	Loading and exploring SAMsum dataset
•	Tokenizing inputs and preparing labels
•	Applying PEFT + LoRA to reduce memory and computation cost
•	Training the model using HuggingFace Trainer
•	Evaluating the generated summaries using ROUGE
________________________________________
 Installation
To set up the project locally or in Google Colab:
 Install required libraries
All required packages are installed directly in the notebook through this command:
!pip install transformers datasets peft accelerate sentencepiece
The notebook automatically installs everything needed.
________________________________________
 Usage
To run the project, simply open the notebook:
1. Upload the notebook to Google Colab
•	Go to https://colab.research.google.com/
•	Upload the file Final_Project_last_version.ipynb
2. Run all cells in order
The notebook is divided into logical steps:
1.	Install dependencies → Installs libraries
2.	Import modules → Loads HuggingFace + PEFT
3.	Load dataset → Reads the dialogue + summary data
4.	Tokenization → Prepares the data for training
5.	LoRA configuration → Applies LoRA to Flan T5
6.	Training → Fine tunes the model
7.	Evaluation → Tests summarization quality
8.	Saving the model → Stores LoRA weights
3. Generating your own summaries
After training, you can run:
text = "Your dialogue text here"
inputs = tokenizer(text, return_tensors="pt").to(model.device)
out = model.generate(**inputs, max_length=128)
print(tokenizer.decode(out[0], skip_special_tokens=True))
________________________________________
Project Structure
Final_Project_last_version.ipynb    
README file                   
________________________________________
 Contributing
Contributions are welcome!
Feel free to submit suggestions on improving the training pipeline, dataset cleaning, or evaluation metrics.
________________________________________
License
You are free to use, copy, modify, and distribute it.
________________________________________
 Contact
Maintainer: Batoul Allahham
Email: batoolallahham5@gmail.com
If you have any questions about the project, feel free to reach out!
