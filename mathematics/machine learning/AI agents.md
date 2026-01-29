## AI agents
- system that interacts with [[LLM]] that has
	- a control loop
	- a state, actions, feedback
	- goal directed multi-step behavior
- an [[AI agents]] is a **dynamic control system** that **interacts** with its **environment** with **actions** and **observes** it
### components
• **[[LLM]]**: decision and action proposals
• **Control Plane**: loop, policies, budgets
• **State**: context and memory
• **Actions**: tools and external operations
• **Feedback**: outcomes from the environment

### Agent loop
#### 1. Observe
- agent gathers information about its current situation
- **user request**, **conversation history**, **environment signals**...
#### 2. Decide
- agent determines the next action
- mostly done by the [[LLM]] by reasoning over
	- observations
	- internal state
	- available actions
#### 3. Act
- The action is executed by the system / control plane → changes the environment
- for example an API call
#### 4. Update
- update the **internal state** by **storing the result of the action**
#### 5. Stop?
- the agent decides to continue or not by evaluation stop conditions
- for example: **goal reached**, **time limit exceeded**, **safety condition**...

# anki

START
Basic
[[AI agents]]
- definition
- core components (5)
- characteristics it needs to be considered an agent (3)

Back: 
## AI agents
- system that interacts with [[LLM]] that has
	- a control loop
	- a state, actions, feedback
	- goal directed multi-step behavior
- an [[AI agents]] is a **dynamic control system** that **interacts** with its **environment** with **actions** and **observes** it
### components
• **[[LLM]]**: decision and action proposals
• **Control Plane**: loop, policies, budgets
• **State**: context and memory
• **Actions**: tools and external operations
• **Feedback**: outcomes from the environment

_______________

### Agent loop
#### 1. Observe
- agent gathers information about its current situation
- **user request**, **conversation history**, **environment signals**...
#### 2. Decide
- agent determines the next action
- mostly done by the [[LLM]] by reasoning over
	- observations
	- internal state
	- available actions
#### 3. Act
- The action is executed by the system / control plane → changes the environment
- for example an API call
#### 4. Update
- update the **internal state** by **storing the result of the action**
#### 5. Stop?
- the agent decides to continue or not by evaluation stop conditions
- for example: **goal reached**, **time limit exceeded**, **safety condition**...

Tags: ml WS2526
<!--ID: 1769701867646-->
END


START
Basic
[[AI agents]]
- 5 steps with explanation and examples

Back: 

### Agent loop
#### 1. Observe
- agent gathers information about its current situation
- **user request**, **conversation history**, **environment signals**...
#### 2. Decide
- agent determines the next action
- mostly done by the [[LLM]] by reasoning over
	- observations
	- internal state
	- available actions
#### 3. Act
- The action is executed by the system / control plane → changes the environment
- for example an API call
#### 4. Update
- update the **internal state** by **storing the result of the action**
#### 5. Stop?
- the agent decides to continue or not by evaluation stop conditions
- for example: **goal reached**, **time limit exceeded**, **safety condition**...

_______
## AI agents
- system that interacts with [[LLM]] that has
	- a control loop
	- a state, actions, feedback
	- goal directed multi-step behavior
- an [[AI agents]] is a **dynamic control system** that **interacts** with its **environment** with **actions** and **observes** it
### components
• **[[LLM]]**: decision and action proposals
• **Control Plane**: loop, policies, budgets
• **State**: context and memory
• **Actions**: tools and external operations
• **Feedback**: outcomes from the environment



Tags: ml WS2526
<!--ID: 1769701867649-->
END