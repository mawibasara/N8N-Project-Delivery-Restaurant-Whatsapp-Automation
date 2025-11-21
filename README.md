# N8N-Project-Delivery-Restaurant-Whatsapp-Automation
This workflow automates restaurant chat by using an AI agent to read customer messages, check inventory and FAQs from Google Sheets, and record orders automatically. It provides smart replies, real-time stock info, and saves each order directly into the Orders sheet.
Restaurant Automation Workflow – Complete Explanation (In My Words)

This workflow is a Restaurant WhatsApp Automation System that I created to automatically handle customer messages, answer FAQs, check inventory, and even record orders in Google Sheets. I will explain everything step by step so it’s very clear how the workflow works and what each part does.

✅ 1. “When Chat Message Received” (Chat Trigger)

This is the very first node of my workflow.
Whenever a customer sends a message on WhatsApp (or any connected chat platform), this node immediately detects it and triggers the whole workflow.

So basically:

A customer sends a message

This node receives it

And it passes the message to my AI Agent

This is what starts the automation.

✅ 2. AI Agent (The Brain of the System)

After the message is received, it goes straight into my AI Agent.
This agent is the actual “brain” of the entire system.

The AI Agent can:

Understand what the customer wants

Decide if it needs to check inventory

Decide if it should answer an FAQ

Decide if the customer is placing an order

And then choose the correct tool to perform the action

This is the central logic of the automation.

✅ 3. Google Gemini Chat Model (The Thinking Power)

My AI Agent uses the Google Gemini Chat Model to actually think and understand conversations.

This model:

Processes customer messages

Generates natural replies

Understands context

Helps the AI decide which tool to use

Makes it possible to have a realistic chat experience

So the AI Agent is the “brain,” and Gemini is the “thinking engine” powering it.

✅ 4. Simple Memory (Conversation Memory)

This node gives the AI the ability to remember the last few messages.
I set the context window to store recent chat history.

This is important because:

If a customer says:
“Do you have biryani?”
and then
“Okay I want 2.”

The memory helps the AI understand that “2” means 2 biryanis.

This makes conversations smooth and natural.

✅ 5. Get Inventory (Google Sheets Tool)

This node connects to my Inventory sheet in Google Sheets.

Whenever the AI needs to check if an item is available or in stock, it uses this node.

For example:

Customer asks: “Do you have pizza?”

The AI calls this tool

The tool fetches data from Google Sheets

The AI replies based on the latest inventory

This ensures the AI always gives real-time and accurate information.

✅ 6. Get FAQs (Google Sheets Tool)

This node connects to my FAQs sheet in Google Sheets.

Whenever the customer asks something like:

“What are your timings?”

“Do you deliver?”

“What are your charges?”

The AI fetches the answer from this sheet.

So instead of hardcoding responses, I just update the FAQ sheet and the AI uses the latest information.

✅ 7. Append Row in Google Sheets (Order Recorder)

This is one of the most important nodes.

Whenever a customer places an order, the AI extracts the necessary details:

Customer name

Food item

Quantity

Status

And then this node automatically adds a new row to the Orders sheet in Google Sheets.

For example, if someone orders:

“My name is Ali, I want 1 Chicken Karahi.”

The AI fills in:

Customer Name: Ali

Food Item: Chicken Karahi

Quantity: 1

Status: Pending

And this node writes it into the Orders sheet.

This makes the whole order-taking process fully automated.

✅ 8. How All Nodes Work Together (Flow Summary)

Here’s the complete flow in simple terms:

Customer sends a message

Chat Trigger activates the workflow

The message goes to the AI Agent

AI Agent uses Google Gemini to think and decide what to do

AI uses Memory to keep context

If customer asks about items → AI checks Inventory Sheet

If customer asks a general question → AI checks FAQs sheet

If customer places an order → AI uses “Append Row” to save it in the Orders sheet

AI replies back to the customer

Everything happens automatically without any manual work.

⭐ Complete Use-Case (Real-Life Scenario)

Here is an example of how my automation works with a real customer:

Customer:

“Do you have Zinger burger?”

AI:

Checks Inventory sheet → sees availability → replies:
“Yes, Zinger burger is available.”

Customer:

“Okay I want 2 and my name is Hamza.”

AI:

Extracts order details
→ Customer: Hamza
→ Item: Zinger Burger
→ Quantity: 2
→ Status: Pending

Then AI uses “Append Row” node to save this order in Google Sheets.

AI replies:
“Your order for 2 Zinger Burgers has been placed, Hamza!”

Customer:

“What are your opening hours?”

AI:

Reads FAQs sheet → replies with correct timing.

🎯 Final Summary (In One Line)

This workflow is a complete automated restaurant assistant that can chat with customers, answer FAQs, check inventory, and take orders — all using AI and Google Sheets.
