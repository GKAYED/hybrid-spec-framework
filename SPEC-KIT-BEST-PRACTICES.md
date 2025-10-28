# Spec Kit best practices guide

> **Learning Path Position:** Advanced - Use this guide after completing Template 1 & 2, when you're ready to scale from learning to production workflows.

## Table of contents

- [When to Transition to Spec Kit](#when-to-transition-to-spec-kit)
- [Understanding Spec Kit's Philosophy](#understanding-spec-kits-philosophy)
- [Getting Started with Spec Kit CLI](#getting-started-with-spec-kit-cli)
- [Best Practices for Using Spec Kit](#best-practices-for-using-spec-kit)
- [Slash Commands Mastery](#slash-commands-mastery)
- [Template Customization](#template-customization)
- [Combining Framework + Spec Kit](#combining-framework--spec-kit)
- [Common Pitfalls to Avoid](#common-pitfalls-to-avoid)
- [Success Metrics](#success-metrics)

---

## When to transition to Spec Kit

**You're ready for Spec Kit when:**

- ✅ You've completed at least 2-3 projects using this framework's templates
- ✅ You understand the value of specifications through hands-on experience
- ✅ Your specs consistently achieve 85%+ adherence across multiple AI models
- ✅ You're starting projects more frequently and need efficiency
- ✅ Your team wants standardized workflows and templates
- ✅ You need version control integration and CI/CD automation

**You should keep using this framework when:**

- 🎓 You're still learning specification-driven development principles
- 🧪 You're experimenting with different spec structures
- 📊 You want to validate specs across multiple AI models
- 🔍 You're reverse-engineering existing projects to extract specs
- 📖 You're teaching others about specification principles

---

## Understanding Spec Kit's philosophy

### Core principles

Spec Kit is built around three fundamental concepts:

#### 1. **Intent-Driven Development**
```
Your specifications should capture WHAT you want, not HOW to build it.
Let the AI handle the implementation details.
```

**Framework Connection:** Our Template 2 teaches you to separate intent from implementation through the conversational → spec extraction process.

#### 2. **Executable Specifications**
```
Specs aren't static documents—they're living instructions that:
- Drive multi-step development workflows
- Enable AI agents to build iteratively
- Provide feedback loops for refinement
```

**Framework Connection:** Our multi-model validation teaches you to measure if specs are truly "executable" by testing with different AI models.

#### 3. **Multi-Phase Refinement**
```
Spec Kit supports three development phases:
- Greenfield: 0-to-1 new projects
- Creative Exploration: Rapid prototyping and experimentation
- Brownfield: Refactoring and improving existing codebases
```

**Framework Connection:** This framework focuses on Greenfield and Creative Exploration phases—learning by building from scratch.

---

## Getting started with Spec Kit CLI

### Installation

```bash
# Install Spec Kit globally
npm install -g @github/specify-cli

# Or use with npx (no installation)
npx @github/specify-cli init
```

### Your first Spec Kit project

**Step 1: Initialize a new project**
```bash
# Navigate to your project directory
cd my-new-project

# Initialize Spec Kit
specify init
```

This creates:
- `.specify/` directory with configuration
- `constitution.md` (core principles)
- `specification.md` (technical requirements)
- `plan.md` (implementation strategy)
- `tasks.md` (actionable todos)

**Step 2: Customize your constitution**

The constitution defines YOUR project's rules. Start with these questions:

```markdown
# constitution.md

## Project identity
- What is this project's single most important goal?
- What makes this project unique?

## Technical principles
- What technologies MUST be used? (e.g., "Always use SQLite for data storage")
- What patterns MUST be followed? (e.g., "All components must be tested")
- What should be AVOIDED? (e.g., "No premature abstraction")

## Quality standards
- What defines "done" for a feature?
- What level of documentation is required?
- How should errors be handled?
```

**Framework Connection:** Use your Template 2 constitutional articles as a starting point! Copy the principles that worked well.

**Step 3: Write your specification**

```markdown
# specification.md

## Overview
[Brief description of what you're building]

## Core features
1. Feature A - [What it does, not how to build it]
2. Feature B - [Focus on user outcomes]
3. Feature C - [Describe the value, not the code]

## Data model
[Define your entities and relationships]

## User interactions
[Describe workflows from user perspective]

## Non-Functional Requirements
- Performance: [Expected response times]
- Security: [Authentication, data protection]
- Scalability: [Growth expectations]
```

**Step 4: Use Spec Kit's AI agent integration**

```bash
# Start an AI-powered development session
specify chat

# The AI will read your constitution, specification, plan, and tasks
# and help you build according to your rules
```

---

## Best practices for using Spec Kit

### 1. **Start with a Strong Constitution**

Your constitution is the "operating system" for your project. Invest time upfront to define:

✅ **DO:**
- Write specific, testable principles ("All functions must have JSDoc comments")
- Include examples of good vs bad code
- Reference specific libraries/frameworks by name
- Update the constitution when you discover new patterns

❌ **DON'T:**
- Write vague principles ("Code should be clean")
- Copy generic best practices that don't fit your project
- Lock yourself into decisions too early—constitutions can evolve
- Forget to document WHY a principle exists

**Example from our AI Agent experiment:**

```markdown
## Article I: Library-first development
When a task can be solved with a well-maintained library, we MUST use the library.

Why: Our AI agent project validated this—implementations using libraries 
(rss-parser, cheerio) achieved 95% spec adherence vs 40% for custom parsers.

Approved Libraries:
- RSS parsing: rss-parser
- Web scraping: cheerio
- Database: better-sqlite3
```

### 2. **Make Specifications Measurable**

Every requirement should have clear success criteria:

✅ **Good Specification:**
```markdown
## RSS feed processing
The system shall fetch RSS feeds and extract articles with the following success criteria:
- Fetch at least 10 feeds in under 30 seconds
- Extract title, URL, date, and description from 95%+ of articles
- Handle feed errors gracefully (log and continue processing)
- Store deduplicated articles in SQLite database
```

❌ **Poor Specification:**
```markdown
## RSS feed processing
The system should be able to get RSS feeds and save them.
```

**Framework Connection:** Use the validation checklist from Template 2 to ensure specs are measurable before importing to Spec Kit.

### 3. **Use the Plan as Your Thinking Tool**

`plan.md` is where you break down HOW to implement your specification:

```markdown
# plan.md

## Phase 1: Core Infrastructure (Week 1)
**Goal:** Set up database and configuration system

Tasks:
1. Create SQLite schema for articles table
2. Implement config.js with environment variables
3. Write database initialization script

**Acceptance Criteria:**
- Database file created on first run
- Config loads from .env file
- Unit tests pass

## Phase 2: RSS Processing (Week 2)
...
```

**Pro Tip:** Use your Template 1 initial build as the prototype for Phase 1. You've already validated it works!

### 4. **Keep Tasks Atomic**

Each task in `tasks.md` should be completable in 1-4 hours:

✅ **Good Task:**
```markdown
- [ ] Implement RSS feed fetcher using rss-parser library
  - Input: Array of feed URLs from config
  - Output: Array of parsed articles
  - Error handling: Log failed feeds, continue processing
  - Test: Mock HTTP responses with sample RSS XML
```

❌ **Poor Task:**
```markdown
- [ ] Build the RSS system
```

### 5. **Version Control Your Specs**

Your `.specify/` directory should be committed to git alongside your code:

```bash
git add .specify/
git commit -m "Update specification: Add web scraping feature"
```

**Why:** Specs evolve as you learn. Version control lets you:
- See how requirements changed over time
- Rollback to previous specs if needed
- Collaborate on specification changes via pull requests
- Track correlation between spec changes and code quality

### 6. **Use Slash Commands Strategically**

Spec Kit supports slash commands during AI chat sessions. Master these:

| Command | When to Use | Example |
|---------|-------------|---------|
| `/constitution` | Remind AI of core principles mid-conversation | "/constitution - Should we add error logging?" |
| `/specification` | Clarify if a feature request aligns with specs | "/specification - Is pagination mentioned?" |
| `/plan` | Check if current task fits the roadmap | "/plan - What phase are we in?" |
| `/tasks` | Review next actionable items | "/tasks - What's the priority?" |
| `/update [file]` | Modify a specification file | "/update specification.md - Add pagination" |

**Pro Tip:** Use `/constitution` frequently! It's easy for AI conversations to drift from your core principles.

---

## Slash commands mastery

### Command reference

#### `/constitution`
**Purpose:** Display your project's core principles and rules.

**When to use:**
- Starting a new feature to ground the conversation
- When AI suggests a solution that might violate principles
- During code review to verify adherence

**Example workflow:**
```
You: "I want to add caching to improve performance"
AI: [Suggests in-memory caching with Redis]
You: "/constitution"
AI: [Displays Article I: Library-First, Article VIII: Use SQLite for all persistence]
You: "Based on our constitution, should we use SQLite for caching instead?"
AI: "Yes! Here's how to implement a cache table in SQLite..."
```

#### `/specification`
**Purpose:** Reference the full technical specification.

**When to use:**
- Clarifying feature boundaries
- Checking if a requirement already exists
- Validating that new ideas align with existing specs

**Example workflow:**
```
You: "Can we add email notifications when new articles arrive?"
You: "/specification"
AI: [Shows specification doesn't mention notifications]
You: "This would be a new feature. Should we update the spec first?"
AI: "Recommended. Here's a draft specification section..."
```

#### `/plan`
**Purpose:** Review the implementation roadmap.

**When to use:**
- Prioritizing what to build next
- Checking if you're ahead/behind schedule
- Deciding if a new task fits current phase

**Example workflow:**
```
You: "/plan - What should I work on next?"
AI: "You're in Phase 2: RSS Processing. Next priority task is implementing 
     the deduplication algorithm (Task 2.3 in tasks.md)"
```

#### `/tasks`
**Purpose:** List actionable todo items.

**When to use:**
- Starting a coding session
- Marking tasks complete
- Breaking down a complex task

**Example workflow:**
```
You: "/tasks - Show incomplete tasks"
AI: [Lists 5 open tasks]
You: "I completed task 2.3. Mark it done and show me task 2.4 details"
AI: [Updates tasks.md and provides detailed context for next task]
```

#### `/update [file]`
**Purpose:** Modify specification files during development.

**When to use:**
- You discover new requirements
- A principle should be added/modified
- The plan needs adjustment based on learnings

**Example workflow:**
```
You: "We need to add a rate limiting principle to avoid hammering RSS servers"
You: "/update constitution.md"
AI: "I'll add Article X: Rate Limiting. Here's a draft:

## Article X: Respectful rate limiting
- Wait 1 second between feed fetches
- Implement exponential backoff for errors
- Cache results for 15 minutes minimum

Shall I commit this to constitution.md?"
```

### Advanced slash command patterns

#### Pattern 1: The Constitution Check
Before implementing any significant feature:
```
1. You: "/constitution"
2. [Review principles]
3. You: "/specification - Does this feature align?"
4. [If yes] You: "/plan - Where does it fit?"
5. [If yes] You: "/tasks - Create task for this"
```

#### Pattern 2: The Spec Drift Detector
When AI suggests something that feels "off":
```
1. AI: "Let's add a MongoDB database for better scalability"
2. You: "/constitution"
3. AI: [Shows Article I: Always use SQLite]
4. You: "This violates our constitution. Propose an SQLite solution."
```

#### Pattern 3: The Living Documentation Flow
As you learn during development:
```
1. You: [Discover that feed parsing needs custom error handling]
2. You: "/update specification.md - Add error handling requirements"
3. AI: [Drafts new section]
4. You: "/update plan.md - Add error handling task to Phase 2"
5. You: "/tasks - Create task: Implement RSS error handling"
```

---

## Template customization

### Creating organization-wide templates

If you're on a team, create shared templates in your organization:

**Step 1: Create a template directory**
```bash
mkdir -p ~/.specify/templates/my-org-template
cd ~/.specify/templates/my-org-template
```

**Step 2: Define your template structure**
```
my-org-template/
├── constitution.md          # Your org's standard principles
├── specification.md         # Template with sections
├── plan.md                  # Standard phase structure
├── tasks.md                 # Task template with categories
└── .specify-template.json   # Metadata
```

**Step 3: Write `.specify-template.json`**
```json
{
  "name": "My Org Web App Template",
  "description": "Standard template for internal web applications",
  "version": "1.0.0",
  "author": "Engineering Team",
  "tags": ["web", "internal", "node.js"]
}
```

**Step 4: Use the template**
```bash
specify init --template my-org-template
```

### Template best practices

**1. Include Placeholder Sections**
```markdown
# specification.md (Template)

## Overview
[FILL IN: 2-3 sentence project description]

## Core features
[FILL IN: List 3-5 primary features]

## Data model
[FILL IN: Define entities and relationships]
```

**2. Provide Examples in Comments**
```markdown
# constitution.md (Template)

## Article I: [Your Principle Name]
[Describe the principle]

<!-- Example:
## Article I: Library-first development
When solving a common problem, prefer well-maintained libraries over custom code.

Approved libraries:
- HTTP requests: axios
- Testing: jest
- Date handling: date-fns
-->
```

**3. Version Your Templates**
Track template changes so teams can adopt updates:
```bash
git tag v1.0.0 -m "Initial web app template"
git push --tags
```

---

## Combining framework + Spec Kit

### The hybrid workflow

Use both tools in sequence for maximum learning and efficiency:

#### Phase 1: Learning (Use This Framework)
**Tools:** Template 1 + Template 2  
**Duration:** 2-4 projects  
**Goal:** Build intuition for what makes good specifications

```
1. Pick a small project (e.g., todo app, RSS reader)
2. Use Template 1 to build conversationally with an AI
3. Use Template 2 to extract specifications from the conversation
4. Validate specs with 2-3 AI models
5. Measure adherence (aim for 85%+)
6. Reflect: What made the spec effective or ineffective?
```

**You'll learn:**
- How much detail specs need
- Which principles actually matter
- How different AI models interpret instructions
- What causes specification failures

#### Phase 2: Transition (Hybrid Approach)
**Tools:** This Framework + Spec Kit  
**Duration:** 2-3 projects  
**Goal:** Apply learnings to Spec Kit workflows

```
1. Use Template 2 to draft initial specifications
2. Validate with multi-model testing (framework approach)
3. Import refined specs into Spec Kit
4. Use Spec Kit's slash commands for development
5. Continue multi-model validation on final code
```

**You'll learn:**
- How to translate framework specs to Spec Kit format
- Which Spec Kit features provide most value
- How to customize constitutions effectively

#### Phase 3: Production (Use Spec Kit)
**Tools:** Spec Kit CLI + Templates  
**Duration:** Ongoing  
**Goal:** Efficient, standardized specification-driven development

```
1. specify init --template [your-org-template]
2. Customize constitution based on project needs
3. Write specifications (now you know what works!)
4. Use specify chat for AI-powered development
5. Periodically validate with multiple models (framework approach)
```

**You'll benefit from:**
- Fast project initialization
- Standardized team workflows
- CI/CD integration
- Version-controlled specifications

### When to return to the framework

Even after adopting Spec Kit, use this framework for:

- **Experimentation:** Testing new constitutional principles before standardizing
- **Quality Audits:** Multi-model validation of critical specifications
- **Training:** Teaching new team members specification principles
- **Post-Mortems:** Analyzing why a project didn't meet expectations

---

## Common pitfalls to avoid

### 1. **Over-Specification in Constitution**

❌ **Problem:**
```markdown
## Article I: Code Style
- Use 2 spaces for indentation
- Maximum line length: 80 characters
- Use single quotes for strings
- Add semicolons at end of statements
- Use camelCase for variables
[...50 more style rules]
```

✅ **Solution:**
```markdown
## Article I: Code Style
Follow the project's .eslintrc and .prettierconfig for style.

Key principle: Consistency over personal preference.
```

**Why:** Constitutions should focus on *architectural* principles, not linting rules. Let automated tools handle style.

### 2. **Vague Specifications**

❌ **Problem:**
```markdown
## Feature: User Management
The app should have user accounts and authentication.
```

✅ **Solution:**
```markdown
## Feature: User Management

**Authentication:**
- Users register with email + password
- Passwords hashed with bcrypt (min 12 rounds)
- JWT tokens for session management (24hr expiry)
- Forgot password flow via email

**Authorization:**
- Role-based: admin, editor, viewer
- Admins can CRUD all resources
- Editors can CRUD own resources
- Viewers read-only access

**Acceptance Criteria:**
- New user can register in <2 seconds
- Login failure shows generic error (security)
- Password reset email arrives in <5 minutes
```

### 3. **Not Using Slash Commands**

❌ **Problem:** Long AI conversation drifts from original specifications.

✅ **Solution:** Use `/constitution` every 5-10 messages to re-ground the AI.

### 4. **Forgetting to Update Specs**

❌ **Problem:** Your code evolves but specifications stay frozen.

✅ **Solution:** 
```bash
# After completing a feature
specify chat "/update specification.md - Document feature X as implemented"
git add .specify/
git commit -m "docs: Update specs for feature X"
```

### 5. **Skipping the Plan**

❌ **Problem:** Jumping straight from specification to code.

✅ **Solution:** Always populate `plan.md` with phases, milestones, and acceptance criteria. It's your roadmap.

---

## Success metrics

### How to measure Spec Kit effectiveness

Track these metrics to know if you're using Spec Kit well:

#### 1. **Specification Stability**
```
Spec Changes Per Week = (# of specification.md commits) / (weeks since project start)

Target: <2 changes per week after initial setup
```

**What it means:** Frequent spec changes suggest you're discovering requirements late. Good specs stabilize after initial drafting.

#### 2. **AI Adherence Rate**
```
Adherence Rate = (Features implemented correctly) / (Total features) × 100%

Target: 85%+ across multiple AI models
```

**How to measure:** Use this framework's multi-model validation on Spec Kit projects!

#### 3. **Task Completion Velocity**
```
Velocity = (Tasks completed this week) / (Tasks completed last week)

Target: Consistent velocity (1.0) or improving (>1.0)
```

**What it means:** If velocity drops, your tasks might be too large or specs too vague.

#### 4. **Constitutional Violations**
```
Violations = (# of code reviews requesting changes for principle violations)

Target: <1 violation per 10 pull requests
```

**How to track:** Tag PR comments that cite constitutional violations.

#### 5. **Time to First Working Feature**
```
Time to First Feature = (Hours from 'specify init' to first deployable feature)

Target: <8 hours for simple projects, <40 hours for complex
```

**Benchmark:** Compare against your Template 1 projects. Spec Kit should be faster after the learning curve.

---

## Next steps

### Immediate actions

1. **Install Spec Kit**
   ```bash
   npm install -g @github/specify-cli
   ```

2. **Create Your First Spec Kit Project**
   ```bash
   mkdir my-spec-kit-test
   cd my-spec-kit-test
   specify init
   ```

3. **Import Your Best Template 2 Spec**
   - Take a project where you achieved 85%+ adherence with this framework
   - Copy its constitutional articles to `constitution.md`
   - Copy its specification to `specification.md`
   - Use Spec Kit to rebuild it from scratch

4. **Compare Results**
   - Time how long it takes with Spec Kit vs Template 1
   - Test final code with multiple AI models (framework approach)
   - Measure if Spec Kit improved your velocity or quality

### Learning resources

- **Official Spec Kit Docs:** [github.com/github/spec-kit](https://github.com/github/spec-kit)
- **Framework Templates:** Use Template 1 & 2 as Spec Kit prep work
- **Example Projects:** See `implementations/` in the [ai-agent-spec experiment](https://github.com/GKAYED/ai-agent-spec)

### Community

Share your learnings:
- What constitutional principles worked best?
- How did Spec Kit change your development speed?
- What specifications achieved highest AI adherence?

**Framework Philosophy:** This guide exists to help you graduate FROM learning WITH this framework TO producing WITH Spec Kit. Use both tools where they shine—framework for education and validation, Spec Kit for efficiency and scale.

---

## Appendix: Quick reference

### Spec Kit commands cheatsheet
```bash
specify init                      # Initialize new project
specify init --template [name]    # Use a template
specify chat                      # Start AI development session
specify validate                  # Check spec file validity
specify export                    # Export specs to markdown
```

### Slash commands cheatsheet
```
/constitution          # Display core principles
/specification         # Show full technical spec
/plan                  # View implementation roadmap
/tasks                 # List actionable todos
/update [file]         # Modify a spec file
```

### File structure reference
```
.specify/
├── constitution.md      # Core principles and rules
├── specification.md     # Technical requirements
├── plan.md              # Implementation roadmap
└── tasks.md             # Actionable todo list
```

### Framework → Spec Kit Mapping
| Framework Document | Spec Kit File | Purpose |
|-------------------|---------------|---------|
| Constitutional Articles (Template 2) | `constitution.md` | Project principles |
| Specification Extraction (Template 2) | `specification.md` | Technical requirements |
| Implementation Plan (Template 2) | `plan.md` | Development roadmap |
| Validation Checklist (Template 2) | `tasks.md` | Actionable items |

---

**Ready to scale your specification-driven development?** Start with `specify init` and remember: you've already validated these principles through hands-on learning. Now make them efficient.
