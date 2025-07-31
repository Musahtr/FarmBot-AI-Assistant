 FarmBot: An AI-Powered Conversational Assistant for Smart Crop Management (Dialogflow Edition)

 💡 Problem Statement
Smallholder farmers often struggle with timely access to accurate information on crop production, including disease identification, optimal planting times, nutrient management, and quality assurance. This leads to reduced yields and post-harvest losses. FarmBot aims to bridge this knowledge gap by providing an intelligent, interactive chatbot.

 🚀 Our Solution: FarmBot with Google Dialogflow
FarmBot leverages Google Dialogflow's powerful Natural Language Understanding (NLU) and dialogue management capabilities, combined with a custom Python fulfillment webhook. This architecture allows for robust conversational AI without complex local setup, making it ideal for rapid development and deployment.

 ✨ Key Features
 Disease & Pest Identification: Farmers can describe symptoms to get insights into potential crop diseases and pests.
 Planting Advice: Provides guidance on optimal planting seasons and methods for various crops.
 Fertilizer & Nutrient Management: Offers recommendations for appropriate fertilizers and helps diagnose nutrient deficiencies.
 Quality Assurance Tips: Advises on post-harvest handling and storage to minimize spoilage and improve market value.
 Conversational & User-Friendly: Designed to understand natural language queries and provide relevant, dynamic responses.

 🛠️ Technology Stack
 Google Dialogflow: For Intent Recognition, Entity Extraction, and Dialogue Management.
 Python (Flask): For the custom fulfillment webhook that contains the agricultural knowledge base and business logic.
 Ngrok: To expose the local Colab Flask server to Dialogflow's cloud webhook.

 📂 Project Structure
This project is primarily configured within the Google Dialogflow console, with the custom logic implemented in a Python script.

 Dialogflow Agent: Configured in the Dialogflow web console (Intents, Entities, Fulfillment settings).
 `
     Includes the in-memory `FARMING_KNOWLEDGE_BASE`.
     Uses `pyngrok` to create a public URL for the webhook.
 `requirements.txt`: Lists all Python dependencies.

 ⚙️ How to Run Locally (on Google Colab)

1.  Google Dialogflow Setup:
     Go to [https://dialogflow.cloud.google.com/](https://dialogflow.cloud.google.com/) and create a new agent named `FarmBot`.
     Follow the instructions in the "Phase 1: Google Dialogflow Agent Setup" section above to create the necessary intents (`Goodbye`, `ThankYou`, `AskDiseaseSymptom`, `AskPlantingAdvice`, `AskFertilizerAdvice`, `AskQualityAssurance`) and configure their training phrases, parameters (making `crop_type` and other relevant entities "Required" with prompts), and enable Webhook fulfillment for `AskDiseaseSymptom`, `AskPlantingAdvice`, `AskFertilizerAdvice`, and `AskQualityAssurance`.
     Go to Fulfillment on the left sidebar and ensure Webhook is enabled.

2.  Google Colab Setup:
     Open your `FarmBot_Fulfillment_Colab.ipynb` notebook in Google Colab.
     Replace `"YOUR_NGROK_AUTH_TOKEN"` in the Python code with your actual ngrok authentication token (get it from [https://ngrok.com/signup](https://ngrok.com/signup)).
     Run the Colab cell containing the Python Flask application. It will install dependencies and print an `Ngrok tunnel URL`.
     Copy this `https://` URL.

3.  Connect Dialogflow to Colab:
     Go back to the Dialogflow console > Fulfillment.
     Paste the copied `Ngrok tunnel URL` into the "URL" field under the Webhook section.
     Click "Save".

4.  Test Your FarmBot:
     Use the "Try it now" panel on the right side of the Dialogflow console to interact with your bot.
     Example queries:
         `Hello`
         `My maize leaves are yellowing.`
         `When should I plant rice?`
         `What fertilizer for cassava?`
         `How do I store yam after harvest?`

 📈 Future Enhancements (Hackathon Stretch Goals / Next Steps)
 Expand Knowledge Base: Add more crops, diseases, pests, and regional farming practices.
 Image Recognition: Integrate image classification (e.g., using TensorFlow Lite or a cloud vision API) for visual disease/pest identification.
 Real-time Data: Connect to external APIs for live weather data, market prices, or soil analysis services.
 Multilingual Support: Leverage Dialogflow's built-in multilingual capabilities to support local Nigerian languages.
 User Interface: Build a simple web-based chat interface (e.g., using HTML/CSS/JS or a framework like Streamlit) that connects to Dialogflow.

 🤝 Contribution
Contributions are welcome! If you have ideas for improving FarmBot, please feel free to open an issue or submit a pull request.

 📄 License
This project is licensed under the MIT License.
