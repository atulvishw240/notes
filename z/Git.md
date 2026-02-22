
>[!bug] If you lose your two-factor authentication credentials or lose access to your account recovery methods.

## Commit Messages

A good commit message will explain the **why** behind your changes. In other words, a commit message describes what problem your changes solve and how it solves them.

Subject and a body.
**Subject** : This is the change you made to the project. (72 char limit)
**Body** : Describe the problem your commit solves and how
Example: 
```
Add missing link and alt text to the company's logo (What)

Screen readers won't read the images to users with disabilities without this information. (Why)
```

**A properly formed Git commit subject line should always be able to complete the following sentence**:

- If applied, this commit will <_your subject line here_>

>Use the body to explain what and why vs how. The code already explains how

---

>The basic Git syntax is `program | action | destination`.

`$ git clone <url>` - clones the github repo to your local machine
`$ git remote -v` -  outputs remote github url to which you push changes or fetch changes. Default name of your remote connection is **origin**.
`$ git log` - to view commit history
`$ git log --oneline` - limit each commit to one line
