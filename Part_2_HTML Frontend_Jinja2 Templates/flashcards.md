# FastAPI Part 2 Flashcards (With Answers)

1. **Q:** What is the primary purpose of using templates in a FastAPI application?
   **A:** To serve HTML pages to users while maintaining JSON endpoints for the backend API.
2. **Q:** What is the default templating engine used by FastAPI?
   **A:** Jinja2
3. **Q:** Which FastAPI package inclusion ensures that Jinja2 is pre-installed?
   **A:** fastapi[standard]
4. **Q:** From which module is the `Request` class imported for use with Jinja2 templates?
   **A:** fastapi
5. **Q:** From which module is the `Jinja2Templates` class imported?
   **A:** fastapi.templating
6. **Q:** Why is the `HTMLResponse` import often removed when switching to Jinja2 templates?
   **A:** Jinja2 templates use their own response class called `TemplateResponse`.
7. **Q:** What is the standard convention for naming the directory that stores HTML templates?
   **A:** templates
8. **Q:** How is the `templates` object initialized to look in a specific directory?
   **A:** By calling `Jinja2Templates(directory="templates")`.
9. **Q:** Which mandatory parameter must be included in a FastAPI route function to render a Jinja2 template?
   **A:** The `request: Request` parameter.
10. **Q:** What method is called on the `templates` object to render an HTML file to the user?
   **A:** The `TemplateResponse` method.
11. **Q:** What are the first two required arguments for the `TemplateResponse` method?
   **A:** The request object and the name of the template file.
12. **Q:** In FastAPI, what is the purpose of setting `include_in_schema=False` on a route decorator?
   **A:** It excludes page routes from the auto-generated API documentation (Swagger UI).
13. **Q:** In Jinja2 syntax, what do double curly braces `{{ ... }}` represent?
   **A:** Variable interpolation or displaying dynamic data.
14. **Q:** In Jinja2 syntax, what does the `{% ... %}` syntax represent?
   **A:** Control structures such as loops and conditionals.
15. **Q:** How is a variable passed from a FastAPI route to a Jinja2 template?
   **A:** Through a context dictionary passed as the third argument to `TemplateResponse`.
16. **Q:** Which Jinja2 keyword is used to begin a loop over a collection?
   **A:** for
17. **Q:** Which Jinja2 tag is required to signal the end of a `for` loop?
   **A:** endfor
18. **Q:** How does Jinja2 allow developers to access dictionary keys in a template?
   **A:** By using dot notation (e.g., `post.title`).
19. **Q:** Which Jinja2 keyword is used to start a conditional block?
   **A:** if
20. **Q:** Which Jinja2 tag is required to signal the end of a conditional block?
   **A:** endif
21. **Q:** What is the benefit of template inheritance in web development?
   **A:** It reduces code duplication by creating a shared parent structure for child templates.
22. **Q:** In a parent template, what tag defines a section that child templates can override?
   **A:** block
23. **Q:** What Jinja2 tag must be at the very top of a child template to utilize a parent layout?
   **A:** extends
24. **Q:** What is the naming convention for a shared parent template containing the site's header and footer?
   **A:** layout.html
25. **Q:** What are 'static files' in the context of a web application?
   **A:** Assets that do not change dynamically, such as CSS, JavaScript, and images.
26. **Q:** From which module is the `StaticFiles` class imported?
   **A:** fastapi.staticfiles
27. **Q:** Which FastAPI application method is used to serve a directory of static assets?
   **A:** app.mount()
28. **Q:** In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what does the first argument represent?
   **A:** The URL path where the static files will be accessible in the browser.
29. **Q:** In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what does the `directory` argument represent?
   **A:** The actual name of the folder on the server containing the static assets.
30. **Q:** In `app.mount("/static", StaticFiles(directory="static"), name="static")`, what is the purpose of the `name` argument?
   **A:** It provides a name for internal referencing, specifically for use with the `url_for` function.
31. **Q:** What Jinja2 function is used to generate URLs for routes or static files dynamically?
   **A:** url_for()
32. **Q:** What is the major advantage of using `url_for` over hardcoded URL strings?
   **A:** Links update automatically if route paths or static mount paths are changed.
33. **Q:** How do you reference the static asset `css/main.css` using `url_for`?
   **A:** url_for('static', path='css/main.css')
34. **Q:** By default, what does FastAPI use as the unique name for a route?
   **A:** The name of the route's handler function.
35. **Q:** How can you resolve a conflict where multiple decorators point to the same function but need distinct names for `url_for`?
   **A:** By providing an explicit `name` parameter in the route decorator.
36. **Q:** If a template uses `url_for` for a route that does not exist, what happens?
   **A:** FastAPI will throw an error.
37. **Q:** Why is the `request` object required within the context of a Jinja2 template response?
   **A:** Jinja2 requires the request object to handle internal operations and URL generation.
38. **Q:** Which CSS framework is utilized in the Corey Schafer tutorial for quick styling?
   **A:** Bootstrap
39. **Q:** What does a 404 status code indicate when viewing the development server logs for a CSS file?
   **A:** The static directory has not been mounted correctly or the file path is incorrect.
40. **Q:** In the `url_for('static', path=...)` function, what is the name of the keyword argument used to specify the file location?
   **A:** path
41. **Q:** What is the purpose of the `else` tag within a Jinja2 `if` block?
   **A:** It defines the content to display if the initial condition evaluates to false.
42. **Q:** How do you specify a default page title in a layout using Jinja2 conditionals?
   **A:** {% if title %} {{ title }} {% else %} Default Title {% endif %}
43. **Q:** What is the purpose of an 'open graph' meta tag in an HTML head section?
   **A:** It controls how a website appears when shared on social media platforms.
44. **Q:** How do you close a block named 'content' in a Jinja2 template?
   **A:** {% endblock content %}
45. **Q:** Which decorator parameter allows a developer to provide a human-friendly name for a route to be used in `url_for`?
   **A:** name
46. **Q:** What is the result of using `url_for('home')` if the `home` function has multiple decorators?
   **A:** It defaults to the last route defined unless explicit names are provided.
47. **Q:** What is the convention for referencing the parent template file in an `extends` tag?
   **A:** Use the filename as a string, such as `{% extends 'layout.html' %}`.
48. **Q:** Where should the `app.mount` command for static files typically be placed in `main.py`?
   **A:** After the FastAPI `app` instance is created.
49. **Q:** In a FastAPI route, what dictionary key is conventionally used to pass a list of objects to a template?
   **A:** posts
50. **Q:** What is a 'hard refresh' in a browser, and why is it used during CSS development?
   **A:** It clears the browser cache to ensure the most recent version of a CSS file is loaded.
51. **Q:** Which Jinja2 tag allows you to create a reusable section like a sidebar in a parent template?
   **A:** block
52. **Q:** Term: TemplateResponse
   **A:** Definition: The FastAPI class used to send a rendered Jinja2 template as an HTTP response.
53. **Q:** Concept: Context Dictionary
   **A:** Definition: A collection of key-value pairs passed to a template to provide dynamic data for rendering.
54. **Q:** What argument must be passed to the `StaticFiles` constructor to identify the source folder?
   **A:** directory
55. **Q:** Why is it better to return JSON for API access and HTML for browsers?
   **A:** JSON is machine-readable for apps, whereas HTML is human-readable for browser users.
56. **Q:** In Jinja2, how do you correctly reference a specific item's property inside a for loop `{% for item in items %}`?
   **A:** Using `{{ item.property_name }}`.
57. **Q:** What tag is used in a layout to indicate where the unique content of a child page will be inserted?
   **A:** {% block content %}
58. **Q:** If you need to install Jinja2 manually, which command would you use?
   **A:** `pip install jinja2` or `uv add jinja2`.
59. **Q:** What is the primary function of the `directory` parameter in `Jinja2Templates`?
   **A:** It tells the engine which folder contains the `.html` template files.
60. **Q:** The function `url_for("home")` maps to which part of the FastAPI route definition?
   **A:** The name of the Python function (or the explicit `name` argument in the decorator).
