# chatbot.py

import nltk
from nltk.chat.util import Chat, reflections

# Define chatbot patterns
pairs = [
    [
        r"hi|hello|hey",
        ["Hello! How can I assist you today?"]
    ],
    [
        r"(.*)(help|support)(.*)",
        ["Sure, I'm here to help. Please describe your issue."]
    ],
    [
        r"(.*)(product|item)(.*)not working(.*)",
        ["I'm sorry to hear that. Can you try restarting the device?"]
    ],
    [
        r"(.*)(refund|return)(.*)",
        ["Please provide your order ID to initiate a refund or return."]
    ],
    [
        r"(.*)(thank you|thanks)(.*)",
        ["You're welcome! Have a great day!"]
    ],
    [
        r"quit",
        ["Goodbye! Have a nice day."]
    ]
]

# Create chatbot
def start_chatbot():
    print("Customer Service Chatbot\nType 'quit' to exit.")
    chat = Chat(pairs, reflections)
    chat.converse()

# Run chatbot
if __name__ == "__main__":
    nltk.download('punkt')  # Download required resources
    start_chatbot()
