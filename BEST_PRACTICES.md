# Best Practices for Feature-Driven Development

## Core Principles

### 1. Start Small, Grow Incrementally

**Always begin with the smallest possible feature that provides value.**

- Break down large features into minimal viable increments
- Each feature should be independently testable and reviewable
- Resist the temptation to build everything at once
- Small features are easier to understand, debug, and maintain

**Example:**
```
❌ Bad: task implement-complete-user-management-system
✅ Good:
  - task user-registration
  - task user-login
  - task password-reset
  - task user-profile
```

### 2. Little by Little Progress

**Add functionality in small, digestible chunks.**

After each feature:
1. Review every line of code written
2. Ensure you understand the implementation
3. Test thoroughly
4. Document before moving forward
5. Get confirmation before the next step

This approach:
- Reduces cognitive load
- Makes debugging easier
- Allows for course correction early
- Builds understanding progressively

### 3. Understand Every Line

**No errors does NOT mean the code is correct.**

Even when:
- Tests pass
- The feature works from a user perspective
- There are no runtime errors
- The application runs smoothly

**You must still:**
- Understand why each line exists
- Know what each function does
- Comprehend the data flow
- Recognize potential edge cases
- Identify hidden complexity

**Critical Questions to Ask:**
- Why is this implementation chosen?
- What are the trade-offs?
- Are there simpler alternatives?
- What could break in the future?
- Are there security implications?
- How does this interact with existing code?

### 4. Review Before Proceeding

**Before starting the next feature, thoroughly review the current one.**

**Review Checklist:**
- [ ] Read every line of code written
- [ ] Understand the logic and flow
- [ ] Verify error handling is appropriate
- [ ] Check for potential bugs or edge cases
- [ ] Ensure documentation matches implementation
- [ ] Confirm APIs are correctly defined
- [ ] Test the feature manually
- [ ] Consider maintenance implications

**If you cannot explain any part of the code, do not proceed.**

### 5. Avoid Big Features

**Large features are the enemy of understanding.**

**Signs a feature is too big:**
- Takes more than a few hours to implement
- Touches more than 5-10 files
- Requires changes across multiple layers
- Has many interconnected parts
- Is difficult to explain in one sentence

**Solution: Split it!**
- Identify natural boundaries
- Create subtasks following rule #6 from the main rules
- Complete each subtask independently
- Get user confirmation between subtasks

### 6. Code Correctness vs. User Perception

**Working ≠ Correct**

The feature may appear to work perfectly from a user's perspective, but the code might:
- Have memory leaks
- Use inefficient algorithms
- Contain security vulnerabilities
- Be unmaintainable
- Have race conditions
- Lack proper error handling
- Create technical debt

**Always prioritize:**
1. Correctness over speed
2. Understanding over functionality
3. Simplicity over cleverness
4. Maintainability over quick fixes

### 7. The Understanding Test

**Can you explain it to someone else?**

Before marking a feature as complete, you should be able to:
- Explain the implementation in plain language
- Draw a diagram of the data flow
- Describe why alternative approaches were rejected
- Predict how future changes might affect it
- Identify the most complex parts and why they're necessary

**If you cannot do these things, you don't understand the code well enough.**

## Practical Workflow

### Step-by-Step Process

1. **Receive Task**
   - Read and understand the requirements
   - Identify the smallest possible first step
   - If unclear, ask questions

2. **Plan Minimally**
   - Define the smallest feature that provides value
   - Create feature specification
   - Get confirmation before coding

3. **Implement Incrementally**
   - Write minimal code to achieve the feature
   - Test as you go
   - Review each section before moving forward

4. **Understand Deeply**
   - Read every line you wrote
   - Understand every library function you called
   - Know why each decision was made
   - Question anything unclear

5. **Document Thoroughly**
   - Write clear documentation
   - Define APIs precisely
   - Include rationale for complex decisions
   - Make it easy for others (or future you) to understand

6. **Review Completely**
   - Review your own code critically
   - Test edge cases
   - Check for common vulnerabilities
   - Verify documentation accuracy

7. **Confirm and Iterate**
   - Get user confirmation
   - Only then move to the next small feature
   - Repeat the process

## Anti-Patterns to Avoid

### ❌ The "It Works" Fallacy
```
"The tests pass, so the code must be good."
"Users aren't reporting bugs, so it's fine."
"It runs without errors, no need to review."
```
**Why it's wrong:** Hidden bugs, technical debt, and maintainability issues aren't immediately visible.

### ❌ The Big Bang Feature
```
"Let me implement the entire authentication system at once."
"I'll build all CRUD operations in one go."
"Let's add the complete payment flow in this feature."
```
**Why it's wrong:** Overwhelming complexity, difficult to review, hard to debug, easy to miss critical details.

### ❌ The Copy-Paste Syndrome
```
"I found this code online, let me use it."
"This library does what I need, I'll add it."
"Someone else wrote this, so it must be correct."
```
**Why it's wrong:** If you don't understand external code, you can't maintain it, debug it, or ensure it's secure.

### ❌ The Moving Target
```
"While implementing login, let me also add OAuth."
"This needs refactoring, I'll do that too."
"I should add these extra features now."
```
**Why it's wrong:** Scope creep leads to unfocused features, incomplete understanding, and missed requirements.

### ❌ The Trust Fall
```
"The AI generated this code, it should be fine."
"The framework handles that automatically."
"TypeScript will catch any errors."
```
**Why it's wrong:** Tools and automation are helpers, not substitutes for understanding.

## Success Metrics

**You're following best practices when:**

✅ You can explain every line of code you wrote
✅ Each feature is small enough to review in one sitting
✅ Documentation matches implementation perfectly
✅ You spot potential issues before they become bugs
✅ Other developers can easily understand your code
✅ You feel confident maintaining the code in 6 months
✅ Features build on each other logically
✅ You catch misunderstandings early

## Remember

> **Quality > Speed**
>
> **Understanding > Completion**
>
> **Small & Correct > Big & Working**

The goal is not to finish quickly. The goal is to build software that:
- Works correctly
- Is maintainable
- Is understandable
- Is secure
- Is reliable

Take your time. Build incrementally. Understand deeply. Review thoroughly.

**Every line of code is a commitment to future maintenance.**

Make sure you understand what you're committing to.
