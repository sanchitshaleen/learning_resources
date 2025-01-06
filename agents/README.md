# Agentic Systems

1) Understanding Agentic AI Architecture
https://www.srajdev.com/understanding-agentic-ai-architecture/

Key Takeaways: <br>
a) Agentic AI: <br>
i) Agentic AI refers to AI systems that demonstrate autonomous behavior, actively working to achieve goals with minimal direct human intervention. <br>
ii) The term "agentic" suggests that these systems can take initiative, make decisions, and even communicate with other agents to achieve complex tasks. <br>

b) Agents and System 1 vs. System 2 Thinking <br>
i) Agentic AI often blends two modes of operation—rapid, instinctual responses for well-defined tasks (System 1) and more comprehensive, deliberate actions for complex decision-making (System 2) <br>
ii) Understanding this distinction helps to design agents that can leverage both approaches effectively, depending on the nature of the task at hand <br>

c) Architecture and Components <br>
<img width="781" alt="Screenshot 2025-01-05 at 9 59 07 PM" src="https://github.com/user-attachments/assets/b17e711e-5f5d-4426-a9ba-6ce36d1af377" /> 

i) Triggering Mechanisms: Any agentic system can be initiated by a user interacting with it or by another system triggering an action, either through a webhook or a frequency timer. <br>
ii) LLM: Every agentic framework is dependent on a language model (LLM). Each component can access the same or different LLM to complete its goal, providing flexibility and scalability in handling various tasks. <br>
iii) Planning Agent: The planning agent serves as the orchestration component, which includes reasoning, planning, and task decomposition. This agent knows all other agents and, through proper planning, reasoning, and task decomposition, decides which agents to execute and in what order. <br>
iv) Agents: Agents encapsulate a set of instructions and tools to achieve a given task <br>
v) Memory: Memory in agentic AI allows agents to store information and recall it in future interactions. Memory is available to all components at all times and can include different types <br>
vi) Guardrails: Rules such as “Ensure there is no mention of competitors in the reply”, “Avoid discussing religion or politics” are a few such examples that should exist at a framework level. These constraints are crucial for deploying agents in dynamic environments, providing default safety checks that can be edited if needed. <br>
vii) Agent Observability: Observability allows developers and users to understand what an agent is doing and why. Providing transparency in agent behavior helps diagnose issues, optimize performance, and ensure that the agent's decisions are aligned with the desired outcomes. <br>
viii) Adaptation and Learning: Adaptation involves an agent's ability to modify its behavior based on feedback from the environment. This includes reinforcement learning or other adaptive techniques that enable agents to optimize their decision-making over time <br>

d) AI Agents Ecosystem: The agent AI infrastructure has evolved tremendously over the last year (2024) and is expected to continue evolving rapidly. This growth has brought many new tools and components that facilitate building agentic AI systems. <br>
<img width="640" alt="Screenshot 2025-01-05 at 10 19 05 PM" src="https://github.com/user-attachments/assets/70279df8-8701-4944-96ea-bf40f7cdc399" />
<br>
Pros <br>

Diverse Tooling: There are numerous good tools available for every part of building agentic AI. This diversity allows developers to pick specialized tools for their specific requirements. <br>
Designed for simplicity: Many of these tools are designed with user-friendly interfaces or straightforward APIs, making it easy to get started and develop prototypes quickly in each area. <br>

Cons <br>

Fragmented Ecosystem: The large number of specialized tools results in a highly fragmented ecosystem, which requires a lot of effort to stitch together. Developers often spend more time integrating and managing multiple tools than on core development. <br>
Integration Complexity: Ensuring compatibility and efficient communication between different tools can be complex and time-consuming, adding significant overhead to projects. <br>

e) Frameworks <br>

Most of the frameworks have most of the functionality and differ in implementation detail rather than functionality.

Langchain: Easy to get started but hard to build complex flows. Best used alongside LangGraph. <br>
LangGraph: Along with Langchain, Langgraph is a very powerful tool. Takes a little getting used to, and visualizing the graph is hard, making it challenging for someone to understand the flow without deep exploration.  <br>
CrewAI: Overall a great framework that allows all functionality. Also has a Saas platform to make it easier to use. Allows hierarchical flows, but more complex flows are still on the roadmap.  <br>
Swarm: Primarily an educational framework and not yet ready for production. It has most functionalities, but combining them to build complex flows seems limited.  <br>

f) Evaluation <br>
Best Practices: <br>

Structured Outputs: Ensure each agent's output is well-structured. Structured output makes it easier to validate correctness and promptly identify issues. <br>
Testing at Scale: Use larger language models to test final outcomes to ensure scalability. Larger models can simulate a variety of user behaviors, which helps stress-test the system effectively. <br>
Iterative Evaluation: Agents should be evaluated iteratively, allowing developers to identify weaknesses early and make improvements swiftly. Each iteration helps refine agents and contributes to more stable outcomes over time. <br>

f) Considerations <br>
i) Best practices for improving accuracy of function calling: <br>
a) Limit the Tools: Limit the number of tools to 4-5 per prompt. Beyond this, hallucinations increase, and accuracy decreases significantly.<br>
b) Specific Prompts with Examples: Make the prompt very specific and try to provide examples of when to call which tool. This can help the LLM better understand the context, reducing errors and improving decision accuracy.<br>
c) Good Evaluations for Tool Calling: Having thorough evaluations for tool calling is essential, as it helps measure and improve accuracy. This is achievable since the output can be structured, making it easier to validate if the correct tools were used effectively.<br>

ii) Best practices for minimizing costs: <br>
a) LLM Selection: Each agent can use a different type of LLM that is best suited for its purpose. For instance, a planning agent may require a more powerful LLM capable of complex reasoning, while simpler agents can rely on lightweight LLMs that are less expensive. <br>
b) Optimized Token Usage: Using tokens and prompts wisely can significantly reduce costs. For example, sending summaries or only the relevant portions of a code base can help reduce the token count, thereby minimizing LLM usage expenses. <br>
c) Batch Processing and Shared Resources: Agents can be designed to share resources when possible. For instance, memory and intermediate results can be cached and reused by multiple agents, reducing redundant computations and LLM calls. This type of optimization helps cut down on both computational and financial costs. <br>

iii) Best practices for minimizing latency: <br>
a) Streaming Last Layer: For user-facing agents, making the last layer of the LLM streaming can significantly reduce the perceived latency. Streaming the output allows the system to provide tokens as they are generated, creating a faster response time for the end-user and improving the overall user experience. <br>
b) Prompt Optimization: Prompts and results can often be identical across different users. To reduce latency, prompt caching can be employed to reuse previously computed results whenever possible. By caching common prompts, agents can bypass unnecessary recomputation, delivering faster responses. <br>
c) Parallel Execution: When possible, agents should run in parallel rather than sequentially. For example, a sentiment analysis and a technical analysis could be conducted simultaneously, reducing the total processing time for a task. <br>





