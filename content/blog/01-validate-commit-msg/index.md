---
title: Regular Expression to validate git commit message
featuredImage: './html-on-screen.jpg'
date: "2021-07-06T22:12:03.284Z"
description: "Add JIRA Ticket Number Validation in 5 minutes"
---


![Alt Text](./html-on-screen.jpg "vs code IDE")

<center>Photo by <a href="https://unsplash.com/@_imkiran?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Sai Kiran Anagani</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a></center>
  
# Why bother
Developer only spend 10 percent of time writing code, the rest is reading. When we want to back track code. It often takes time to pick up the context. The best place would be JIRA ticket when this job is assigned.
If we can track the ticket number in a flash. I mean on a mouse over, that is a tremendous action in now days already. That will make our life more civilized!

# What to use
- [vscode](https://code.visualstudio.com/) primary IDE
- [vscode extension gitlens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) infomation will be shown via inline hint
- [commitizen](https://www.npmjs.com/package/commitizen) gate keeper when you commit
- [cz-conventional-changelog](https://github.com/commitizen/cz-conventional-changelog) commit template
- [validate-commit-msg](https://www.npmjs.com/package/validate-commit-msg)
- [husky](https://www.npmjs.com/package/husky) 

# How

#### 1. install commitizen

`npm i commitizen cz-conventional-changelog husky validate-commit-msg --save-dev`

#### 2. install commitizen

add `"commit": "git-cz",` to package.json scirpt block

#### 3. create .czrc file and add path 
```
{
	"path": "cz-conventional-changelog"
}
```
So that git-cz will use cz-conventional-changelog as default setting.

#### 4. create .vcmrc file and validation message regular expression
```
{
  "subjectPattern": "^[a-zA-Z]+-[0-9]+ - .*",
  "subjectPatternErrorMsg": "Subject must include JIRA/Confluence ticket number like 'project-123 - your commit message'",
}
``` 

#### 5. create .vcmrc file and validation message regular expression
```
{
  "subjectPattern": "^[a-zA-Z]+-[0-9]+ - .*",
  "subjectPatternErrorMsg": "Subject must include JIRA/Confluence ticket number like 'project-123 - your commit message'",
}
``` 

#### 6. create .huskyrc file, this is for running commit message validaton after commitizen
```
{
	"hooks": {
		"commit-msg": "validate-commit-msg"
	}
}
``` 

![Alt Text](https://placehold.it/200x50 "Image Title")

    ![Alt Text](https://placehold.it/200x50 "Image Title")
