**Agents for Engineering Design and Operations**

The process of building and maintaining engineering systems, from relatively simple ones like the first car engine to missions like the apollo 11, has remained more or less the same over the last century. 

You start with the question of what you want to build, hopefully based on what people want. Senior system engineers write down the requirements of the system in terms of performance and design. These then get cascaded down into component level performance and design requirements. 

Engineers get to work building the solutions at component and system level. They define the architecture, the detailed design and start implementing. Once the design is ready, integration tests and verifications happen at the component and system level. After the performance of the system is validated, it is deployed in the field and maintained till the end of its lifetime. 

**The problem**
This process is highly labor intensive and slow. Junior design engineers work at component level to execute on requirements that have been cascaded down to them by senior system engineers. They typically perform a combination of writing documentation on the architecture as well as performing computer aided desing/engineering/simulations to design the components. This is in addition to the meetings they attend to verify with their stakeholders that they are on the right path. Similar processes are followed by engineers responsible for manufacturing the components and systems: creating tests needed to verify performance, executing them and documenting the results. Finally customer support engineers typically read through the logs produced by the system once it is deployed, ensuring it performs as it should, finding the root cause in case something goes wrong, while simultaneously thinking about what to change so that the problems don't occur again. 

Engineering companies are typically organized in response to the system definition, implementation, testing and integration process, starting from research to development to manufacturing and customer support. Each of these organizations hire hundreds or thousands of engineers who are constantly working within their scope while ensuring that they communicate with their stakeholders so that the full system runs and operates as required.
The human labor is expensive, hard to replace and varying in motivation/competence. 

**The solution**
AI agents like Claude Code and coding assistants like Cursor/Github copilot are helping software engineers write code faster. Similarly, Agentic AI (LLM running in a loop with tool calls) can help design engineers write and revise requirement documents, perform simulations using CAD/CAE tools, build predictive surrogate models using predictive 