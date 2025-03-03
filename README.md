```markdown
# Goraya Health Care Center - Appointment Booking Agents Vertical Starter Kit

Welcome to the **Goraya Health Care Center Appointment Booking System**! This AI-powered appointment booking agent is designed to streamline scheduling for businesses, starting with Goraya Health Care Clinic. Built with **LangGraph**, **Composio**, and **AI Telephony**, this system integrates **Google Calendar** and **Gmail** to manage appointments, send confirmations, and handle outbound phone calls. 

Users can check available time slots, confirm bookings, and receive queue updates via email, call, or message. The system is highly customizable, supporting alternative CRM, mail services, and voice providers like **Twilio** or **Vapi**. It is deployed on **Vercel** and **LangGraph Cloud**, with robust testing via **LangSmith** and **LLM unit tests**.

---

## Tech Stack:
- **Agent Framework**: LangGraph, Composio (Tools Library), Voice Orchestrator (Bland.com)
- **LLMs**: Gemini-2.0-flash-exp 
- **Frontend**: NextJS 15
- **Deployment**: Vercel, LangGraph Cloud
- **Testing**: LangSmith, LLM Unit Tests
- **Development**: VS Code/Cursor, Google Colab, Docker
- **Version Control**: [GitHub Repository](https://github.com/goraya2005/appointments_agent) (Active development in live Agentic AI sessions)
- **CRM/Calendar**: Google Calendar, Gmail

---

## User Story
1. **User Wants to Book an Appointment**:
   - Share available time slots (e.g., Monday 09-06 PM).
   - User specifies preferred time (e.g., 4 PM on a specific date).
   - User inquires about wait time and queue number.
   - User receives booking confirmation via email or phone call.

---

## Features

### Completed:
- [x] Connect Google Calendar (Replaceable with any Calendar or CRM)
- [x] Greet Users and Collect Basic Info
- [x] Check for Available Time Slots for Goraya Health Care Clinic (Can be adapted for any business)
- [x] Suggest Time Slots and Confirm the Final One with the User
- [x] Schedule Booking in Google Calendar
- [x] Create and Save a Draft Email in Gmail (Replaceable with any Mail Service)
- [x] Confirmation Call after Booking Appointment using Bland API (Replaceable with any provider)

### In Progress:
- [ ] Cron Job to Schedule Calls
- [ ] Change TimeZone from UTC to User-Specific
- [ ] Add Voice Modality with Providers (Twilio, Vapi, Bland)

### Pending User Stories:
- [ ] Business Active Hours
- [ ] Queue Number and Wait Time Flow
- [ ] Handle Invalid Emails or Failed Calls (Retry Logic)

---

## Directory Structure

- **Prototyping**: All prototyping notebooks are in the `prototypes` directory.
- **Final Agents**: All final agents live in the `src` directory.

---

## Getting Started

### Prerequisites

1. **Docker**: Install Docker Desktop from [here](https://www.docker.com/products/docker-desktop).
2. **API Keys**:
   - Obtain API keys for **Composio**, **Google AI Studio**, and **LangSmith**.
3. **Set Up Tools**:
   - Use the Composio dashboard or CLI to enable Google Calendar and Gmail:
     ```bash
     composio add googlecalendar gmail
     composio triggers enable GMAIL_NEW_GMAIL_MESSAGE
     ```

---

## Local Setup on Windows with VS Code

### Step 1: Clone the Repository
1. Open **VS Code**.
2. Open the terminal (`Ctrl + ``) and run:
   ```bash
   git clone https://github.com/goraya2005/appointments_agent.git
   cd appointments_agent
   ```

### Step 2: Set Up the Environment
1. Create a virtual environment:
   ```bash
   python -m venv venv
   ```
2. Activate the virtual environment:
   ```bash
   venv\Scripts\activate
   ```
3. Create a `.env` file:
   ```bash
   touch .env
   ```
4. Copy the example environment file:
   ```bash
   cp .env.example .env
   ```
5. Update the `.env` file with your API keys and configurations.

### Step 3: Run LangGraph Server with Docker
1. Open **Docker Desktop**.
2. In the terminal, start the Docker container:
   ```bash
   docker compose up
   ```
3. To run in detached mode:
   ```bash
   docker compose up -d
   ```

### Step 4: Access LangGraph Studio
1. Open your browser and navigate to:
   ```
   http://127.0.0.1:8123
   ```

---

## Development Workflow

### Applying Changes
1. Stop the container:
   ```bash
   docker compose down
   ```
2. Restart the container:
   ```bash
   docker compose up -d
   ```
   **Note**: Changes outside the `src` directory require rebuilding the Docker image.

---

## Alternative Setup Methods

### A. Using LangGraph CLI
1. Install the `uv` package manager:
   ```bash
   pip install uv
   ```
2. Create and activate a virtual environment:
   ```bash
   uv venv
   source .venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   uv pip install -r requirements.txt
   ```
4. Run the LangGraph server:
   ```bash
   langgraph up
   ```

### B. Using Google Gemini Instead of OpenAI
To switch models, update line 26 in `configuration.py`:
```python
# From:
default="openai/gpt-4o"
# To:
default="google_genai/gemini-1.5-flash"
```

---

## Contributing
We welcome contributions! Please follow these steps:
1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Submit a pull request with a detailed description of your changes.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contact
For questions or support, please contact the maintainers:
- **Email**: [goraya.tahir@outlook.com](mailto:goraya2005@gmail.com)
- **GitHub**: [goraya2005](https://github.com/goraya2005)

---

Thank you for using the **Goraya Health Care Center Appointment Booking System**! Let’s build something amazing together. 😊
``` 