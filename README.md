# Appointment Booking Agents Vertical Starter Kit

[x] Connect Google Calendar (Replaceable with any Calendar or CRM)
[x] Greet Users and Collect basic Info
[x] Check for Available Time Slots for the Dental Clinic (Can be any Business)
[x] Suggest TimeSlots and Confirm the final One with User
[x] Schedule Booking in Google Calendar
[x] Create a save a Draft Email in Gmail (Replaceable with any Mail Service)
[ ] Change TimeZone from UTC to User Specific.
[ ] Confirmation Call after Booking and Cron Job to schedule 
[ ] Add Voice Modality with providers (Twillio, Vapi, Bland)

## Directory Structure
- All prototyping notebooks are in the prototypes directory.
- All final agents will live in in the src directory.

## Getting Started

### Prerequisites

1. Docker
2. Composio, Google AI Studio and LangSmith API Key
3. Setup following either in composio dashboard or through CLI or Jupyter Notebook.
   - composio add googlecalendar gmail
   - composio triggers enable GMAIL_NEW_GMAIL_MESSAGE

### Local Setup

To get startedfollow these steps:

1. **Clone the repository:**

   ```sh
   git clone https://github.com/...
   cd ...
   ```

2. **Create a `.env` file:**

Copy the `.env.example` file to `.env` and update the environment variables as needed:

```sh
cp .env.example .env
```

3. **Run LangGraph Server:**

#### Using Docker

 - Install Docker Desktop

 - Open Docker Desktop

 - Run Below Command to create Docker Image & also Container up

 ```bash
 docker compose up 
 ```

 Or if we want to run in detach mode ( Background )

 ```bash
 docker compose up -d 
 ```

### Step 03 : Open Langgraph Studio

 - Click Below Link to view your graph

 <a href="https://smith.langchain.com/studio/thread?baseUrl=http%3A%2F%2F127.0.0.1%3A8123">Langgraph Studio URL</a>


### Step 04 : How to reflect your change in container

 - Simply Down Your Container

 ```bash
 docker compose down
 ```

 - Then again up your container

 ```bash
 docker compose up -d
 ```

 - It's changes are outside src directory rebuild the image.
 
### Optional: 

##### A. Run using LangGraph CLI

a. Install uv package manager ```python pip install uv```

b. Create Virtual Environment and activate it 
```python 
uv venv
source .venv/bin/activate
```

c. Install packages in pyproject.toml
```python 
uv run
```

d. Run LangGraph Server
- Ensure you have docker engine running (i.e: Open Docker Desktop)
```python 
uv pip install langgraph-cli
uv run langgraph up
```

If you get any error in `d` step stop all containers, run `docker system prune` and try again.


---------------------------------------------------------------------------------------------




##### B. Change model from OPENAI to GOOGLE GEMINI (OPTIONAL)

 - in `configration.py` file change the below 26 number line:
 

 ```code
  default="openai/gpt-4o",
 ```

 To

 ```code
 default="google_genai/gemini-1.5-flash",
 ```
