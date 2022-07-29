

```html
<a href="mailto:bryan@bryanjenks.dev?subject=mailto%20links">Send Mail</a>
```

- `mailto:` links have additional properties that can be set in [[s.m.html]] but also with Markdown
- [Resource Link](https://css-tricks.com/snippets/html/mailto-links/)
- in markdown, to generate an email addressed to someone, with defined subjects line, body, and other addressees you use these pieces of text as part of the links remembering to escape spaces with `$20`:
    - `?subject=` the subject line of the email. `?subject=My%20Subject`
    - `?cc=` add carbon copy addressees `?cc=jonny.test@gmail.com`
    - `?bcc=` blind carbon copy someone `?bcc=jonny.test@gmail.com`
    - `?body=` your body text remembering to escape spaces with `%20`
    - `?body=My%20lovely%20email%20body%20message`
    -  If you only use 1 parameter after the email addressee then that parameter will start with a `?` like `?subject=` every parameter used after that will use a `&` such as `&cc=`, or `&bcc=`, etc.
