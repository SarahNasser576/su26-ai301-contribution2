# Contribution 2: Creating a new user, non-translated error key

**Contribution Number:** 2  
**Student:** Sarah Nasser \
**Issue:** https://github.com/ls1intum/Artemis/issues/12187
**Status:** Phase I Complete

---

## Why I Chose This Issue

I chose this issue because I am interested in web development, especially UI/UX design. I enjoy examining and resolving inconsistencies in a web application's UI/UX design that can confuse users. I fully understand this issue, which is that a confirmation message box always appears in the admin translations UI regardless of whether the admin set a custom confirmation message. This can confuse admins who did not set a custom confirmation message because they would not know whether they should click the confirmation message box. Thus, for clarity purposes, a confirmation message box should appear in the admin translations UI only if the admin set a custom confirmation message. In concrete acceptance criteria, the issue is fixed if a confirmation message box does not appear in the admin translations UI when the custom confirmation message is empty, and if a confirmation message box appears in the admin translations UI when the custom confirmation message is not empty.

This issue is specific and bounded, and I can resolve it within a couple of weeks. The languages for the repository hosting this issue are Java, TypeScript, and HTML. I am skilled in Java and HTML, and despite having no knowledge of TypeScript, I believe I can learn TypeScript within a few days. This issue has not been assigned to anyone, and no one has claimed it. There has been recent maintainer and team member activity in this repository, and no open pull requests are already solving this issue. A commenter in the discussion thread for this issue provided a useful tip on resolving the issue (link to this comment: https://github.com/civiform/civiform/issues/6007#issuecomment-1821719919), and she recommends storing localizedConfirmationMessage as an Optional.empty() when there is no confirmation message. Her tip  would make it easier to determine whether there is actually a confirmation message. Following her tip would also make it easier to exclude the confirmation message box from the UI if there is no confirmation message. Additionally, the project has clear setup documentation that is compatible with my OS. I hope to learn TypeScript and gain more experience in coding with HTML and Java and making open-source contributions.

---

## Understanding the Issue

### Problem Description

When creating a new user as an admin with an invalid email pattern, the error message displayed is unclear and does not provide an explanation or visual feedback on why the email address is invalid.

### Expected Behavior

When creating a new user as an admin with an invalid email pattern, the error message displayed should be clear and provide an explanation or visual feedback on why the email address is invalid.

### Current Behavior

If a new user is created as an admin with invalid email address, the error message displayed is unclear and does not explain why the email address is invalid.

### Affected Components

[Which parts of the codebase are involved?]

---

## Reproduction Process

### Environment Setup

I learned from an Artemis Development Environment Setup guide linked in the README instructions for this open-source project. To set up my local development environment on Visual Studio Code, I downloaded and installed Java JDK 25 and Node.js LTS 24.18.0. I also ran "sudo corepack enable" so I would not have to manually follow the official pnpm installation steps. I then used Docker to set up a MySQL database. While setting up the MySQL database, I struggled with resetting the root password to an empty password. I was using the command "mysql -u root --execute "ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY ''";", and I asked Claude Code why my terminal was saying that the command "mysql" was not found. Claude told me that the mysql command-line client was installed only inside the Docker container and not on my Mac itself. Claude recommended me to use docker exec and the command "docker exec -it artemis-mysql mysql -u root --execute "ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY ''"" because my container was named artemis-mysql. This solution did not require me to install the mysql command-line client on my Mac itself. 

Next, I set up my server by creating application-local.yml in src/main/resources/config and copying and pasting configuration settings recommended by the development environment setup guide into application-local.yml. When trying to run the server with the command line using a Gradle wrapper (command: ./gradlew bootRun --args='--spring.profiles.active=dev,jenkins,localvc,artemis,scheduling,local,core'), the application was not getting executed, so I gave Claude my terminal output from trying to run the server and asked Claude the application is not being executed. Claude informed me that I should not be using tabs in application-local.yml, and Claude also recommended numerous configuration options that were not mentioned in this setup guide. After including the configuration options recommended by Claude and removing tabs from application-local.yml, I was able to run the server. Finally, I started client application in the browser using the command "pnpm start" and accessed the website on http://localhost:8080 in my Chrome browser.

### Steps to Reproduce

1. Include the YAML configuration code from the link https://docs.artemis.tum.de/admin/user-registration/ into application-local.yml, which is in src/main/resources/config, while not removing any of the preexisting code that is already in application-local.yml
2. Run the server with the command ./gradlew bootRun --args='--spring.profiles.active=dev,jenkins,localvc,artemis,scheduling,local,core'.
3. Once the website content becomes accessible on http://localhost:8080 in my Chrome browser, click the "Log in" button at the top right corner of the website to log in as a (super) admin.
4. Input the username "artemis_admin" and the password "artemis_admin" to log in as a (super) admin
5. Click on the profile link at the top right corner of the website, then click the button labeled "Administration"
6. Click on the "Create a new user" button
7. Fill in a nonvalid email address, e.g., CoursesExams
8. Fill in anything for the first name and last name that only consists of letters, e.g., Courses for the first name and Exams for the last name
9. Fill in a random number for registration number
10. Use any of the options provided (English or Deutsch) for the Language prompt
11. Choose any and as many of the options as you want (Super Admin, Admin, Instructor, Editor, Tutor, Student) in the global roles prompt
12. Click the "Save" button at the bottom of the "Create a new user" page
14. Observed result: An error message (Error on field "translation-not-found[artemisApp.managedUserVM.email]") is displayed at the top of the webpage. This error message is unclear and does not explain why the email address is invalid or how to make the email address valid.

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:** ![Issue Reproduction Screenshot](issue_reproduction.png)
- **My findings:** During reproduction, I found that the issue described by the maintainer still exists. The error message (Error on field "translation-not-found[artemisApp.managedUserVM.email]") displayed at the top of the webpage after logging in as a (super) admin is unclear does not explain why the email address is invalid or how to make the email address valid.

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]

### Proposed Solution

[High-level description of your fix approach]

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** When new user as an admin gets created with an invalid email pattern, the error message displayed is unclear and does not provide an explanation or visual feedback on why the email address is invalid. I should make the error message clear and explain to the user why their email address is invalid or how to make their email address valid.

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
