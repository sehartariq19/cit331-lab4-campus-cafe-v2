# HTTP observations (Lab 4, Task 1)

| Question | My answer |
|----------|-----------|
| Request method for index.html | GET |
| Status code with Disable cache ticked | 200 |
| Status code on a normal reload | 304 |
| Status code for /nothing-here.html | 404 |
| Value of the Content-Type response header | text/html; charset=UTF-8 |
| Remote Address (IP and port) | 127.0.0.1:5500 |
| Protocol in the address bar (http or https) | http |

## Why is this address http and not https?

This website runs on a local development server at 127.0.0.1, so the communication stays on my own computer. HTTPS encrypts traffic travelling over a network, but this local development setup uses HTTP because the traffic does not leave my computer.

## Specificity experiment

The #main p selector overrides .hero p because an ID selector has higher specificity than a class selector. When changed to main p, the .hero p rule wins and the hero paragraph returns to white.

## Selectors I used

| Selector kind | Example from my CSS |
|---------------|---------------------|
| Element | body |
| Class | .card |
| ID | #main |
| Grouping (comma) | h1, h2, h3 |
| Descendant (space) | .nav-list a |
| Child (>) | main > section |
| Adjacent sibling (+) | h1 + p |
| Compound | .nav-list a.active |
| Attribute | a[href^="http"] |
| Pseudo-class | a:hover |
| Pseudo-element | .menu-group h2::before |

## Bug log (Lab 4, Task 6)

| # | What was wrong (file and line) | Which tool showed it | My fix |
|---|---|---|---|
| 1 | bugs.html: stylesheet linked to style.css instead of bugs.css | Network | Changed href to bugs.css |
| 2 | bugs.html: html element had no lang attribute | W3C Validator / Lighthouse | Added lang="en" |
| 3 | bugs.html: navigation used a div instead of a nav element | Accessibility tree | Replaced div with nav |
| 4 | bugs.html: h4 followed h1, skipping heading levels | W3C Validator | Changed h4 to h2 |
| 5 | bugs.html: image was missing alt text | Lighthouse / W3C Validator | Added descriptive alt text |
| 6 | bugs.html: label for="mail" did not match input id="email" | Lighthouse / W3C Validator | Changed for to email |
| 7 | bugs.css: colour property was misspelled | Styles pane | Changed colour to color |
| 8 | bugs.css: missing semicolon after hover background prevented cursor rule from working | Styles pane | Added semicolon |
| 9 | bugs.css: .notes selector did not match class="note" | Styles pane | Changed .notes to .note |
| 10 | bugs.css: note text had weak colour contrast | Lighthouse after stylesheet loaded | Changed text color to #595959 |
