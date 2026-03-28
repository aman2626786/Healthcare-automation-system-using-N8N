# Healthcare Chatbot – Swasthya Sampark 

## 📌 Overview
This project implements an **AI-powered healthcare chatbot** named **Jaya**, designed for **Swasthya Sampark: healthcare management system**.  
The chatbot provides empathetic, safe, and action-oriented support to users, helping them feel heard, calmer, and more capable in the moment.  

<img width="1501" height="593" alt="Screenshot 2026-03-28 224152" src="https://github.com/user-attachments/assets/a3a84205-5a0d-4c8a-b2cb-b455939e027a" />

It integrates with **n8n workflow automation** to handle:
- User input via webhook
- AI-driven responses using Google Gemini
- Memory context for personalized conversations
- Conditional logic for hospital searches
- External API calls for location-based hospital data
- Safe and supportive guidance following strict mental health safety rules


## ⚙️ Workflow Components
The automation is built in **n8n** and consists of the following nodes:

1. **Webhook**  
   - Entry point for user messages (`POST` requests).

2. **AI Agent (LangChain)**  
   - Powered by Google Gemini Chat Model.  
   - Uses memory (`Simple Memory v2`) and tools (`SerpAPI`) for contextual responses.  
   - System prompt defines Jaya’s empathetic personality, mission, and safety rules.

3. **Google Gemini Chat Model**  
   - Generates conversational responses with warmth and clarity.

4. **Simple Memory**  
   - Maintains session context (`sessionKey: ******`) for personalized replies.

5. **SerpAPI (Google Search)**  
   - Provides real-time facts, helplines, and region-specific guidance.

6. **Conditional Logic (If / If1)**  
   - Detects intent (e.g., `hospital_search`).  
   - Checks if location data is available.

7. **HTTP Request (Overpass API)**  
   - Fetches nearby hospitals using OpenStreetMap data.

8. **Respond to Webhook**  
   - Returns the final chatbot response to the user.

---

## 🛡️ Safety Rules
- **No diagnosis or prescriptions**  
- **Not a replacement for a therapist/doctor**  
- Crisis handling:  
  - Respond with urgent empathy  
  - Encourage immediate human help  
  - Provide helpline numbers (US/Canada: 988, India: Tele-MANAS 14416 / 1-800-891-4416)  
  - Suggest contacting trusted persons immediately  

---

## 🖥️ Features
- Warm, concise, empathetic responses (4–8 lines)  
- Hinglish support (Roman script) for accessibility  
- Emotion validation + practical micro-plans  

---

## 🚀 How It Works
1. User sends a message → **Webhook** receives input.  
2. **AI Agent** processes message with memory + Gemini model.  
3. If intent = `hospital_search`, workflow checks location:  
   - If location available → **HTTP Request** fetches hospitals.  
   - If not → fallback response.  
4. Final supportive reply returned via **Respond to Webhook**.  

---

## 📂 File Info
- **File Name:** `Healthcare Chatbot.json`  
- **Platform:** n8n Workflow Automation  
- **Status:** Active  

---

## 🔮 Future Enhancements
- Expand hospital search to multiple regions dynamically  
- Add emotion-based branching for tailored exercises  
- Integrate with external wellness APIs for richer guidance  
- Enhance dashboard with progress tracking and personalized recommendations  

---

## 🧑‍💻 Author
Developed by **Aman Sharma**  
Focused on **democratizing technical education** and building **accessible healthcare automation systems** using AI + workflow automation.
