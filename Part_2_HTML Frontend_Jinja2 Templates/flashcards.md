# FastAPI Part 2 Master Flashcards

> [!IMPORTANT]
> **Part 2 Master Deck**
> **Format:** GitHub-friendly study sheet
> **Coverage:** `60 cards` · `5 sections` · Fully expanded Q&A

## Quick Navigation
- [1. Foundations and Template Setup](#1-foundations-and-template-setup)
- [2. Jinja2 Syntax and Data Binding](#2-jinja2-syntax-and-data-binding)
- [3. Static Files and URL Generation](#3-static-files-and-url-generation)
- [4. Template Patterns and Naming Conventions](#4-template-patterns-and-naming-conventions)
- [5. Core Concepts and Definitions](#5-core-concepts-and-definitions)

## How to Use This Deck
1. Read the **Q** and answer from memory before looking at the **A**.
2. Compare your response with the official answer and note gaps.
3. Lock the concept by repeating the **Key takeaway** in your own words.

## Progress Tracker
- [ ] 1. Foundations and Template Setup
- [ ] 2. Jinja2 Syntax and Data Binding
- [ ] 3. Static Files and URL Generation
- [ ] 4. Template Patterns and Naming Conventions
- [ ] 5. Core Concepts and Definitions

---

## 1. Foundations and Template Setup
**Section focus:** Build the base FastAPI + Jinja2 mental model and understand required setup pieces.
**Cards:** `Card 01` to `Card 12`

### Card 01 · What is the primary purpose of using...
> [!NOTE]
> **Q:** What is the primary purpose of using templates in a FastAPI application?
> **A:** To serve HTML pages to users while maintaining JSON endpoints for the backend API.
> **Key takeaway:** Core point: To serve HTML pages to users while maintaining JSON endpoints for the backend API.

### Card 02 · What is the default templating engine used...
> [!NOTE]
> **Q:** What is the default templating engine used by FastAPI?
> **A:** Jinja2
> **Key takeaway:** Core point: Jinja2

### Card 03 · Which FastAPI package inclusion ensures that Jinja2...
> [!NOTE]
> **Q:** Which FastAPI package inclusion ensures that Jinja2 is pre-installed?
> **A:** fastapi[standard]
> **Key takeaway:** Core point: fastapi[standard]

### Card 04 · From which module is the `Request` class...
> [!NOTE]
> **Q:** From which module is the `Request` class imported for use with Jinja2 templates?
> **A:** fastapi
> **Key takeaway:** Core point: fastapi

### Card 05 · From which module is the `Jinja2Templates` class...
> [!NOTE]
> **Q:** From which module is the `Jinja2Templates` class imported?
> **A:** fastapi.templating
> **Key takeaway:** Core point: fastapi.templating

### Card 06 · Why is the `HTMLResponse` import often removed...
> [!NOTE]
> **Q:** Why is the `HTMLResponse` import often removed when switching to Jinja2 templates?
> **A:** Jinja2 templates use their own response class called `TemplateResponse`.
> **Key takeaway:** Core point: Jinja2 templates use their own response class called `TemplateResponse`.

### Card 07 · What is the standard convention for naming...
> [!NOTE]
> **Q:** What is the standard convention for naming the directory that stores HTML templates?
> **A:** templates
> **Key takeaway:** Core point: templates

### Card 08 · How is the `templates` object initialized to...
> [!NOTE]
> **Q:** How is the `templates` object initialized to look in a specific directory?
> **A:** By calling `Jinja2Templates(directory="templates")`.
> **Key takeaway:** Core point: By calling `Jinja2Templates(directory="templates")`.

### Card 09 · Which mandatory parameter must be included in...
> [!NOTE]
> **Q:** Which mandatory parameter must be included in a FastAPI route function to render a Jinja2 template?
> **A:** The `request: Request` parameter.
> **Key takeaway:** Core point: The `request: Request` parameter.

### Card 10 · What method is called on the `templates`...
> [!NOTE]
> **Q:** What method is called on the `templates` object to render an HTML file to the user?
> **A:** The `TemplateResponse` method.
> **Key takeaway:** Core point: The `TemplateResponse` method.

### Card 11 · What are the first two required arguments...
> [!NOTE]
> **Q:** What are the first two required arguments for the `TemplateResponse` method?
> **A:** The request object and the name of the template file.
> **Key takeaway:** Core point: The request object and the name of the template file.

### Card 12 · In FastAPI, what is the purpose of...
> [!NOTE]
> **Q:** In FastAPI, what is the purpose of setting `include_in_schema=False` on a route decorator?
> **A:** It excludes page routes from the auto-generated API documentation (Swagger UI).
> **Key takeaway:** Core point: It excludes page routes from the auto-generated API documentation (Swagger UI).

### Section Recap Prompts
- Which imports and parameters are mandatory before templates render correctly?
- Why does `include_in_schema=False` matter for page-style routes?
- What is the quickest way to verify your basic template setup works?

---

## 2. Jinja2 Syntax and Data Binding
**Section focus:** Understand Jinja2 expressions, control flow, inheritance, and data passing rules.
**Cards:** `Card 13` to `Card 24`

### Card 13 · In Jinja2 syntax, what do double curly...
> [!NOTE]
> **Q:** In Jinja2 syntax, what do double curly braces `{{ ... }}` represent?
> **A:** Variable interpolation or displaying dynamic data.
> **Key takeaway:** Core point: Variable interpolation or displaying dynamic data.

### Card 14 · In Jinja2 syntax, what does the `{%...
> [!NOTE]
> **Q:** In Jinja2 syntax, what does the `{% ... %}` syntax represent?
> **A:** Control structures such as loops and conditionals.
> **Key takeaway:** Core point: Control structures such as loops and conditionals.

### Card 15 · How is a variable passed from a...
> [!NOTE]
> **Q:** How is a variable passed from a FastAPI route to a Jinja2 template?
> **A:** Through a context dictionary passed as the third argument to `TemplateResponse`.
> **Key takeaway:** Core point: Through a context dictionary passed as the third argument to `TemplateResponse`.

### Card 16 · Which Jinja2 keyword is used to begin...
> [!NOTE]
> **Q:** Which Jinja2 keyword is used to begin a loop over a collection?
> **A:** for
> **Key takeaway:** Core point: for

### Card 17 · Which Jinja2 tag is required to signal...
> [!NOTE]
> **Q:** Which Jinja2 tag is required to signal the end of a `for` loop?
> **A:** endfor
> **Key takeaway:** Core point: endfor

### Card 18 · How does Jinja2 allow developers to access...
> [!NOTE]
> **Q:** How does Jinja2 allow developers to access dictionary keys in a template?
> **A:** By using dot notation (e.g., `post.title`).
> **Key takeaway:** Core point: By using dot notation (e.g., `post.title`).

### Card 19 · Which Jinja2 keyword is used to start...
> [!NOTE]
> **Q:** Which Jinja2 keyword is used to start a conditional block?
> **A:** if
> **Key takeaway:** Core point: if

### Card 20 · Which Jinja2 tag is required to signal...
> [!NOTE]
> **Q:** Which Jinja2 tag is required to signal the end of a conditional block?
> **A:** endif
> **Key takeaway:** Core point: endif

### Card 21 · What is the benefit of template inheritance...
> [!NOTE]
> **Q:** What is the benefit of template inheritance in web development?
> **A:** It reduces code duplication by creating a shared parent structure for child templates.
> **Key takeaway:** Core point: It reduces code duplication by creating a shared parent structure for child templates.

### Card 22 · In a parent template, what tag defines...
> [!NOTE]
> **Q:** In a parent template, what tag defines a section that child templates can override?
> **A:** block
> **Key takeaway:** Core point: block

### Card 23 · What Jinja2 tag must be at the...
> [!NOTE]
> **Q:** What Jinja2 tag must be at the very top of a child template to utilize a parent layout?
> **A:** extends
> **Key takeaway:** Core point: extends

### Card 24 · What is the naming convention for a...
> [!NOTE]
> **Q:** What is the naming convention for a shared parent template containing the site's header and footer?
> **A:** layout.html
> **Key takeaway:** Core point: layout.html

### Section Recap Prompts
- When do you use `{{ ... }}` vs `{% ... %}` in templates?
- How does template inheritance reduce duplication across pages?
- How is route data passed into templates for rendering?

---

## 3. Static Files and URL Generation
**Section focus:** Serve static assets safely and generate stable links using `url_for`.
**Cards:** `Card 25` to `Card 40`

### Card 25 · What are 'static files' in the context...
> [!NOTE]
> **Q:** What are 'static files' in the context of a web application?
> **A:** Assets that do not change dynamically, such as CSS, JavaScript, and images.
> **Key takeaway:** Core point: Assets that do not change dynamically, such as CSS, JavaScript, and images.

### Card 26 · From which module is the `StaticFiles` class...
> [!NOTE]
> **Q:** From which module is the `StaticFiles` class imported?
> **A:** fastapi.staticfiles
> **Key takeaway:** Core point: fastapi.staticfiles

### Card 27 · Which FastAPI application method is used to...
> [!NOTE]
> **Q:** Which FastAPI application method is used to serve a directory of static assets?
> **A:** app.mount()
> **Key takeaway:** Core point: app.mount()

### Card 28 · In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what does the...
> [!NOTE]
> **Q:** In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what does the first argument represent?
> **A:** The URL path where the static files will be accessible in the browser.
> **Key takeaway:** Core point: The URL path where the static files will be accessible in the browser.

### Card 29 · In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what does the...
> [!NOTE]
> **Q:** In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what does the `directory` argument represent?
> **A:** The actual name of the folder on the server containing the static assets.
> **Key takeaway:** Core point: The actual name of the folder on the server containing the static assets.

### Card 30 · In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what is the...
> [!NOTE]
> **Q:** In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what is the purpose of the `name` argument?
> **A:** It provides a name for internal referencing, specifically for use with the `url_for` function.
> **Key takeaway:** Core point: It provides a name for internal referencing, specifically for use with the `url_for` function.

### Card 31 · What Jinja2 function is used to generate...
> [!NOTE]
> **Q:** What Jinja2 function is used to generate URLs for routes or static files dynamically?
> **A:** url_for()
> **Key takeaway:** Core point: url_for()

### Card 32 · What is the major advantage of using...
> [!NOTE]
> **Q:** What is the major advantage of using `url_for` over hardcoded URL strings?
> **A:** Links update automatically if route paths or static mount paths are changed.
> **Key takeaway:** Core point: Links update automatically if route paths or static mount paths are changed.

### Card 33 · How do you reference the static asset...
> [!NOTE]
> **Q:** How do you reference the static asset `css/main.css` using `url_for`?
> **A:** url_for('static', path='css/main.css')
> **Key takeaway:** Core point: url_for('static', path='css/main.css')

### Card 34 · By default, what does FastAPI use as...
> [!NOTE]
> **Q:** By default, what does FastAPI use as the unique name for a route?
> **A:** The name of the route's handler function.
> **Key takeaway:** Core point: The name of the route's handler function.

### Card 35 · How can you resolve a conflict where...
> [!NOTE]
> **Q:** How can you resolve a conflict where multiple decorators point to the same function but need distinct names for `url_for`?
> **A:** By providing an explicit `name` parameter in the route decorator.
> **Key takeaway:** Core point: By providing an explicit `name` parameter in the route decorator.

### Card 36 · If a template uses `url_for` for a...
> [!NOTE]
> **Q:** If a template uses `url_for` for a route that does not exist, what happens?
> **A:** FastAPI will throw an error.
> **Key takeaway:** Core point: FastAPI will throw an error.

### Card 37 · Why is the `request` object required within...
> [!NOTE]
> **Q:** Why is the `request` object required within the context of a Jinja2 template response?
> **A:** Jinja2 requires the request object to handle internal operations and URL generation.
> **Key takeaway:** Core point: Jinja2 requires the request object to handle internal operations and URL generation.

### Card 38 · Which CSS framework is utilized in the...
> [!NOTE]
> **Q:** Which CSS framework is utilized in the Corey Schafer tutorial for quick styling?
> **A:** Bootstrap
> **Key takeaway:** Core point: Bootstrap

### Card 39 · What does a 404 status code indicate...
> [!NOTE]
> **Q:** What does a 404 status code indicate when viewing the development server logs for a CSS file?
> **A:** The static directory has not been mounted correctly or the file path is incorrect.
> **Key takeaway:** Core point: The static directory has not been mounted correctly or the file path is incorrect.

### Card 40 · In the `url_for('static', path=...)` function, what is...
> [!NOTE]
> **Q:** In the `url_for('static', path=...)` function, what is the name of the keyword argument used to specify the file location?
> **A:** path
> **Key takeaway:** Core point: path

### Section Recap Prompts
- What does each argument in `app.mount("/static", StaticFiles(...), name="static")` control?
- Why is `url_for` preferred over hardcoded links in templates?
- What usually causes CSS-related `404` responses in development?

---

## 4. Template Patterns and Naming Conventions
**Section focus:** Apply practical naming, conditional, layout, and route-linking conventions.
**Cards:** `Card 41` to `Card 50`

### Card 41 · What is the purpose of the `else`...
> [!NOTE]
> **Q:** What is the purpose of the `else` tag within a Jinja2 `if` block?
> **A:** It defines the content to display if the initial condition evaluates to false.
> **Key takeaway:** Core point: It defines the content to display if the initial condition evaluates to false.

### Card 42 · How do you specify a default page...
> [!NOTE]
> **Q:** How do you specify a default page title in a layout using Jinja2 conditionals?
> **A:** {% if title %} {{ title }} {% else %} Default Title {% endif %}
> **Key takeaway:** Core point: {% if title %} {{ title }} {% else %} Default Title {% endif %}

### Card 43 · What is the purpose of an 'open...
> [!NOTE]
> **Q:** What is the purpose of an 'open graph' meta tag in an HTML head section?
> **A:** It controls how a website appears when shared on social media platforms.
> **Key takeaway:** Core point: It controls how a website appears when shared on social media platforms.

### Card 44 · How do you close a block named...
> [!NOTE]
> **Q:** How do you close a block named 'content' in a Jinja2 template?
> **A:** {% endblock content %}
> **Key takeaway:** Core point: {% endblock content %}

### Card 45 · Which decorator parameter allows a developer to...
> [!NOTE]
> **Q:** Which decorator parameter allows a developer to provide a human-friendly name for a route to be used in `url_for`?
> **A:** name
> **Key takeaway:** Core point: name

### Card 46 · What is the result of using `url_for('home')`...
> [!NOTE]
> **Q:** What is the result of using `url_for('home')` if the `home` function has multiple decorators?
> **A:** It defaults to the last route defined unless explicit names are provided.
> **Key takeaway:** Core point: It defaults to the last route defined unless explicit names are provided.

### Card 47 · What is the convention for referencing the...
> [!NOTE]
> **Q:** What is the convention for referencing the parent template file in an `extends` tag?
> **A:** Use the filename as a string, such as `{% extends 'layout.html' %}`.
> **Key takeaway:** Core point: Use the filename as a string, such as `{% extends 'layout.html' %}`.

### Card 48 · Where should the `app.mount` command for static...
> [!NOTE]
> **Q:** Where should the `app.mount` command for static files typically be placed in `main.py`?
> **A:** After the FastAPI `app` instance is created.
> **Key takeaway:** Core point: After the FastAPI `app` instance is created.

### Card 49 · In a FastAPI route, what dictionary key...
> [!NOTE]
> **Q:** In a FastAPI route, what dictionary key is conventionally used to pass a list of objects to a template?
> **A:** posts
> **Key takeaway:** Core point: posts

### Card 50 · What is a 'hard refresh' in a...
> [!NOTE]
> **Q:** What is a 'hard refresh' in a browser, and why is it used during CSS development?
> **A:** It clears the browser cache to ensure the most recent version of a CSS file is loaded.
> **Key takeaway:** Core point: It clears the browser cache to ensure the most recent version of a CSS file is loaded.

### Section Recap Prompts
- How do `if/else` blocks and named blocks improve template flexibility?
- Why are explicit route names useful when using `url_for`?
- Where should static mounting happen in `main.py` for consistency?

---

## 5. Core Concepts and Definitions
**Section focus:** Solidify definitions and core conceptual anchors used across the Part 2 stack.
**Cards:** `Card 51` to `Card 60`

### Card 51 · Which Jinja2 tag allows you to create...
> [!NOTE]
> **Q:** Which Jinja2 tag allows you to create a reusable section like a sidebar in a parent template?
> **A:** block
> **Key takeaway:** Core point: block

### Card 52 · Term: TemplateResponse
> [!NOTE]
> **Q:** Term: TemplateResponse
> **A:** Definition: The FastAPI class used to send a rendered Jinja2 template as an HTTP response.
> **Key takeaway:** Core point: Definition: The FastAPI class used to send a rendered Jinja2 template as an HTTP response.

### Card 53 · Concept: Context Dictionary
> [!NOTE]
> **Q:** Concept: Context Dictionary
> **A:** Definition: A collection of key-value pairs passed to a template to provide dynamic data for rendering.
> **Key takeaway:** Core point: Definition: A collection of key-value pairs passed to a template to provide dynamic data for rendering.

### Card 54 · What argument must be passed to the...
> [!NOTE]
> **Q:** What argument must be passed to the `StaticFiles` constructor to identify the source folder?
> **A:** directory
> **Key takeaway:** Core point: directory

### Card 55 · Why is it better to return JSON...
> [!NOTE]
> **Q:** Why is it better to return JSON for API access and HTML for browsers?
> **A:** JSON is machine-readable for apps, whereas HTML is human-readable for browser users.
> **Key takeaway:** Core point: JSON is machine-readable for apps, whereas HTML is human-readable for browser users.

### Card 56 · In Jinja2, how do you correctly reference...
> [!NOTE]
> **Q:** In Jinja2, how do you correctly reference a specific item's property inside a for loop `{% for item in items %}`?
> **A:** Using `{{ item.property_name }}`.
> **Key takeaway:** Core point: Using `{{ item.property_name }}`.

### Card 57 · What tag is used in a layout...
> [!NOTE]
> **Q:** What tag is used in a layout to indicate where the unique content of a child page will be inserted?
> **A:** {% block content %}
> **Key takeaway:** Core point: {% block content %}

### Card 58 · If you need to install Jinja2 manually,...
> [!NOTE]
> **Q:** If you need to install Jinja2 manually, which command would you use?
> **A:** `pip install jinja2` or `uv add jinja2`.
> **Key takeaway:** Core point: `pip install jinja2` or `uv add jinja2`.

### Card 59 · What is the primary function of the...
> [!NOTE]
> **Q:** What is the primary function of the `directory` parameter in `Jinja2Templates`?
> **A:** It tells the engine which folder contains the `.html` template files.
> **Key takeaway:** Core point: It tells the engine which folder contains the `.html` template files.

### Card 60 · The function `url_for("home")` maps to which part...
> [!NOTE]
> **Q:** The function `url_for("home")` maps to which part of the FastAPI route definition?
> **A:** The name of the Python function (or the explicit `name` argument in the decorator).
> **Key takeaway:** Core point: The name of the Python function (or the explicit `name` argument in the decorator).

### Section Recap Prompts
- How would you define `TemplateResponse` and a context dictionary in one sentence each?
- What is the practical split between HTML responses for users and JSON for APIs?
- Which template and static-folder conventions prevent routing confusion?
