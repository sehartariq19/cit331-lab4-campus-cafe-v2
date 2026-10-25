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

## Live site observations (Lab 4, Task 7)

### 1. Localhost vs Live Website
On localhost, the website used HTTP with the address 127.0.0.1:5500, and requests were handled by the local development server. The published website uses HTTPS and is served by GitHub Pages. In DevTools, the live website returned status 200 OK, showed the server header as GitHub.com, and had a remote address of 185.199.109.153:443.

### 2. HTTPS and Security Certificate
The HTTPS connection encrypts data exchanged between the browser and the website and uses a certificate to help verify the server's identity. If the website used plain HTTP, an attacker on the same Wi-Fi network could potentially read or modify the information being transferred.

### 3. Local Storage
The Saved orders table was empty on the live website because localStorage data belongs to a specific origin. Orders stored on 127.0.0.1:5500 are separate from orders stored on sehartariq19.github.io. The live website therefore has its own localStorage data.

### 4. Missing Page and HTTP 404
When a non-existent page such as nothing-here.html is requested, the server should return HTTP status 404 Not Found. On the published website, this response is provided by GitHub Pages rather than the local development server.
