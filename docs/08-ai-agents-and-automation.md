# Chapter 08 — AI Agents & Automation

**Project:** Artificial Intelligence (AI) — Deep Research & Study Notes  
**Owner / Content Creator:** Sandeep Barupal  
**Copyright:** © 2026 Sandeep Barupal. Original explanatory notes; third-party names and trademarks belong to their respective owners.

## 1. AI Agent kya hai?

AI Agent ek software system hai jo kisi goal ko achieve karne ke liye context samajh sakta hai, plan bana sakta hai, tools call kar sakta hai, results observe kar sakta hai aur zaroorat ke hisaab se next action choose kar sakta hai.

Example: "Meri weekly work report prepare karo." Authorized tools ke saath Agent task records read, pending work group, report draft aur approval request prepare kar sakta hai. Agent ki capability uske tools, permissions aur system design par depend karti hai.

## 2. Chatbot vs Automation vs AI Agent

| Type | Kaise kaam karta hai | Example |
|---|---|---|
| Chatbot | Conversation aur answers | Support FAQ |
| Rule-based automation | Predefined trigger/action | Daily backup |
| AI Agent | Goal ke hisaab se actions choose kar sakta hai | Research workflow with search and document tools |

Ye systems combine bhi ho sakte hain.

## 3. Agent ke core components

- **Goal:** Desired outcome.
- **Instructions:** Rules aur boundaries.
- **Model:** Language/task understanding aur decisions.
- **Planner:** Work ko steps mein divide karna.
- **Tools:** APIs aur external functions.
- **State:** Current task ki progress.
- **Memory:** Relevant past information.
- **Environment:** Jahan actions execute hote hain.
- **Evaluator:** Result quality check.
- **Guardrails:** Permissions aur safety restrictions.

## 4. Agent execution loop

1. User goal receive.
2. Request aur context understand.
3. Plan ya next step decide.
4. Tool choose aur arguments prepare.
5. Backend permission aur input validation kare.
6. Tool execute ho.
7. Result observe aur validate ho.
8. Agent next step, retry, escalation ya final answer choose kare.

Loop ko max steps, timeout aur budget se bound karna chahiye. Infinite action loop avoid karein.

## 5. Tools and function calling

Tools Agent ko external capabilities dete hain: search, calculator, database read, file processing, email draft, calendar, code repository ya browser actions.

Model tool-call request propose karta hai; application/backend ko arguments validate, authorization check aur tool execution karna hota hai. Model ko direct unrestricted system access dena unsafe hai.

Example Python function:

```python
def calculate_total(price, quantity):
    if price < 0 or quantity < 0:
        raise ValueError("Values must be non-negative")
    return price * quantity

print(calculate_total(500, 3))  # 1500
```

## 6. Planning and task decomposition

Planning large goal ko smaller tasks mein todti hai.

Example: Research report:
1. Scope define.
2. Questions list.
3. Trusted sources search.
4. Findings compare.
5. Gaps identify.
6. Draft prepare.
7. Citations verify.
8. Human review.

Approaches include task decomposition, plan-and-execute, hierarchical planning aur ReAct-style action/observation loops. Simple requests ko unnecessarily complex planning ki zaroorat nahi.

## 7. Agent memory

- **Working memory:** Current task ke temporary details.
- **Conversation history:** Current/previous messages, subject to retention policy.
- **Episodic memory:** Past task events and outcomes.
- **Semantic memory:** Structured facts or knowledge.
- **External knowledge:** Documents, databases or search indexes.

Memory ko explicit access control, retention, correction aur deletion policies ke saath design karein. Sensitive information bina valid need aur permission store na karein.

## 8. Agent state

State current execution ka structured record hota hai, jaise:
- Task ID and goal.
- Current step.
- Completed steps.
- Tool outputs.
- Retry count.
- Approval status.
- Error details.

State ko memory se confuse na karein: state task execution track karta hai; memory reusable information retain kar sakti hai.

## 9. Single-agent architecture

Ek Agent multiple tools use karke task complete karta hai. Ye simple workflows aur early prototypes ke liye useful hai.

Benefits: simpler deployment, easier debugging, fewer coordination steps.

Limitations: too many tools ya broad responsibilities se tool selection aur context management difficult ho sakte hain.

## 10. Multi-agent systems

Multiple specialized Agents coordinated task par kaam karte hain.

Example roles:
- Supervisor: Work assign aur coordinate.
- Researcher: Sources collect.
- Analyst: Compare and interpret.
- Writer: Draft prepare.
- Reviewer: Quality and citation check.

Multi-agent architecture coordination, cost, latency aur error propagation badha sakti hai. Jab single Agent sufficient ho, multi-agent system use karna zaroori nahi.

## 11. Orchestration

Orchestration Agents, tools aur workflow steps ko coordinate karti hai.

Important decisions:
- Sequential vs parallel execution.
- Agent/tool routing.
- Retry and timeout policy.
- State persistence.
- Error recovery.
- Human approval.
- Budget and stop conditions.

## 12. Workflow automation

AI + deterministic automation useful combination hai.

Example support workflow:
1. Ticket receive.
2. Rules se required fields validate.
3. AI category suggest kare.
4. Knowledge base se policy retrieve.
5. Response draft create.
6. High-risk case human ko route.
7. Approval ke baad response send.
8. Ticket status update and audit log.

Deterministic steps ko ordinary code/rules se handle karna often more reliable aur cheaper hota hai.

## 13. Human-in-the-Loop

Human approval ya review important actions ko safe banata hai.

Approval gates consider karein:
- Payments/refunds.
- External email/message send.
- Data deletion.
- Permission changes.
- Production deployment.
- Legal or high-impact decisions.

Approval screen par action, target, data changes aur consequences clearly show hone chahiye.

## 14. Guardrails and security

1. Least-privilege permissions.
2. Tool allowlists.
3. Input and output validation.
4. Prompt-injection defenses.
5. Untrusted documents ko instructions na samajhna.
6. Secrets management.
7. Rate and spending limits.
8. Timeouts and maximum steps.
9. Audit logs.
10. Emergency stop/kill switch.
11. Human approval for consequential actions.
12. Tenant and user data isolation.

Prompt injection user input, web pages ya retrieved files mein ho sakti hai. Retrieved content ko untrusted data treat karein. Tool permissions model ke generated text par depend karke grant na karein.

## 15. Agent evaluation

Agent ke final answer ke saath uske actions bhi evaluate karein.

| Metric | Meaning |
|---|---|
| Task success rate | Goal kitni baar correctly complete hua |
| Tool selection accuracy | Correct tool choose hua ya nahi |
| Argument validity | Tool inputs valid the ya nahi |
| Reliability | Failure/retry frequency |
| Latency | End-to-end time |
| Cost | Model and tool usage |
| Safety violations | Policy/permission breaches |
| Human escalation rate | Kitne tasks review ko bheje gaye |

Test normal, ambiguous, incomplete, adversarial aur failure scenarios par karein. Production monitoring ke saath regression test set maintain karein.

## 16. Frameworks and ecosystem

Examples:
- LangChain: LLM application components and integrations.
- LangGraph: Stateful, graph-based agent workflows.
- Microsoft AutoGen: Multi-agent application patterns.
- CrewAI: Role/task-oriented agent orchestration.
- OpenAI Agents SDK: Agent, tool, handoff and tracing primitives.

Official documentation:
- https://docs.langchain.com/
- https://docs.langchain.com/oss/python/langgraph/overview
- https://microsoft.github.io/autogen/
- https://docs.crewai.com/
- https://openai.github.io/openai-agents-python/

Framework features and recommended APIs can change; check current official docs before implementation.

## 17. Practical project — AI Research & Task Management Agent

Suggested pages:
- Dashboard: tasks, status and usage.
- AI Assistant: natural-language task request.
- Agents: registered agents and status.
- Tasks: create, assign and track.
- Workflows: configured steps.
- Tools: connected integrations and scopes.
- Approvals: pending human decisions.
- Activity Logs: tool/action history.
- Analytics: success, cost and latency.
- Settings: roles, limits and policies.

Suggested architecture:

```text
User Interface
     |
Backend API + Authentication
     |
Task Orchestrator ---- Persistent Task State
     |
Policy / Permission Check
     |
Agent Runtime
   /    |     \
Tools  Memory  Knowledge
     |
Validation + Human Approval
     |
Final Result + Audit Log
```

Start with one Agent and two safe read-only tools. Add write actions only after permissions, approval and audit logging are working.

## 18. Basic rule-based task router

This demonstrates routing only; it is not an LLM-powered autonomous Agent.

```python
def task_agent(task):
    task = task.lower()

    if "research" in task:
        return "Research workflow selected"
    if "report" in task:
        return "Report workflow selected"
    if "email" in task:
        return "Email workflow selected"

    return "Needs clarification or manual review"

print(task_agent("Prepare research report"))
```

Expected output: `Research workflow selected`.

## 19. Real-world use cases

- Customer support: classify tickets, retrieve policy, draft replies.
- Coding assistance: explain code, suggest tests, prepare changes for review.
- Research: collect and compare sources, draft reports.
- IT operations: summarize alerts and suggest remediation.
- Document processing: extract fields and route for validation.
- Business operations: prepare reports and coordinate approved workflows.

## 20. Knowledge check

1. Chatbot, fixed automation aur Agent mein kya difference hai?
2. Tool call execute karne se pehle backend ko kya validate karna chahiye?
3. Task state aur long-term memory mein kya difference hai?
4. Multi-agent architecture ki kuch costs kya hain?
5. Human approval kin actions ke liye important hai?
6. Prompt injection se kya risk hota hai?
7. Agent evaluation mein final answer ke alawa kya measure karna chahiye?

## 21. Chapter summary

- AI Agent goal-oriented task execution system hai.
- Tools/API calls external capabilities provide karte hain.
- Planning work ko steps mein divide karti hai.
- Memory reusable context store kar sakti hai; state current execution track karta hai.
- Single-agent simple workflows ke liye often enough hota hai.
- Multi-agent systems specialist roles coordinate karte hain, par complexity bhi badhate hain.
- Orchestration execution, retries, state aur approvals manage karti hai.
- Human-in-the-loop consequential actions ko review karta hai.
- Guardrails, least privilege, monitoring aur evaluation production safety ke liye zaroori hain.

**Chapter 08 status:** Research notes prepared.
