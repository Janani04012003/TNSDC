import re
import random

class ReceptionistChatbot:
    def __init__(self):
        self.greetings = ["hello", "hi", "hey", "greetings"]
        self.goodbyes = ["bye", "goodbye", "see you later", "take care"]
        self.appointments = ["schedule an appointment", "book an appointment", "appointment"]
        self.departments = ["sales", "support", "billing"]
        self.responses = {
            "greetings": "Hello! How can I assist you today?",
            "goodbye": "Goodbye! Have a great day.",
            "appointment": "Sure, would you like to schedule an appointment?",
            "department": "Which department would you like to reach? We have Sales, Support, and Billing.",
            "fallback": "I'm sorry, I didn't understand that. Can you please rephrase?"
        }

    def respond_to_input(self, user_input):
        user_input = user_input.lower()
        if any(greeting in user_input for greeting in self.greetings):
            return self.responses["greetings"]
        elif any(bye in user_input for bye in self.goodbyes):
            return self.responses["goodbye"]
        elif any(appointment in user_input for appointment in self.appointments):
            return self.responses["appointment"]
        elif any(department in user_input for department in self.departments):
            return self.responses["department"]
        else:
            return self.responses["fallback"]

# Main function for interacting with the chatbot
def main():
    chatbot = ReceptionistChatbot()
    print("Receptionist: Hello! How can I assist you today? (Type 'bye' to exit)")
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'bye':
            print("Receptionist: Goodbye! Have a great day.")
            break
        response = chatbot.respond_to_input(user_input)
        print("Receptionist:", response)

if __name__ == "__main__":
    main()
Receptionist: Hello! How can I assist you today? (Type 'bye' to exit)
You: hello
Receptionist: Hello! How can I assist you today?
You: bye
Receptionist: Goodbye! Have a great day.
