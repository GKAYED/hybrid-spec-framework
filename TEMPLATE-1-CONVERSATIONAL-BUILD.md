# Template 1: Conversational AI Build (Prototyping Phase)

**Purpose**: Build a minimum viable implementation through conversational prompting to establish core functionality, then refine to a satisfactory baseline before specification extraction.

---

## 🎯 Goal Setting (Start Here)

Before you begin, define your project clearly:

```markdown
PROJECT NAME: [Your project name]

CORE PURPOSE: [One sentence describing what this does]

PRIMARY USER: [Who uses this and why]

SUCCESS CRITERIA: [What does "working" mean?]
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3
```

---

## 📋 Phase 1: Initial Build Prompt (Minimum Viable Features)

**Instructions**: Use this template to prompt your AI model. Fill in the bracketed sections with your specific requirements.

### Initial Prompt Template

```
I want to build [PROJECT NAME] - a [TYPE OF APPLICATION] that [CORE PURPOSE].

**Core Functionality (Minimum Features):**
1. [First essential feature - be specific about inputs/outputs]
2. [Second essential feature - describe the user interaction]
3. [Third essential feature - define the expected behavior]

**Technical Stack Preference:**
- Backend: [e.g., Node.js/Express, Python/Flask, etc.]
- Frontend: [e.g., React, Vue, vanilla HTML/JS, etc.]
- Database: [e.g., SQLite, PostgreSQL, MongoDB, or "suggest best option"]
- Deployment: [e.g., Docker, local development only, etc.]

**Non-Negotiables:**
- [e.g., "Must work offline", "Must be fast (<100ms response)", "Must handle 1000+ items"]
- [e.g., "Simple setup - no complex dependencies"]
- [e.g., "Clear error messages for users"]

**What I DON'T need yet:**
- [e.g., "Authentication/login"]
- [e.g., "Advanced filtering"]
- [e.g., "Mobile responsiveness"]

Please implement this as a complete, working application with:
- Clear file structure
- Basic documentation (README with setup instructions)
- Sample data or test cases to verify it works

Start with the most straightforward implementation. We'll refine after I see it running.
```

---

## 🔄 Phase 2: Review & Refinement Prompts

After your initial build is running, use these prompts to improve specific areas:

### Refinement Prompt 1: Core Functionality Enhancement

```
The [FEATURE NAME] is working, but I'd like to enhance it:

CURRENT BEHAVIOR:
[Describe what it does now]

DESIRED BEHAVIOR:
[Describe what you want it to do]

SPECIFIC REQUIREMENTS:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

Please update the implementation while maintaining backward compatibility with existing functionality.
```

### Refinement Prompt 2: Error Handling & Edge Cases

```
I've tested the application and found these edge cases that need handling:

SCENARIO 1: [Describe what breaks or behaves unexpectedly]
Expected: [What should happen]
Actual: [What happens now]

SCENARIO 2: [Another edge case]
Expected: [What should happen]
Actual: [What happens now]

Please add robust error handling, input validation, and user-friendly error messages for these cases.
```

### Refinement Prompt 3: Performance & UX Polish

```
The functionality is solid. Now I want to improve the user experience:

PERFORMANCE:
- [e.g., "Loading feels slow - can we add loading indicators?"]
- [e.g., "Can we cache results to avoid re-fetching?"]

UX IMPROVEMENTS:
- [e.g., "Add visual feedback when actions complete"]
- [e.g., "Show empty states with helpful messages"]
- [e.g., "Make the interface more intuitive for [specific user action]"]

VISUAL POLISH:
- [e.g., "Improve the layout/styling"]
- [e.g., "Add icons or visual indicators"]
- [e.g., "Make it look professional, not prototype-y"]

Please implement these improvements while keeping the core functionality intact.
```

---

## ✅ Phase 3: Validation Checklist

Before moving to specification extraction, verify your application meets these criteria:

### Functional Completeness
- [ ] All core features work as expected
- [ ] Edge cases are handled gracefully
- [ ] Error messages are clear and helpful
- [ ] Sample/test data demonstrates all functionality

### Code Quality
- [ ] File structure is logical and organized
- [ ] Code is reasonably clean (not necessarily perfect)
- [ ] No obvious bugs or crashes
- [ ] Dependencies are documented

### Documentation
- [ ] README exists with setup instructions
- [ ] Key functionality is explained
- [ ] Running the app is straightforward
- [ ] Any configuration is documented

### User Experience
- [ ] Interface is intuitive (for your target user)
- [ ] Loading states are visible
- [ ] Actions provide feedback
- [ ] It "feels" complete, not prototype-y

---

## 🎓 Pro Tips for Conversational Building

### 1. **Start Stupidly Simple**
Don't try to build everything at once. Get ONE feature working perfectly before adding more.

**Bad**: "Build a social media platform with posts, comments, likes, notifications, and chat"
**Good**: "Build a system to create and display posts. We'll add interactions later."

### 2. **Be Specific About Inputs and Outputs**
Vague requests get vague results.

**Bad**: "Add a search feature"
**Good**: "Add a search box that filters posts by title in real-time as I type, showing 'No results found' if nothing matches"

### 3. **Reference Existing Behavior**
Connect new features to what already works.

**Example**: "The current post list shows 10 items. Add pagination buttons at the bottom that work the same way, loading 10 more items per page."

### 4. **Test Immediately After Each Change**
Don't stack multiple refinements before testing. Verify each change works before moving on.

### 5. **Know When to Stop Refining**
You're ready for spec extraction when:
- Core features work reliably
- You'd be comfortable showing this to someone
- Adding more features feels like "nice to have" not "must have"
- The implementation represents your vision (even if not perfect)

---

## 📝 What You Should Have at the End

Before moving to Template 2 (Spec Extraction), you should have:

1. **A Working Application**
   - Runs without errors
   - Demonstrates all core functionality
   - Has basic documentation

2. **Clear Understanding of What You Built**
   - You can explain what each feature does
   - You know why you made key technical decisions
   - You understand the data flow

3. **Confidence in the Approach**
   - This implementation represents a valid solution
   - It's not perfect, but it's "good enough" to formalize
   - You'd use this architecture if building from scratch

4. **A Mental Model of Success**
   - You know what "correct" looks like
   - You can articulate what matters vs what doesn't
   - You have acceptance criteria in your head

---

## 🚀 Next Step

Once your conversational build is satisfactory, proceed to **Template 2: Specification Extraction** to formalize your knowledge into AI-readable specifications that can reproduce this project.

**Why This Matters**: You're not just building one implementation—you're creating executable specifications that can generate infinite implementations across different AI models, tech stacks, and use cases.

**Spec Kit Users**: If you're familiar with GitHub Spec Kit, you can alternatively use `/speckit.specify` and `/speckit.plan` commands to formalize your work. This conversational approach is compatible with and complementary to Spec Kit's workflow.

---

## 🎓 Learn More

- **[Framework Overview](./FRAMEWORK-QUICKSTART.md)** - Understand how this fits into spec-driven development
- **[Template 2: Specification Extraction](./TEMPLATE-2-SPEC-EXTRACTION.md)** - Next phase of the framework
- **[GitHub Spec Kit](https://github.com/github/spec-kit)** - Official toolkit for spec-driven development

---

**Remember**: The goal isn't perfection—it's a solid baseline that captures your intent. You're building the "reference implementation" that specifications will describe.
