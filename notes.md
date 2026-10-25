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
