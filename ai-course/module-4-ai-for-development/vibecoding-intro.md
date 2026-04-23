# Vibecoding: Build Software by Describing It

A practical introduction to conversational software development: building functional applications by describing what you want in plain English, with or without a traditional coding background.

---

## What You Will Learn

- Understand what vibecoding is and why it's a genuine shift in how software gets made
- Use the leading vibecoding platforms to build functional applications from descriptions
- Apply a structured workflow for going from idea to working product
- Recognize the limitations of vibecoding and know when to bring in an engineer
- Use AI coding assistants within traditional development environments

---

## What Is Vibecoding?

In early 2025, AI researcher Andrej Karpathy coined the term "vibecoding" to describe a new way of building software: instead of writing code line-by-line, you describe what you want in natural language and let AI generate and iterate on the implementation.

The name is deliberately playful. The "vibe" is your intent: the feeling, behavior, and purpose of what you're building. The "coding" part happens largely automatically.

This is not magic, and it does not make traditional software engineering obsolete. But it does represent a genuine expansion of who can build software, what small teams can accomplish, and how fast ideas can be validated.

> **Key Insight:** Vibecoding is best understood as a new rung on the ladder of abstraction. Just as spreadsheets enabled financial analysis without custom database programming, and no-code tools enabled websites without HTML knowledge, vibecoding enables functional software applications without traditional coding skills.

---

## Who Is Vibecoding For?

**Non-engineers who want to build:**
- Startup founders who want to validate product ideas before hiring a development team
- Product managers who want to prototype features and test them with users
- Entrepreneurs who want to build internal tools without a technical co-founder
- Researchers who need custom data tools that don't exist as SaaS products

**Engineers who want to move faster:**
- Senior developers who want to scaffold new applications instantly
- Full-stack developers who want AI to handle boilerplate while they focus on architecture
- Teams that want to prototype and validate before investing in production engineering

---

## The Leading Vibecoding Platforms

| Platform | Best For | Key Strength |
|---|---|---|
| **Bolt.new** | Full-stack web apps; React/Node applications | Fastest from prompt to working app; strong for web |
| **Lovable** | Consumer and SaaS product prototypes | Clean UI; built-in design system; strong for MVPs |
| **Replit Agent** | Applications with database and backend needs | Handles deployment; strong for full-stack with data |
| **v0 by Vercel** | UI components and frontend interfaces | Beautiful, production-ready React components |
| **Cursor** | Engineers who want AI-powered code editing | Best IDE-integrated experience; works on existing codebases |
| **GitHub Copilot** | Enterprise developers; IDE integration | Deep GitHub integration; broad language support |
| **Claude** (Anthropic) | Complex logic, debugging, architecture discussion | Best for reasoning through technical problems |

---

## The Vibecoding Workflow

### Step 1: Define the Vibe

Before you write a single prompt, be precise about what you're building. The more specific your initial description, the closer the first output will be to what you want.

Write a one-paragraph product brief that answers:
- What does this application do?
- Who uses it and what problem does it solve?
- What are the 3–5 core features?
- What should it look like (minimal/modern, data-heavy, mobile-first)?

**Example brief:**
> *"A time tracking tool for freelancers. Users can log time entries with a project name, description, and hourly rate. The app calculates total earnings per project per month and exports a summary as a PDF. Clean, minimal interface. Mobile-friendly."*

---

### Step 2: Generate the First Version

Paste your product brief into your chosen vibecoding platform. Most platforms will:
1. Interpret your description and plan the implementation
2. Generate the application code
3. Launch a live preview you can interact with immediately

Run this in Bolt.new:
> *"Build a [paste your product brief]. Use React for the frontend. Make it responsive and clean."*

The first output is rarely exactly what you want. That is expected. Treat it as a starting point.

---

### Step 3: Iterate Through Conversation

This is where vibecoding becomes a dialogue. You interact with the application, note what's wrong or missing, and describe changes in plain language.

**Effective iteration prompts:**
- *"The 'Add Entry' button should be more prominent. Move it to the top right."*
- *"When I click Save, it should show a success message and clear the form."*
- *"Add a summary section at the top showing total hours and total earnings for the current month."*
- *"The color scheme feels too corporate. Make it friendlier; use a softer blue and some rounded corners."*

**What works well in vibecoding iteration:**
- Visual changes (layout, color, size, position)
- Adding or removing features
- Changing flow (what happens after a user action)
- Simple data transformations (calculations, filters, sorts)

**What requires more care:**
- Complex business logic (always verify the logic is correct, not just that it runs)
- Security-sensitive features (authentication, data access controls)
- Performance optimization for scale

---

### Step 4: Test Thoroughly

Vibecoded applications can look correct while having logic errors that only surface through use. Test by:

1. **Happy path testing**: Does the core workflow work end-to-end?
2. **Edge case testing**: What happens with empty inputs, very long text, or unusual data?
3. **Cross-device testing**: Does it work on mobile? On different screen sizes?
4. **Data persistence**: If the app stores data, does it persist correctly after refresh?

When you find bugs, describe them precisely:
> *"When I enter a project name with a comma in it, the export breaks. Fix this."*

---

### Step 5: Know When to Stop (or Call an Engineer)

Vibecoding is excellent for early-stage validation and internal tools. It has real limits for production-grade systems.

**Signs you should involve a professional engineer:**
- The application needs to handle sensitive user data or payments
- You need more than a few hundred concurrent users
- You're encountering security requirements (GDPR, HIPAA, SOC2)
- The application needs deep integration with complex external systems
- You've hit a bug that vibecoding cannot resolve after 3–4 attempts

> **Rule of thumb:** Vibecoding is for discovering *what* to build. Professional engineering is for building it to last.

---

## AI Coding Assistants for Engineers

For engineers who want AI within a professional development workflow, the tools are more sophisticated.

### Cursor: The AI-Native Code Editor

Cursor is a code editor built around AI assistance. Unlike adding an AI plugin to an existing editor, Cursor's AI is architectural; it understands your full codebase, not just the current file.

**Key Cursor capabilities:**
- **Composer**: Describe a multi-file change in natural language; Cursor implements it across the whole codebase
- **Tab completion**: Context-aware completions that understand the entire project
- **Chat**: Ask questions about any part of your codebase and get accurate, context-aware answers
- **Edit mode**: Select any block of code and give natural language instructions to change it

**Cursor workflow for adding a feature:**
1. Open Composer (Cmd+I)
2. Describe the feature: *"Add a user authentication system using email/password. Include login, logout, and password reset flows. Use our existing database models."*
3. Review every file Cursor proposes to create or modify
4. Accept, reject, or request changes for each
5. Run tests and review the implementation

---

### GitHub Copilot

Copilot integrates into VS Code, JetBrains, and other editors. It works at the inline completion level; as you type, it suggests completions ranging from a single line to entire functions.

**Most valuable for:**
- Boilerplate reduction (writing the same pattern for the fifth time in a project)
- Test generation (given a function, generate the unit tests)
- Documentation (given a function, write the docstring)
- Language translation (convert a Python function to TypeScript)

---

### The Mental Model for AI-Assisted Engineering

> *"Think of AI as a skilled junior developer on your team, not a senior engineer. It's brilliant at execution but needs clear direction, thorough review, and cannot be trusted to make architectural decisions independently."*

**What AI does well:**
- Implementing well-defined functions based on a clear specification
- Writing tests for existing code
- Finding syntax errors and common bug patterns
- Explaining what existing code does
- Translating code between languages or frameworks

**What requires human expertise:**
- System architecture and technical decision-making
- Security review of AI-generated code
- Performance optimization under real-world load
- Code that handles edge cases safely (financial transactions, medical data)

---

## Hands-On Practice

### Exercise 1: Your First Vibecoded App

Choose a simple tool you wish existed. Write a one-paragraph product brief. Use Bolt.new or Lovable to build it.

Suggestions if you're stuck:
- A word counter and reading-time estimator
- A simple habit tracker
- A meeting cost calculator (number of people × hourly rate × meeting length)
- A random team name generator

Iterate through at least three changes after the first version.

---

### Exercise 2: Feature Addition

Take the app from Exercise 1. Add two features through conversation:
1. A feature you specified but that wasn't implemented exactly as you envisioned
2. A feature you didn't initially plan but realized you wanted while using it

How many iterations did each feature take?

---

### Exercise 3: Copilot or Cursor Test (for engineers)

If you have a Cursor or Copilot license:
1. Open an existing project
2. Use the chat/composer to ask: *"What are the most complex or risky parts of this codebase? Explain what they do and why they're complex."*
3. Select a function you know well and ask AI to explain it; is the explanation accurate?
4. Ask AI to write a unit test for one function; evaluate its correctness

---

### Exercise 4: Limitation Testing

Deliberately test the limits of vibecoding with your app from Exercise 1:
1. Try to break it: empty inputs, special characters, long strings
2. Try to add a feature that seems simple but is actually complex (e.g., "now add user accounts and let multiple people share this")
3. Document where the vibecoding approach succeeded and where it fell short

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **What vibecoding is** | Building functional software by describing it in natural language: a new rung on the abstraction ladder |
| **Who it's for** | Both non-engineers (prototyping, validation, internal tools) and engineers (faster scaffolding, boilerplate reduction) |
| **Core workflow** | Define the vibe → Generate → Iterate through conversation → Test → Know when to stop |
| **Leading platforms** | Bolt.new (web apps), Lovable (MVPs), Replit Agent (full-stack), v0 (UI components), Cursor (engineers) |
| **Real limits** | Security, scale, complex integrations, and production reliability require professional engineering |

---

## Next Steps

- Continue to [AI Across the Software Development Lifecycle](ai-in-the-sdlc.md) to understand how AI integrates into professional software engineering
- Build your first vibecoded app this week using Bolt.new or Lovable
- If you're an engineer, install Cursor or Copilot and use it for your next coding task
