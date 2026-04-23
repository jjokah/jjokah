# AI Across the Software Development Lifecycle

How AI integrates into every phase of professional software development, from planning through maintenance, and what it means for how engineering teams work.

---

## What You Will Learn

- Map AI assistance to each of the six SDLC phases
- Apply AI to planning, design, implementation, testing, deployment, and maintenance
- Use AI code assistants effectively within a professional workflow
- Understand token economics and their impact on how you use AI in coding
- Build an AI-enhanced QA process using the First Author → Reviewer → Gatekeeper framework

---

## AI and the Modern SDLC

Software development has always been a craft that blends creativity, logic, and collaboration. AI doesn't change what great software is, but it dramatically changes how fast you can build it and at what cost.

The key mental model: **AI is a skilled junior developer on your team.** It is brilliant at execution, fast at boilerplate, and capable across a wide range of tasks. But it lacks the context of your specific system, the judgment to make architectural trade-offs, and the accountability for security and performance that a senior engineer carries.

Work with it as you would a capable junior: give clear specifications, review everything, use it to multiply your own velocity, not to replace your expertise.

---

## Phase 1: Planning and Requirements

### AI-Assisted User Story Generation

Given a high-level feature description, AI can generate a complete set of user stories in seconds, saving the hours a product team typically spends in requirements workshops.

**Prompt:**
```
Act as a senior product manager. Given this feature description:
"[feature description]"

Generate a complete set of user stories in the format:
"As a [user type], I want to [action], so that [benefit]."

Include:
- Happy path stories for the core workflow
- Edge case stories for error conditions
- Non-functional requirements (performance, accessibility, security)
- Acceptance criteria for each story
```

### Requirements Analysis and Gap Finding

> *"Review these requirements and identify any ambiguities, contradictions, or unstated assumptions. List any scenarios the requirements don't address."*

---

## Phase 2: Design

### Architecture Consultation

AI is useful for exploring design options and thinking through trade-offs, not for making final architectural decisions without expert human review.

**Effective architecture prompt:**
```
I'm designing a [type of system] that needs to:
- [Requirement 1]
- [Requirement 2]
- [Constraint: scale/budget/team size]

Compare three architectural approaches. For each:
- Describe the architecture
- List the advantages for my requirements
- List the disadvantages and risks
- Name one real-world system that uses this approach
```

> **Warning:** Architecture decisions have long-term consequences. AI can help you think through options, but final decisions require a senior engineer's judgment, knowledge of your team's capabilities, and your organization's operational context.

### UI/UX Prototyping

For frontend work, v0 by Vercel converts design descriptions into production-ready React components:
> *"Create a data table component that shows user activity logs. Columns: timestamp, user, action, resource, status. Sortable columns. Pagination at 25 rows per page. Status column shows colored badges (green=success, red=error, yellow=warning)."*

---

## Phase 3: Implementation

### The Three AI Coding Workflows

**Workflow 1: IDE-Integrated Co-Pilots**

Tools like GitHub Copilot and Codeium work inline as you type, autocompleting functions, suggesting variable names, and generating boilerplate.

Best for:
- Repetitive patterns (the 10th API endpoint, the 5th form handler)
- Standard library usage
- Type declarations and interface definitions
- Function documentation

**Workflow 2: Conversational Development (Cursor, Claude)**

More powerful than autocomplete; you describe what you want and review the full implementation.

Effective conversational prompts:
```
Implement a function that [does X].
Requirements:
- Input: [type and format]
- Output: [type and format]
- Handle these edge cases: [list]
- Error handling: [approach]
- Performance constraint: [if any]

Also write unit tests for this function.
```

**Workflow 3: Multi-File Refactoring (Cursor Composer)**

For changes that span multiple files:
```
Refactor the authentication system to use JWT tokens instead
of session cookies. The changes should:
- Update the login endpoint to issue JWTs
- Add JWT validation middleware
- Update all protected routes to use the new middleware
- Maintain backward compatibility during a transition period

Show me each file that needs to change before making any edits.
```

---

### Setting Realistic Expectations

**AI coding excels at:**
| Task | Why AI Does It Well |
|---|---|
| Boilerplate code | Highly repetitive; pattern-based |
| CRUD operations | Standard, well-understood patterns |
| Unit test generation | Follows from the function signature |
| Code translation (Python → TypeScript) | Pattern transformation |
| Documentation generation | Structured extraction from code |
| Finding syntax errors | Mechanical pattern matching |

**AI requires careful human oversight for:**
| Task | Why Human Review Is Essential |
|---|---|
| Security-sensitive code | Authentication, authorization, data access |
| Financial or medical logic | Subtle errors have serious consequences |
| Performance-critical paths | AI optimizes for correctness, not efficiency |
| Architectural patterns | AI may implement locally correct but globally inconsistent patterns |
| Anything that touches production data | Irreversible or dangerous without understanding |

---

### The Human Verification Mandate

Every piece of AI-generated code must be reviewed before deployment. This is not bureaucratic caution; it is professional responsibility.

**Code review checklist for AI-generated code:**
- [ ] Does the logic correctly implement the specification?
- [ ] Are edge cases handled correctly?
- [ ] Are there any security vulnerabilities (injection, unvalidated input, exposed secrets)?
- [ ] Is error handling appropriate; does it fail safely?
- [ ] Will this perform acceptably under expected load?
- [ ] Is this maintainable; can another engineer understand and modify it?
- [ ] Does it follow the codebase's conventions and patterns?

---

## Phase 4: Testing

### AI-Powered Test Generation

Given a function, AI can generate a comprehensive test suite including edge cases that humans often miss.

**Test generation prompt:**
```
Here is a function:
[paste function]

Generate a comprehensive test suite using [Jest/pytest/etc.].
Include:
1. Happy path tests for expected inputs
2. Edge cases: empty inputs, null/undefined, boundary values
3. Error cases: invalid types, out-of-range values
4. Performance test: time the function with [N] items

For each test, include a comment explaining what it tests and why.
```

### AI-Assisted Test-Driven Development (TDD)

Reverse the normal flow: describe the behavior first, generate the tests, then implement the function to make the tests pass.

1. *"Write tests for a function that validates a credit card number. Specify exactly what behaviors to test, not the implementation."*
2. Review and adjust the tests; they specify your requirements
3. *"Now implement a function that passes all these tests."*
4. Review the implementation carefully

### Synthetic Test Data

> *"Generate 50 synthetic user records for testing. Include realistic names, valid email formats, US phone numbers, and dates of birth spanning ages 18–65. Ensure diversity in demographics. Return as a JSON array."*

---

## Phase 5: Deployment

### CI/CD Script Generation

```
Generate a GitHub Actions workflow for a Node.js application that:
1. Runs on push to main and on pull requests
2. Installs dependencies (npm ci)
3. Runs unit tests
4. Runs linting (eslint)
5. Builds the application
6. If all steps pass on push to main: deploys to AWS ECS
7. Uses environment secrets for: AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, DOCKER_USERNAME, DOCKER_PASSWORD

Include comments explaining each step.
```

### Infrastructure as Code

```
Write a Terraform configuration to provision:
- An AWS VPC with public and private subnets
- An RDS PostgreSQL instance in the private subnet
- An ECS Fargate cluster
- An Application Load Balancer
- Security groups with minimum necessary permissions

Follow AWS Well-Architected Framework security best practices.
```

---

## Phase 6: Maintenance

### AI-Assisted Debugging

When you have an error you can't explain:
```
I'm getting this error:
[paste error message and stack trace]

Context:
- This happens when [describe the trigger]
- It did not happen before [recent change]
- Environment: [language version, framework, OS]

Analyze the error and:
1. Explain what the error message means
2. List the most likely root causes in order of probability
3. For the top cause, describe how to confirm it and how to fix it
```

### Proactive Refactoring

> *"Review this function and identify: (1) any code smells or anti-patterns, (2) opportunities to improve readability without changing behavior, (3) potential performance improvements. Show me the original and the refactored version side by side."*

### Security Scanning

> *"Review this API endpoint for security vulnerabilities. Specifically check for: SQL injection, XSS, CSRF, authentication bypass, authorization bypass, and sensitive data exposure. For each vulnerability found, explain the risk and how to fix it."*

### Automated Documentation

> *"Generate complete documentation for this module, including: module description, function signatures with parameter types, return value descriptions, usage examples for each public function, and any important constraints or gotchas."*

---

## Token Economics

Understanding how AI models are priced helps you use them cost-effectively in development contexts.

**How tokens work:**
- 1 token ≈ 0.75 words (rough approximation)
- You pay for both input tokens (your prompt + code) and output tokens (AI's response)
- Prices vary by model tier: frontier models (GPT-4o, Claude Sonnet) cost more than smaller models

**Cost control strategies:**

| Strategy | How | Impact |
|---|---|---|
| **Model tiering** | Use smaller models for simple tasks (test generation, documentation), frontier models only for complex reasoning | 5–10x cost reduction |
| **Prompt efficiency** | Avoid redundant context; ask for exactly what you need | 20–40% cost reduction |
| **Caching** | Many APIs support prompt caching; static system prompts cached after first call | Up to 90% reduction on repeated patterns |
| **Batch processing** | Use batch APIs for non-latency-critical tasks | ~50% cost reduction |

**The quality/latency/cost triangle:**
Every AI API call involves a trade-off between three variables. Choose two:
- High quality + low latency → high cost
- High quality + low cost → higher latency
- Low cost + low latency → lower quality

For a production coding assistant: optimize for quality and acceptable latency. For batch documentation generation: optimize for cost.

---

## The AI-Enhanced QA Framework

**AI as First Author → Developer as Reviewer → CI/CD as Gatekeeper**

This three-tier framework brings AI into the quality assurance process while maintaining human accountability:

1. **AI as First Author**: AI generates tests, documentation, and code review suggestions automatically
2. **Developer as Reviewer**: Engineer reviews, modifies, and approves all AI output before it's accepted
3. **CI/CD as Gatekeeper**: Automated pipeline enforces quality gates; tests must pass, coverage must meet threshold, security scans must clear

No AI-generated code or test reaches production without passing all three tiers.

---

## Hands-On Practice

### Exercise 1: Requirements → User Stories

Take a feature you are planning or have recently built. Describe it in 2–3 sentences, then use the user story generation prompt to generate a complete set of stories. Evaluate: what did AI include that you wouldn't have thought of? What did it miss?

---

### Exercise 2: Test Generation

Select a function from your current codebase (or write a simple one). Use the test generation prompt to create a comprehensive test suite. Evaluate: are the tests correct? Do they cover edge cases you would have missed? What needs to be added or corrected?

---

### Exercise 3: Code Review Simulation

Select a piece of code you wrote recently. Use AI to review it for the items in the human verification checklist above. What did it find? What did it miss? How would you use this in a real code review process?

---

### Exercise 4: Debugging with AI

Find a bug in code you are working on (or introduce one deliberately in a test environment). Share the error and context with an LLM using the debugging prompt template. Evaluate: how accurate was the root cause analysis? How useful was the suggested fix?

---

## Summary

| Phase | AI Contribution | Human Role |
|---|---|---|
| **Planning** | User story generation, requirements analysis | Define goals, validate completeness |
| **Design** | Option comparison, UI component generation | Architectural decisions, system trade-offs |
| **Implementation** | Boilerplate, CRUD, test generation | Review all code, handle security and performance |
| **Testing** | Test suite generation, synthetic data | Validate test correctness, edge case judgment |
| **Deployment** | CI/CD scripts, IaC templates | Review configuration, security validation |
| **Maintenance** | Debugging assistance, refactoring, documentation | Root cause judgment, strategic refactoring decisions |

---

## Next Steps

- Continue to [Building Personal AI Agents](building-personal-agents.md) to explore autonomous AI systems
- Integrate AI code review into your next PR workflow
- Experiment with AI test generation on one function in your current project
