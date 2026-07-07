# Contribution 2: Don't show confirmation message in translations UI if there's no message set

**Contribution Number:** 2  
**Student:** Sarah Nasser
**Issue:** https://github.com/civiform/civiform/issues/6007  
**Status:** Phase I Complete

---

## Why I Chose This Issue

I chose this issue because I am interested in web development, especially UI/UX design. I enjoy examining and resolving inconsistencies in a web application's UI/UX design that can confuse users. I fully understand this issue, which is that a confirmation message box always appears in the admin translations UI regardless of whether the admin set a custom confirmation message. This can confuse admins who did not set a custom confirmation message because they would not know whether they should click the confirmation message box. Thus, for clarity purposes, a confirmation message box should appear in the admin translations UI only if the admin set a custom confirmation message. In concrete acceptance criteria, the issue is fixed if a confirmation message box does not appear in the admin translations UI when the custom confirmation message is empty, and if a confirmation message box appears in the admin translations UI when the custom confirmation message is not empty.

This issue is specific and bounded, and I can resolve it within a couple of weeks. The languages for the repository hosting this issue are Java, TypeScript, and HTML. I am skilled in Java and HTML, and despite having no knowledge of TypeScript, I believe I can learn TypeScript within a few days. This issue has not been assigned to anyone, and no one has claimed it. There has been recent maintainer and team member activity in this repository, and no open pull requests are already solving this issue. A commenter in the discussion thread for this issue provided a useful tip on resolving the issue (link to this comment: https://github.com/civiform/civiform/issues/6007#issuecomment-1821719919), and she recommends storing localizedConfirmationMessage as an Optional.empty() when there is no confirmation message. Her tip  would make it easier to determine whether there is actually a confirmation message. Following her tip would also make it easier to exclude the confirmation message box from the UI if there is no confirmation message. Additionally, the project has clear setup documentation that is compatible with my OS. I hope to learn TypeScript and gain more experience in coding with HTML and Java and making open-source contributions.

---

## Understanding the Issue

### Problem Description

[In your own words, what's broken or missing?]

### Expected Behavior

[What should happen?]

### Current Behavior

[What actually happens?]

### Affected Components

[Which parts of the codebase are involved?]

---

## Reproduction Process

### Environment Setup

[Notes on setting up your local development environment - challenges you faced, how you solved them]

### Steps to Reproduce

1. [Step 1]
2. [Step 2]
3. [Observed result]

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:** [If applicable]
- **My findings:** [What you discovered during reproduction]

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]

### Proposed Solution

[High-level description of your fix approach]

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** [Restate the problem]

**Match:** [What similar patterns/solutions exist in the codebase?]

**Plan:** [Step-by-step implementation plan]
1. [Modify file X to do Y]
2. [Add function Z]
3. [Update tests]

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** [How will you verify it works?]

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
