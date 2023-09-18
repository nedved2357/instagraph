Note for non-coders: you can sign up for the waitlist at [instagraph.ai](https://instagraph.ai).

# InstaGraph 🌐

Hello there, adventurous coder! Welcome to InstaGraph, your go-to application for converting text or URLs into insightful knowledge graphs. Curious about the relationships between entities in a complex topic? Feed the text to InstaGraph and voila! A beautiful knowledge graph is at your fingertips.

See example flowcharts generated by InstaGraph [here](https://twitter.com/yoheinakajima/status/1701351068817301922).

Powered by OpenAI's GPT-3.5, this Flask application turns your text into a vividly colored graph, making it easier to visualize relationships between various entities. Enough talking—let's get started!

***Author's TL;DR**: If you're just looking for how the knowledge graph is generated, check out the function call parameters taking up half of main.py.*

## Table of Contents 📚

- [Features](#features-)
- [Installation](#installation-%EF%B8%8F)
- [Usage](#usage-)
- [Contributing](#contributing-)
- [License](#license-)

## Features 🌟

- Dynamic Text to Graph conversion.
- Color-coded graph nodes and edges.
- Responsive design—use it on any device.
- Super-duper user-friendly!

## Installation 🛠️

To get started, you'll need Python and pip installed.

#### 1. Clone the repository

```bash
git clone https://github.com/yoheinakajima/instagraph.git
```

#### 2. Navigate to the project directory

```bash
cd instagraph
```

#### 3. Install the required Python packages

```bash
pip install -r requirements.txt
```

#### 4. Set up your OpenAI API Key

Change .env.example to .env

```text
mv .env.example .env
```

Add your OpenAI API key to .env file:

```text
OPENAI_API_KEY=your-api-key-here
```

##### Optional

Add Neo4J username, password and URL in the `*.env` file as well.

```text
NEO4J_USERNAME=
NEO4J_PASSWORD=
NEO4J_URL=
```

#### 5. Run the Flask app

```bash
python main.py
```

   Navigate to `http://localhost:8080` to see your app running.

## Run as Container 
#### 1. Clone the repository
```bash
git clone https://github.com/yoheinakajima/instagraph.git
```
#### 2. Navigate to the project docker directory
```bash
cd instagraph/docker
```

#### 3.1 Run in Dev mode 

```bash
docker-compose -f docker-compose-dev.yml up # Add -d flag at the end to run in background/daemon mode.
```
#### 3.2 Run in Prod - Create the docker image

- Using the `gunicorn==21.2.0` to run the application in production mode

```bash
docker-compose -f docker-compose.yml up --build -d
```

## Usage 🎉

### Web Interface

- Open your web browser and navigate to `http://localhost:8080`.
- Type your text or paste a URL in the input box.
- Click "Submit" and wait for the magic to happen!

### API Endpoints

1. **GET Response Data**: `/get_response_data`

    - Method: `POST`
    - Data Params: `{"user_input": "Your text here"}`
    - Response: GPT-3.5 processed data

2. **GET Graph Data**: `/get_graph_data`

    - Method: `POST`
    - Response: Graph Data

3. **GET History Data**: `/get_graph_history`

    - Method: `GET`
    - Response: Graph Data

## Contributing 🤝

Best way to chat with me is on Twitter at [@yoheinakajima](https://twitter.com/yoheinakajima). I usually only code on the weekends or at night, and in pretty small chunks. I have lots ideas on what I want to add here, but obviously this would move faster with everyone. Not sure I can manage Github well given my time constraints, so please reach out if you want to help me run the Github. Now, here are a few ideas on what I think we should add based on comments...
- ~~Store knowlege graph~~ (thx [@tomasonjo](https://github.com/tomasonjo)! 9/13/23)
- ~~Pull knowledge graph from storage~~ (thx [@tomasonjo](https://github.com/tomasonjo)! 9/13/23)
- Show history
- Ability to combine two graphs
- Ability to combine 2+ graphs from history
- ~~Ability to expand on a graph~~ (thx [@tomasonjo](https://github.com/tomasonjo)! 9/13/23)
- Ability to expand on graph from specific nodes
- Fuzzy matching of nodes for combining graphs (vector match + LLM confirmation)

There are a lot of "build a chart" tools out there, so instead of doing user account and custom charts, it sounds more fun for me to work on building the largest knowledge graph ever...

Before creating an Issue please refer the [ISSUE_TEMPLATE](https://github.com/yoheinakajima/instagraph/tree/main/.github/ISSUE_TEMPLATE) provided.

## License 📝

MIT License. See [LICENSE](LICENSE) for more information.

---

Enjoy using InstaGraph! 🎉
