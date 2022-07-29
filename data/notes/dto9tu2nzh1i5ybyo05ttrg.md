
- Mermaid on [[s.apps.azure.devops]] uses a different syntax for the diagram code fences. Instead of 3 backticks \`\`\`  they use colons `:::`
  - The diagrams will only render and preview on the DevOps wiki pages not the markdown pages or their previews.
  - The diagrams will also no render in the preview pane of the pull request review section
  - The only way of reviewing diagram code visually is the code [[cli.cmd.diff]], or by using a sample test wiki page to show preview renders of the diagrams
  - `mailto:` links have additional properties that can be set in [[s.m.html]] but also with Markdown
    - [Resource Link](https://css-tricks.com/snippets/html/mailto-links/)
    - in markdown, to generate an email addressed to someone, with defined subjects line, body, and other addressees you use these pieces of text as part of the links remembering to escape spaces with `$20`:
      - `?subject=` the subject line of the email. `?subject=My%20Subject`
      - `?cc=` add carbon copy addressees `?cc=jonny.test@gmail.com`
      - `?bcc=` blind carbon copy someone `?bcc=jonny.test@gmail.com`
      - `?body=` your body text remembering to escape spaces with `%20`
        - `?body=My%20lovely%20email%20body%20message`
      -  If you only use 1 parameter after the email addressee then that parameter will start with a `?` like `?subject=` every parameter used after that will use a `&` such as `&cc=`, or `&bcc=`, etc.

## All together:

```markdown
[Send formatted email](mailto:bryan@bryanjenks.dev?cc=bryan@bryanjenks.dev&bcc=bryan@bryanjenks.dev&subject=My%20Subject%20Line&body=My%20lovely%20email%20body%20message)
```

[Send formatted email](mailto:bryan@bryanjenks.dev?cc=bryan@bryanjenks.dev&bcc=bryan@bryanjenks.dev&subject=My%20Subject%20Line&body=My%20lovely%20email%20body%20message)


- The Git Stash command has some awesome options

```bash
git stash push 
```
- like an array method this will create a _Box_ and put all your changes inside of it and shove that _box_ in the corner of the room and give you a clean working tree.
- The _box_ is now portable and you can switch to another branch and open the _box_ there and take out all of the changes.

```bash
git stash pop
```

- This opens the _box_ and applies all those stashed changes to the current working tree.
- This is very useful for the situations where maybe you made a bunch of changes and you forgot to make a new branch and you're still on `master`/`main` and you want to move all those changes to the actual feature branch.
- markdown You can link to other markdown page headings from other documents

```markdown
[link](file-name.md#heading-with-dashes-for-spaces)
```

```bash
git worktree add master
```

- Create a bare repo and start making new worktrees
  - This means that a copy of the repo files is made for each worktree at the source commit that the bare repo was made from
  - Worktrees make it easier to open multiple repo branches at once under a unified workspace for easy switching of work between multiple features
  - Doesn't lend itself to easy updating.
    - The bare repo doesn't `git pull` itself but the worktrees after creation can use `git pull` but this is not ideal. The bare repo is basically frozen at a single commit for all new worktrees made.

- HL7
  - HL7 terms to better understand what is HL7. There are four primary HL7 standard message types:
  - Patient Administration ([ADT](http://www.corepointhealth.com/resource-center/hl7-resources/hl7-adt))
  - Orders ([ORM](http://www.corepointhealth.com/resource-center/hl7-resources/hl7-orm-message)'s)
  - Results ([ORU](http://www.corepointhealth.com/resource-center/hl7-resources/hl7-oru-message)'s)
  - Charges ([DFT](http://www.corepointhealth.com/resource-center/hl7-resources/hl7-dft-detail-financial-transaction)'s)
  - Most commonly used HL7 message types include:
    - [ACK](https://corepointhealth.com/resource-center/hl7-resources/hl7-acknowledgement-ack) – General acknowledgement
    - [ADT](https://corepointhealth.com/resource-center/hl7-resources/hl7-adt) – Admit, Discharge, Tranfser
    - BAR – Add/change billing account
    - [DFT](https://corepointhealth.com/resource-center/hl7-resources/hl7-dft-detail-financial-transaction) – Detailed financial transaction
    - [MDM](https://corepointhealth.com/resource-center/hl7-resources/hl7-mdm-message) – Medical document management
    - MFN – Master files notification
    - [ORM](https://corepointhealth.com/resource-center/hl7-resources/hl7-orm-message) – Order (Pharmacy/treatment)
    - [ORU](https://corepointhealth.com/resource-center/hl7-resources/hl7-oru-message) – Observation result (unsolicited)
    - QRY – Query, original mode
    - RAS – Pharmacy/treatment administration
    - [RDE](https://corepointhealth.com/resource-center/hl7-resources/hl7-rde-message-pharmacy) – Pharmacy/treatment encoded order
    - RGV – Pharmacy/treatment give
    - [SIU](https://corepointhealth.com/resource-center/hl7-resources/hl7-siu-message) – Scheduling information unsolicited

