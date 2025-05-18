Gen AI Notes:
Day1:
1.Key concepts in AI and ML

AI -> 
Machine - small set of data 
What is Machine Learning (ML) ?
Machine Learning (ML) is a subset of artificial intelligence that enables systems to learn from
data, identify patterns, and make decisions without explicit programming.

deep learning with volume of data
1) What is the difference between LLM and Generative AI?
- LLM is a type of generative AI that focuses on text-based content generation.
- Generative AI encompasses a broader range of content types, including images, audio, and video.
- LLMs are specifically designed for natural language processing tasks, while generative AI can include various modalities.   

Data:

x -- > number of columns -- > parameters (AI)
-- > records (AI)

y -- > number of rows

Deep Learning Models

OpenAI (Chatgpt) / Meta (Llama) / Google (Gemini) / DeepSeek (r1) / Alibaba (qwen) / AWS (BedRock)

Generate 400 scripts for Onboarding customers to a bank

Estimation: 400 x 4 -- > 1600 hours (5) == > 1600/40 == > 40 days == > 2 months

LLM + Fine tuning (Supervised + RLHF) : Generate 400 scripts in less than 2 days (less than 50 USD) -- > 70% accuracy

2 people -- > in less than 2-3 weeks

Salesforce + ServiceNow :: Agentic AI

Generate code + fix the code + test the code + deploy code

Automation code fail reasons:
----------------------------------------------------------------------------------

Day 2:
What is Generative Al?

Generative Al refers to a class of artificial intelligence systems that can create new content,
such as images, text, videos, or other data, by learning from existing datasets.

chatgpt 
deepseek
qwen

Write testcases for corporate banking login functions

----
Token

1. Input (Text / Image / Video)

1 Token = 1 Word

2. Why do I need a token?

1. Context Window - How much I can take as input?

a. 3.5 -- > 4096
b. 4.x -- > 8000+

Process it >> I need large number of GPU

2. Cost -

Cloud based Models

Input tokens per million
Output tokens per million
--------------------
Would I need worry about tokens when I use opensource models like deepseek when deployed within my org?

- Cost (No) only for API + There is cost for hardware (~ 10000+ USD) + Cloud based usage
- Each Model has restrictions for context window (process well)


--------------------------------------------------------------------------
Day3:
Go to google.com
Type testleaf
Click on the first link

Natural Language >> LLM (API) >> Launch >> Read the DOM >> Text -- > Element (Index) -- > Interaction

1) Tokens -- > Per Step 0.05 USD -- > 4.2 INR
1) OpenAI - Pay per usage
2) Llama - Opensource
3) DeepSeek - Opensource
4) Bedrock - Pay per usage

Cloud LLM (Unlimited)

# groq.com >> You can use them through API
You will not able to fine tune them

Do not put personal information !!

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

2 or 3 models preferred 

1_ llama-3.3-70b-versatile
2_ deepseek-r1-distill-llama-70b
3_ deepseek-r1-distill-qwen-32b

----------
1) Chat using API

Request Body - json !!

role : user, assistant, system !!

system - Standard common message (given once for the entire conversation) - Background or context

system - You are AI assistant to generate selenium code in Java from DOM
assistant -- What are you expecting the AI assistant to provide you back (Output)
user - The input prompt that you wanted to provide the AI (Input)


Day 4:
- Build Applications (connect using API)
- Hyper Parameters (Only available in the API)
- No Memory (Stateless)

Models

Using groq

- llama (chat)
- deepseek (chat)
- qwen (chat)
- llama vision (vision)
- whisper (text to audio)
- llamaguard (moderation)

These models are deployed in the groq cloud and they provide you access (api keys)

Adv: No cost
Limitations:
- Rate Limit

2) Setup your servers and deploy the opensource models

- GPU vs CPU
- Ollama server
- Security

Advantages

- You can deploy within your own network
- No worries about data security

Setting Ollama

- CPU (Azure Cloud)
- 32 GB RAM + 16 Core CPU
- Server (Linux)

- Setup llama or deepseek or qwen

Ollama Setup

Step 1) curl -fsSL https://ollama.com/install.sh | sh
Step 2) ollama -- version
Step 3) ollama pull qwen2.5:0.5b
Step 4) ollama run qwen2.5:0.5b

curl http://localhost:11434/api/generate -H "Content-Type: application/json" -d '{
"model": "qwen2.5:3b",
"prompt": "Write a Selenium Java code to open Google and search for \"Testleaf\"",

"stream": false - entire content will come response is not fast ,set true


- Is there a token cost to my ollama server ? No !!
- What is the cost I need to pay? Azure Server

I like to ask my leadership team to setup a LLM Server for me?

- What LLM are they using?
- Which models are been used? Is there any specific guidelines?
- Proof of Cost : Advantages -- > Cost benefits + People + Timelines

1) Existing Cloud Server they have LLM deployed
2) OpenAI Cloud with Azure
(pAY)

3) On demand Azure GPU


Function:

- Does all the text models can support real-time information? No !

shots means example to training a model

_____________________________________________________________________________________
Day 5:
ICED To Framework for Prompting

Instructions    - Mandatory
Context         - Good to Have
Examples        - Good to Have
Desired Output  - Nice to Have
Tone            - Nice to Have
Output Format   - Nice to Have
Persona         - Good to Have (provide what is your role or what you are doing)

Use Emotional 


instrucitons:
Keywords

- [Important]
- [Note]
- [Mandatory]
- [CRITICAL]
- [DO NOT USE THE FOLLOWING TYPE OF XPATH : ]
- [NEVER]

80 - 90%
>Iterations

Multi Task Instructions

- Use bullets or -
- Intent
- Use Step numbers
- Order Matters
- [Exception]

Context/Background:
Context:
Tip 1: You will have to build your prompt from the prompt [unless you need tell what framework to use]
Tip 2: Never settle with 1 LLM for building prompt
Tip 3: Use the same chat for coninuous conversation[can avoid the context to set again]
Tip 4: You will never the perfect prompt in the first go [you will have to iterate]
Tip 5: Always remember build your project or framework 


[Turn any Git repository into a simple text digest of its codebase.

This is useful for feeding a codebase into any LLM.](https://gitingest.com/)


1) API guarded !!
2) DOM (publically available)
3) DOM (eliminate the data part) + Send the data to the LLM
4) private LLM(Locally installed)


### **1. ICED-T (Iteration, Context, Examples, Detail, Testing)**
   - **Iteration**: Refine prompts through multiple versions.  
   - **Context**: Provide background to guide the AI.  
   - **Examples**: Include sample inputs/outputs.  
   - **Detail**: Be specific about requirements.  
   - **Testing**: Evaluate prompt effectiveness.  
   - **Best for**: General-purpose prompt engineering, refining prompts over time.

### **2. ICE-POT (Instruction, Context, Examples, Purpose, Outcome, Testing)**
   - **Instruction**: Clear directive for the AI.  
   - **Context**: Background info for better understanding.  
   - **Examples**: Demonstrations of desired output.  
   - **Purpose**: Why the prompt is being used.  
   - **Outcome**: Expected format/content of the response.  
   - **Testing**: Validate prompt effectiveness.  
   - **Best for**: Highly structured, outcome-focused prompts (e.g., technical or business use cases).

### **Key Differences**
| Feature       | ICED-T          | ICE-POT         |
|--------------|----------------|----------------|
| **Focus**    | Iterative refinement | Precise instruction & outcome |
| **Structure**| General improvement | Goal-oriented |
| **Best Use** | Broad applications | Specific, high-stakes tasks |

### **Which is Best?**
- **Use ICED-T** if you want a flexible, iterative approach (e.g., creative writing, brainstorming).  
- **Use ICE-POT** if you need strict control over outputs (e.g., coding, data analysis, business reports).  

Tone - is not good fit for coding.
---------------------------------------------------------------------------------------------------------------
Day 7:

Today's Agenda

- Recap [API, Prompt Engineering]
- Build Apps using LLM API
- Browser Extension
- Objective: Convert the DOM to Selenium / Playwright for different language
- Assignments (Breaking into sub groups)

- Limitations: Da

End point: https://api.groq.com/openai/v1/chat/completions
- You got multiple LLM at one space
- You also get FREE tier for basic activities
- Data Privacy, No fine tuning

End point: https://api. openai.com/v1/chat/completions
- You got multiple models
- Limitations: Cost

End point: https://api.ollama.com/llama/v1/chat/completions
- You got multiple LLM and models
- Limitations: Hardware cost

"model": "llama-3.3-70b-versatile",
"messages": [
{
"role": "user",
"content": "<prompt here>",
"temparture": 0.2,
"max_tokens": 1500,
"top_p": 0.95
}]

Build a Solution:

- Research the problem :

- UI Test Automation is challenging
- It takes lot of effort a build a test script
- It is quite flaky
- Requiring lot of exception handling, data, sleep/wait
- It is not easy to maintain
- Not great skilled resources available
- coverage is not great

Question: Can we use GenAI to generate scripts for us ? Yes !
- Build a solution using GenAI
- Use GenAI to generate test scripts
- Use GenAI to generate data
- Use GenAI to generate exception handling
- Use GenAI to generate wait/sleep
- I am okay even if it is 70% accurate
- I can fix the rest of the 30% manually

- How do we build the solution?
- What should be my architecture?
- What should be my tech stack?
- How do we build the solution?
- What should be my architecture?
- What should be my tech stack?
- Inputs: DOM elements, test case, test data
- Outputs: test script
- Where do I get the DOM elements? From the application under test (AUT).
- How do I send the DOM to GenAI?
- Use a REST API
- Do I really a send the entire DOM ? That may be huge?

Steps to install ext:
1) Download the zip (ai-extensions. zip) and extract
- ignore MacOS content
- You will see the assets, panel.html etc

2) Open the chrome browser, type this on the URL >>> chrome://extensions/

3) Enable the developer mode (top right corner)

4) Click on "Load unpacked" button

5) Select the folder where you extracted the zip file (ai-extensions)

6) You will see the extension

7) Click on the extension icon (top right corner of the browser) and pin

8) after entering close and open ext , do same for any error


Week 4 Day 7:
Today's Agenda

- Another Usecase : Swagger document -- > RestAssured Code + TestNG
- Tech Stack + Code (ReactJs + NodeJs / Springboot)
- Practice: Another usecase

API Testing

Endpoint : https://<Server> :< port>/<resources>/

- Requirement :

- API Specification should looks like
- Resources end point
- Method : POST / GET / PUT / PATCH / DELETE ..
- Request Headers (Authorization, Content-type ... )
- Request Payload (POST / PUT / PATCH)
- Request Parameters (GET)
- Response Payload
- Response Headers
- Response : Status Desc, Status Code, Time ...

- Standard for both dew & test

Output Requirement:

- RestAssured Code for every API call
- Should be inclusing TestNG code using annotations
- Should compile and run
- [LATER] : Feature file (Cucumber) + Step Definitions + POJO Classes

Estimated Times & Cost:

- Convert Swagger API -- > RestAssured Code -- > 60 minutes !!
- 400+ API that need to be converted
- Efforts: 400 x 1 hr == 400 hours
- Hourly rate : 25 USD per hour = 400 x 25 = 10000 USD\
- This is development cost

Agreed to build this solution using LLM API (Llama) just using Prompts.

Tech Stack :

- Is Browser extension good idea? No !! (We are not dealing with Browser information)
- Whom are we building this for? Manual tester / Automation Engineer / Business Analyst
- Do you need UI layer? yes (upload or choose the swagger file)
- What functions you like to have ???
- Upload swagger file
- Generate test scripts
- Run the tests
- Generate test case execution report

why shouldnt we upgrade the browser extension with file upload(API) functionality and generate code with the extension? I

- What functions you like to have ???
- Upload swagger file
- Generate test scripts
- Run the tests
- Generate test case execution report
Tech Stack :

    - Is Browser extension good idea? No !! (We are not dealing with Browser / web apps information)
    - Whom are we building this for? Manual tester / Automation Engineer / Business Analyst
    - Do you need UI layer? yes (upload or choose the swagger file)
    - What functions you like to have ??? 
        - Upload swagger file
        - Generate test scripts
        - Run the tests
        - Generate test case execution report

    - Front end technology : ReactJs
    - Back end technology : Logic + Prompt + API calls to LLM + Parse the response >> Send back to ReactJs (NodeJs / Springboot)
    - No database !!
	
	
Steps to setup the front end (Reactjs)

- Extract the front-end.zip
- Open VSCode and Import (Add folder to workspace)
- Go to terminal (Select project -- > Terminal -- > New Terminal)
- Confirm you are in the package. json path (ls / dir)
- Confirm node and npm are available (if not, install)
- run >> npm install >> command
- make sure all of the node modules are installed
- run >> npm start >> command
- confirm the page: http://localhost:3000/ >> displays correctly

Week 5 day2:
100 examples

5 examples in a batch - 20 batches - time will be shorter
50 examples in a batch - 2 batches - relationship between each data

Base Model (v1) -- > 10 training examples -- > Fine Tuned Model (v2) -- > 70%

Fine Tuned Model (v2) (seed) -- > 10 training examples (add/edit/delete) -- > 80%

Base Model (v1) -- > 10 training examples -- > Fine Tuned Model (v2) -- > 40%

Base Model (v1) -- > 13 training examples (add/edit/delete) -- > Fine Tuned Model (v3) I

Seed means -- > use similar hyper parameters turn the model

Week 7: day 1:
Supervised Fine tuning

- Built examples
- Upload the training and validation files (specific model)
- Create a supervised fine tuning using hyper-parameters
- epochs, learning rate, batch size, seed
- Use the output model in our app (browser extension)

- Accuracy becomes challenge
- How to confirm what is working and not working?

1) compile error ? Yes / No
2) runtime error ? Yes / No

Compile time

- syntax
- depedencies
- if all expected methods present or not
- if xpath patterns are good
- if data is correctly fed from method argument

Learning

- Even after multiple fine tuning using supervised approach >> there were errors in the accuracy !!
- If you are getting poor accuracy -- then it means

- Your example(s) are bad
- Your data is not fed right model
- Your prompt in the fine tuning is not great !!

- Fix these (above problems ) -- > re-train -- > until you get better accuracy

Example: 70 - 75 accuracy :: even after 5-7 iterations : score is not moving up !!

- Continue to generate new pages and check !!

Feature File (Based on flow) -- Page Name

Click Choose Date button from Create Contact Page

Step Definition

internally calls the page

one approach

DOM -- > Generate everything -- > Feature, Step Definitions, Page !

If the same page exist, how to handle ??

Better approach (Advanced solution)

RAG + Fine tuning + Vector 

------------------

Other problem:

Auto code fix -- > When it fails !!

Already existing -- GIT -- Vector - RAG <-- Fine tuning !!


RHLF - Reinforcement Learning from Human Feedback

- Expensive (than fine tuning)
- 10 examples x 10 iterations -- 100 data -- 4 USD (many models are not supported RHLF)
- Data collection is not easy (require expertise)
- The time taken to create a model would be very slow (100 data -90 minutes)
Remember - the data set for RLHF should be small (~10)

Supervised learning

- <Template>
- <DOM>
- <Page Java code>

system
user
assistant

Reinforcement learning:
- Are you supposed to be selenium expert ?
- syntax, method, correctness, debugging !!

Week 8 day 1:

 Tools for Productivity

a) Meetings AI Scribe & Action Items - Fireflies.ai
b) Develop new apps - Bolt.new
c) Organizing your daily tasks - Notion.ai
d) Building Presentations - gamma.app
e) OpenAI Voice for daily tasks and reminders

Prompt:
Context
- Building web based app for banking app (UK)
- Front end : ReactJs
Backend for FE : Restful API
Backend : NodeJs
Database : Mongo

Instructions

- Start with Registration page, Login Page
- Make sure to have every required info to be collected
- Color theme: reference -- > NatWest app

https://building-llm-powered-bro-lmyn8gy.gamma.site/

Problem Statement

- We got bunch of API testing to do (~automated tests)
- Input : Swagger document / Postman Collection
- We have to complete these in less than few weeks (~1-2 resources)
- We cannot afford to do the same with lot of money

Objectives

- Can we do this using Generative AI ? Yes !
- Do we need to have a API test framework? Yes !
     - Matschie
     - Cucumber (Feature file) + Step Definitions (Java) + POJO Classes (RestAssured) + Base API (Post/Get)
     - Orchestration (TestNg)

Objectives:

- Can we do this using Generative AI ? Yes !
- Do we need to have a API test framework? Yes !
- Matschie
- Cucumber (Feature file) + Step Definitions (Java) + POJO Classes (RestAssured) + Base API (Post/Get)
- Orchestration (TestNg)
- Who is the user? Tester / Automation Engineer
- Okay, what is the type of tool?

a) Browser Extension Tool - Use this only you need to talk web DOM structure (XX Not Preferred XX)
b) Web Based App (ReactJs) - Upload single or multiple - LLM -Generates & Download (Okay, Tester)
    - You need to download manually and copy them into your eclipse / IntelliJ / IDE
c) Build Plugin (IDE) - Right click on the swagger - Auto generates the code using LLM (Tech QA)


1) Web Based App

Objectives:

Input : Swagger File
Output : Generate the RestAssured code (based on framework)
a) Feature File
b) Step Definitions
c) POJO Classes
d) Base API

3)

Run these commands
a) npm install
b) npm start
4) Confirm the web app started in http://localhost:3000/

B :: SpringBoot Code

1) Extract the backend (LLM) zip
2) Import the maven project in eclipse
3) Run the maven spring boot command
a) mvn spring-boot:run (CLI)
b) in the run option -- > spring-boot:run
4) Confirm the springboot started in 8080 port


Week 8 day2:

Usecase : Browser Extension

Scenario 1 : Connect your feature file + Page class (Step Definition)

Tips

- Use checkbox
- Generate Both (Feature File --- > Step Definitions)
- Reference: Springboot Java


Scenario 2 : Add Repo Access to this

Tips

- Automated access to the repo (push code to repo)
- Challenge : Code is incorrectly generated --- > pushed to repo (XXX)
- Recommendations (Branch strategy) : feature -- > PR --- > development -- > PR --- > release (monthly)
- feature (ai-generated)

Scenario 3 : Automated Run

Tips

- Run button --- > run the tests (cucumber) using testng runner
- Connect your code to the testng local / repo
- Launch the browser and run tests
- Add browser tab - type, headless, grid or local



Scenario 4 : Multiple Pages / Feature sequence (Chaining)

Tips:

- implement larger DOM capture
use bg.js
- make sure the size is not bigger than context window

Scenario 5 : Update existing code

- Multiple tests / people can use same page
- You do not want to generate all the page
- Question : How do I update the code and not create it again?

- RAG ( i need to query existing git repo -- > all the classes --- > what methods are in ?? )

- Database : Vector >> PineCone + Mongo (Vectors)


Build AI Agentic Workflow ??

AI Agent: Browser Extension

LLM (Deepseek) + Tool (Selenium) + Memory (Chrome Storage) --- > AI Agent Assistant

- Human involvement (inspect + code + ... )

- Future : Website --- > Code --- > github --- > run itself !!
- Autonomous ! !



Web Based Ideas

1) Generate Manual Test Scenario

Tips

- Integrate with Jira (API)
- Drop down (list all epic, sprint)
- Choose sprint -- > list all stories
- Choose one story
- Generate all possible testcases
- Integrate to Jira (all tests get created)

Context:

Building AI assistant to generate tests from User Stories

Instructions

-Collect the epic, sprint details from Jira using API
Based on each sprint, get all the stories
-Provide me API for both actions (generic JIRA with latest version)