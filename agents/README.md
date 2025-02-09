# Agentic Systems

## 1) Understanding Agentic AI Architecture
source: https://www.srajdev.com/understanding-agentic-ai-architecture/

**Key Takeaways:** <br>

**a) Agentic AI:** <br>

i) Agentic AI refers to AI systems that demonstrate autonomous behavior, actively working to achieve goals with minimal direct human intervention. <br>

ii) The term "agentic" suggests that these systems can take initiative, make decisions, and even communicate with other agents to achieve complex tasks. <br>

**b) Agents and System 1 vs. System 2 Thinking** <br>

i) Agentic AI often blends two modes of operation—rapid, instinctual responses for well-defined tasks (System 1) and more comprehensive, deliberate actions for complex decision-making (System 2) <br>

ii) Understanding this distinction helps to design agents that can leverage both approaches effectively, depending on the nature of the task at hand <br>

**c) Architecture and Components** <br>
<img width="781" alt="Screenshot 2025-01-05 at 9 59 07 PM" src="https://github.com/user-attachments/assets/b17e711e-5f5d-4426-a9ba-6ce36d1af377" /> 

***i) Triggering Mechanisms:*** Any agentic system can be initiated by a user interacting with it or by another system triggering an action, either through a webhook or a frequency timer. <br>

***ii) LLM:*** Every agentic framework is dependent on a language model (LLM). Each component can access the same or different LLM to complete its goal, providing flexibility and scalability in handling various tasks. <br>

***iii) Planning Agent:*** The planning agent serves as the orchestration component, which includes reasoning, planning, and task decomposition. This agent knows all other agents and, through proper planning, reasoning, and task decomposition, decides which agents to execute and in what order. <br>

***iv) Agents:*** Agents encapsulate a set of instructions and tools to achieve a given task <br>

***v) Memory:*** Memory in agentic AI allows agents to store information and recall it in future interactions. Memory is available to all components at all times and can include different types <br>

***vi) Guardrails:*** Rules such as “Ensure there is no mention of competitors in the reply”, “Avoid discussing religion or politics” are a few such examples that should exist at a framework level. These constraints are crucial for deploying agents in dynamic environments, providing default safety checks that can be edited if needed. <br>

***vii) Agent Observability:*** Observability allows developers and users to understand what an agent is doing and why. Providing transparency in agent behavior helps diagnose issues, optimize performance, and ensure that the agent's decisions are aligned with the desired outcomes. <br>

***viii) Adaptation and Learning:*** Adaptation involves an agent's ability to modify its behavior based on feedback from the environment. This includes reinforcement learning or other adaptive techniques that enable agents to optimize their decision-making over time <br>

**d) AI Agents Ecosystem:** The agent AI infrastructure has evolved tremendously over the last year (2024) and is expected to continue evolving rapidly. This growth has brought many new tools and components that facilitate building agentic AI systems. <br>
<img width="640" alt="Screenshot 2025-01-05 at 10 19 05 PM" src="https://github.com/user-attachments/assets/70279df8-8701-4944-96ea-bf40f7cdc399" />
<br>
Pros <br>

***Diverse Tooling:*** There are numerous good tools available for every part of building agentic AI. This diversity allows developers to pick specialized tools for their specific requirements. <br>

***Designed for simplicity:*** Many of these tools are designed with user-friendly interfaces or straightforward APIs, making it easy to get started and develop prototypes quickly in each area. <br>

Cons <br>

***Fragmented Ecosystem:*** The large number of specialized tools results in a highly fragmented ecosystem, which requires a lot of effort to stitch together. Developers often spend more time integrating and managing multiple tools than on core development. <br>

***Integration Complexity:*** Ensuring compatibility and efficient communication between different tools can be complex and time-consuming, adding significant overhead to projects. <br>

**e) Frameworks** <br>

Most of the frameworks have most of the functionality and differ in implementation detail rather than functionality.

***Langchain:*** Easy to get started but hard to build complex flows. Best used alongside LangGraph. <br>

***LangGraph:*** Along with Langchain, Langgraph is a very powerful tool. Takes a little getting used to, and visualizing the graph is hard, making it challenging for someone to understand the flow without deep exploration.  <br>

***CrewAI:*** Overall a great framework that allows all functionality. Also has a Saas platform to make it easier to use. Allows hierarchical flows, but more complex flows are still on the roadmap.  <br>

***Swarm:*** Primarily an educational framework and not yet ready for production. It has most functionalities, but combining them to build complex flows seems limited.  <br>

**f) Evaluation** <br>
Best Practices: <br>

***i) Structured Outputs:*** Ensure each agent's output is well-structured. Structured output makes it easier to validate correctness and promptly identify issues. <br>

***ii) Testing at Scale:*** Use larger language models to test final outcomes to ensure scalability. Larger models can simulate a variety of user behaviors, which helps stress-test the system effectively. <br>

***iii) Iterative Evaluation:*** Agents should be evaluated iteratively, allowing developers to identify weaknesses early and make improvements swiftly. Each iteration helps refine agents and contributes to more stable outcomes over time. <br>

**g) Considerations** <br>

***i) Best practices for improving accuracy of function calling:*** <br>

a) Limit the Tools: Limit the number of tools to 4-5 per prompt. Beyond this, hallucinations increase, and accuracy decreases significantly.<br>

b) Specific Prompts with Examples: Make the prompt very specific and try to provide examples of when to call which tool. This can help the LLM better understand the context, reducing errors and improving decision accuracy.<br>

c) Good Evaluations for Tool Calling: Having thorough evaluations for tool calling is essential, as it helps measure and improve accuracy. This is achievable since the output can be structured, making it easier to validate if the correct tools were used effectively.<br>

***ii) Best practices for minimizing costs:*** <br>

a) LLM Selection: Each agent can use a different type of LLM that is best suited for its purpose. For instance, a planning agent may require a more powerful LLM capable of complex reasoning, while simpler agents can rely on lightweight LLMs that are less expensive. <br>

b) Optimized Token Usage: Using tokens and prompts wisely can significantly reduce costs. For example, sending summaries or only the relevant portions of a code base can help reduce the token count, thereby minimizing LLM usage expenses. <br>

c) Batch Processing and Shared Resources: Agents can be designed to share resources when possible. For instance, memory and intermediate results can be cached and reused by multiple agents, reducing redundant computations and LLM calls. This type of optimization helps cut down on both computational and financial costs. <br>

***iii) Best practices for minimizing latency:*** <br>
a) Streaming Last Layer: For user-facing agents, making the last layer of the LLM streaming can significantly reduce the perceived latency. Streaming the output allows the system to provide tokens as they are generated, creating a faster response time for the end-user and improving the overall user experience. <br>

b) Prompt Optimization: Prompts and results can often be identical across different users. To reduce latency, prompt caching can be employed to reuse previously computed results whenever possible. By caching common prompts, agents can bypass unnecessary recomputation, delivering faster responses. <br>

c) Parallel Execution: When possible, agents should run in parallel rather than sequentially. For example, a sentiment analysis and a technical analysis could be conducted simultaneously, reducing the total processing time for a task. <br>

## 2) Agents
source: https://huyenchip.com//2025/01/07/agents.html

**Key Takeaways:** <br>

**a) Agent Overview:** <br>

i) An agent is defined by the environment it operates in and the set of tools it has access to. In an AI-powered agent, the AI model is the brain that leverages its tools and feedback from the environment to plan how best to accomplish a task. <br>

ii) While the concept of “agents” sounds novel, they are built upon many concepts that have been used since the early days of LLMs, including self-critique, chain-of-thought, and structured outputs. <br>

iii) Given an environment, the success of an agent in an environment depends on the tool it has access to and the strength of its AI planner. <br>

**b) Tools:** <br>

i) By itself, a model can typically perform one action—an LLM can generate text and an image generator can generate images. External tools make an agent vastly more capable. <br>

ii) Depending on the agent’s environment, there are many possible tools. Here are ***three categories*** of tools that you might want to consider: <br> 

***1) Knowledge augmentation (i.e., context construction):*** <br>

a) Accessing Enterprise-specific private knowledge-base using tools like text retriever, image retriever, SQL executor, internal people search, inventory API that returns the status of different products, Slack retrieval, an email reader. <br>

b) Web browsing using tools like search APIs, news APIs, GitHub APIs, or social media APIs <br>

***2) Capability extension:*** <br>

a) Simple tools that can significantly boost a model’s capability include a calculator, calendar, timezone converter, unit converter (e.g., from lbs to kg), and translator that can translate to and from the languages that the model isn’t good at. <br>

b) More complex but powerful tools are code interpreters. Instead of training a model to understand code, you can give it access to a code interpreter to execute a piece of code, return the results, or analyze the code’s failures. <br>

c) Tool use can significantly boost a model’s performance compared to just prompting or even finetuning. Chameleon (Lu et al., 2023) shows that a GPT-4-powered agent, augmented with a set of 13 tools, can outperform GPT-4 alone on several benchmarks. Examples of tools this agent used are knowledge retrieval, a query generator, an image captioner, a text detector, and Bing search. <br>

***3) Tools that let your agent act upon its environment:*** <br>

a) Tools can also perform write actions, making changes to the data sources. An SQL executor can retrieve a data table (read) and change or delete the table (write). An email API can read an email but can also respond to it. A banking API can retrieve your current balance, but can also initiate a bank transfer. <br>

b) Write actions enable a system to do more. They can enable you to automate the whole customer outreach workflow: researching potential customers, finding their contacts, drafting emails, sending first emails, reading responses, following up, extracting orders, updating your databases with new orders, etc <br>

**c) Planning:** <br>

i) Given a task, there are many possible ways to solve it, but not all of them will lead to a successful outcome. <br>

ii) To avoid fruitless execution, planning should be decoupled from execution. You ask the agent to first generate a plan, and only after this plan is validated is it executed. <br>

iii) The plan can be validated using heuristics. For example, one simple heuristic is to eliminate plans with invalid actions. If the generated plan requires a Google search and the agent doesn’t have access to Google Search, this plan is invalid. <br>

iv) A plan can also be validated using AI judges. You can ask a model to evaluate whether the plan seems reasonable or how to improve it. <br>

v) If the plan consists of external tools, function calling will be invoked. Outputs from executing this plan will then again need to be evaluated. Note that the generated plan doesn’t have to be an end-to-end plan for the whole task. It can be a small plan for a subtask. <br>

<img width="829" alt="Screenshot 2025-02-07 at 11 33 04 PM" src="https://github.com/user-attachments/assets/8bf72a89-2983-4169-9ceb-2b25ec64976b" /> <br>

vi) To summarize, solving a task typically involves the following processes. Note that reflection isn’t mandatory for an agent, but it’ll significantly boost the agent’s performance. <br>

1) Plan generation: come up with a plan for accomplishing this task. A plan is a sequence of manageable actions, so this process is also called task decomposition. <br>

2) Reflection and error correction: evaluate the generated plan. If it’s a bad plan, generate a new one. <br>

3) Execution: take actions outlined in the generated plan. This often involves calling specific functions. <br>

4) Reflection and error correction: upon receiving the action outcomes, evaluate these outcomes and determine whether the goal has been accomplished. Identify and correct mistakes. If the goal is not completed, generate a new plan. <br>

vii) ***Foundation Models as Planners:*** <br>

1) While there is a lot of anecdotal evidence that LLMs are poor planners, it’s unclear whether it’s because we don’t know how to use LLMs the right way or because LLMs, fundamentally, can’t plan. <br>

2) Planning, at its core, is a search problem. You search among different paths towards the goal, predict the outcome (reward) of each path, and pick the path with the most promising outcome. Often, you might determine that no path exists that can take you to the goal. <br>

3) Even if AI can’t plan, it can still be a part of a planner. It might be possible to augment an LLM with a search tool and state tracking system to help it plan. <br>

vii) ***Plan Generation:*** <br>

1) Tips for making an agent better at planning. <br>

1.1) Write a better system prompt with more examples. <br>
1.2) Give better descriptions of the tools and their parameters so that the model understands them better.<br>
1.3) Rewrite the functions themselves to make them simpler, such as refactoring a complex function into two simpler functions. <br>
1.4) Use a stronger model. In general, stronger models are better at planning. <br>
1.5) Finetune a model for plan generation. <br>

2) Function Calling <br>

A tool is a function. Invoking a tool is, therefore, often called function calling. Different model APIs work differently, but in general, function calling works as follows: <br>

2.1) Create a tool inventory. Declare all the tools that you might want a model to use. Each tool is described by its execution entry point (e.g., its function name), its parameters, and its documentation (e.g., what the function does and what parameters it needs). <br>
2.2) Specify what tools the agent can use for a query.
Because different queries might need different tools, many APIs let you specify a list of declared tools to be used per query. Some let you control tool use further by the following settings: <br>
***required***: the model must use at least one tool. <br>
***none***: the model shouldn’t use any tool. <br>
***auto***: the model decides which tools to use. <br>

<img width="878" alt="Screenshot 2025-02-08 at 8 33 31 PM" src="https://github.com/user-attachments/assets/0acd534a-b5f8-43dd-813a-311f472c4845" />

<br>

3) Planning Granularity <br>

3.1) There’s a planning/execution tradeoff. A detailed plan is harder to generate, but easier to execute. A higher-level plan is easier to generate, but harder to execute. <br>

3.2) An approach to circumvent this tradeoff is to plan hierarchically. First, use a planner to generate a high-level plan, such as a quarter-to-quarter plan. Then, for each quarter, use the same or a different planner to generate a month-to-month plan. <br>

3.3) Using more natural language helps your plan generator become robust to changes in tool APIs. If your model was trained mostly on natural language, it’ll likely be better at understanding and generating plans in natural language and less likely to hallucinate. <br>

3.4) The downside of this approach is that you need a translator to translate each natural language action into executable commands. However, translating is a much simpler task than planning and can be done by weaker models with a lower risk of hallucination. <br>

4) Complex Plans <br>

The order in which actions can be executed is called a control flow. The list below provides an overview of each control flow, including sequential for comparison: <br>

4.1) ***Sequential*** <br>
Executing task B after task A is complete, possibly because task B depends on task A. For example, the SQL query can only be executed after it’s been translated from the natural language input. <br>

4.2) ***Parallel***<br>
Executing tasks A and B at the same time. For example, given the query “Find me best-selling products under $100”, an agent might first retrieve the top 100 best-selling products and, for each of these products, retrieve its price.<br>

4.3) ***If statement*** <br>
Executing task B or task C depending on the output from the previous step. For example, the agent first checks NVIDIA’s earnings report. Based on this report, it can then decide to sell or buy NVIDIA stocks. Anthropic’s post calls this pattern “routing”.<br>

4.4) ***For loop*** <br>
Repeat executing task A until a specific condition is met. For example, keep on generating random numbers until a prime number. <br>

<img width="830" alt="Screenshot 2025-02-08 at 8 43 30 PM" src="https://github.com/user-attachments/assets/0ffee40f-b2fc-47d1-a7b4-797ddd75eb01" />

<br>

viii) ***Reflection and error correction*** <br>

1) Reflection and error correction are two different mechanisms that go hand in hand. Reflection generates insights that help uncover errors to be corrected. While reflection isn’t strictly necessary for an agent to operate, it’s necessary for an agent to succeed. There are many places during a task process where reflection can be useful: <br>

1.1) After receiving a user query to evaluate if the request is feasible. <br>
1.2) After the initial plan generation to evaluate whether the plan makes sense.<br>
1.3) After each execution step to evaluate if it’s on the right track. <br>
1.4) After the whole plan has been executed to determine if the task has been accomplished. <br>

2) ReAct (Reason + Act) <br>
2.1) Interleaving reasoning and action has become a common pattern for agents. <br>
2.2) “Reasoning” encompasses both planning and reflection. At each step, the agent is asked to explain its thinking (planning), take actions, then analyze observations (reflection), until the task is considered finished by the agent <br>

<img width="711" alt="Screenshot 2025-02-08 at 8 54 25 PM" src="https://github.com/user-attachments/assets/ff8476f5-d15f-4668-97f5-604cce474ab0" />

<br>

3) Reflexion Agent Framework <br>
3.1) In this framework, reflection is separated into two modules: an evaluator that evaluates the outcome and a self-reflection module that analyzes what went wrong.  <br>

3.2) Below example covers Reflexion Agents in action. "trjectory" refers to a "plan". At each step, after evaluation and self-reflection, the agent proposes a new trajectory <br>
<img width="856" alt="Screenshot 2025-02-08 at 8 59 02 PM" src="https://github.com/user-attachments/assets/b0fa2d81-5d3c-44f6-81b9-e7fb61f6cda8" />



















