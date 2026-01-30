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

#### example

##### task
- find **3 suitable meeting slots** in the next week for a list of persons
- constraints: **max 4 iterations** and **2 tool calls**
- stop when **>= 3 slots are found** or **budget exhausted**

##### t=0
- **observe**: user request and constraints
- **decide**: need to call the calendar tool to request persons calendar
- **act**: call calendar tool `CalendarFreeBusy(attendees, range)`
- **update**: store conflict and candidate windows in the state
##### t=1
- **observe**: free window overlaps
- **decide**: generate proposals
- **act**: propose slots `CalendarFreeBusy(attendees, proposed_slots)`
- **update**: keep only slots valid for all attendees
##### t=2
- **observe**: only two slots found
- **decide**: expand search window
- **act**: `CalendarFreeBusy(attendees, expanded_range)`
- **update**: add new candidate windows + re-check
##### t=2
- **observe**: 4 slots found
- **decide**: draft email with top 3 options
- **act**: store final proposal + rationale
- **update**: add new candidate windows + re-check
- **stop**: success criteria met

### autonomy levels
- **Human-in-the-Loop (HITL)**: Agent proposes actions, human approves → high latency
- **Human-on-the-Loop (HOTL)**: Human monitors and can intervene
- **Fully Autonomous**: Agent acts without human intervention → high risk

### stopping criteria
- agents are designed to continue by default → stopping conditions are a critical design choice

#### budget constraints
- **step**: number of iterations
- **time**: time based deadline
- **cost**: number of tokens used
- **risk**: number of irreversible actions

#### stopping constraints
- **success**: goal reached, test passed
- **failure**: repeated errors, no progress
- **budget exhausted**
- **hand-off** to human


### failure modes
- **infinite looping** with similar observations and actions
- **goal drift**: sub goal replaces original objective
- **tool thrashing**: excessive/redundant tool calls
- **premature stopping** does to overaggressive budget constraints
- **compounding errors**: small early errors propagate across steps
# anki

START
Basic
how can [[AI agents]] fail and how to prevent it (5)

Back: 
### failure modes
- **infinite looping** with similar observations and actions → **define suitable budget constrains**
- **goal drift**: sub goal replaces original objective
- **tool thrashing**: excessive/redundant tool calls → **define suitable budget constrains for tool usage**
- **premature stopping** does to overaggressive budget constraints → **loosen budget constraints**
- **compounding errors**: small early errors propagate across steps

_______________
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

Tags: ml WS2526
<!--ID: 1769791391765-->
END

START
Basic
[[AI agents]]: stopping criteria 4+4

Back: 
### stopping criteria
- agents are designed to continue by default → stopping conditions are a critical design choice

#### budget constraints
- **step**: number of iterations
- **time**: time based deadline
- **cost**: number of tokens used
- **risk**: number of irreversible actions

#### stopping constraints
- **success**: goal reached, test passed
- **failure**: repeated errors, no progress
- **budget exhausted**
- **hand-off** to human

_______________
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

Tags: ml WS2526
<!--ID: 1769791391770-->
END

START
Basic
autonomy levels of [[AI agents]] (3) with advantages and disadvantages

Back: 
### autonomy levels
- **Human-in-the-Loop (HITL)**: Agent proposes actions, human approves → high latency
- **Human-on-the-Loop (HOTL)**: Human monitors and can intervene
- **Fully Autonomous**: Agent acts without human intervention → high risk

_______________
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

Tags: ml WS2526
<!--ID: 1769791391773-->
END

START
Basic
give an example how an [[AI agents]] would perform this task
##### task
- find **3 suitable meeting slots** in the next week for a list of persons
- constraints: **max 4 iterations** and **2 tool calls**
- stop when **>= 3 slots are found** or **budget exhausted**

Back: 
##### t=0
- **observe**: user request and constraints
- **decide**: need to call the calendar tool to request persons calendar
- **act**: call calendar tool `CalendarFreeBusy(attendees, range)`
- **update**: store conflict and candidate windows in the state
##### t=1
- **observe**: free window overlaps
- **decide**: generate proposals
- **act**: propose slots `CalendarFreeBusy(attendees, proposed_slots)`
- **update**: keep only slots valid for all attendees
##### t=2
- **observe**: only two slots found
- **decide**: expand search window
- **act**: `CalendarFreeBusy(attendees, expanded_range)`
- **update**: add new candidate windows + re-check
##### t=2
- **observe**: 4 slots found
- **decide**: draft email with top 3 options
- **act**: store final proposal + rationale
- **update**: add new candidate windows + re-check
- **stop**: success criteria met


_______________
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

Tags: ml WS2526
<!--ID: 1769791391775-->
END

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