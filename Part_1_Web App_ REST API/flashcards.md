# FastAPI Flashcards (With Answers)

1. **Q:** What is FastAPI?
   **A:** A modern, fast Python web framework for building APIs.
2. **Q:** Name three key features of the FastAPI framework mentioned in the tutorial.
   **A:** Automatic API documentation, built-in data validation, and async support.
3. **Q:** What command-line package manager, noted for its speed, is used as an alternative to pip in the tutorial?
   **A:** `uv`.
4. **Q:** What is the recommended pip command to install FastAPI with its standard extras?
   **A:** `pip install "fastapi[standard]"`.
5. **Q:** The `[standard]` extra in a FastAPI installation includes the FastAPI framework itself, the FastAPI CLI, and what ASGI server?
   **A:** Uvicorn.
6. **Q:** What is the purpose of Uvicorn in a FastAPI project?
   **A:** It is an ASGI server used to run the application.
7. **Q:** In a new FastAPI project, what is the conventional filename for the main application file?
   **A:** `main.py`.
8. **Q:** Which class must be imported from the `fastapi` library to create an application instance?
   **A:** `FastAPI`.
9. **Q:** What line of code creates the main application instance in FastAPI?
   **A:** `app = FastAPI()`.
10. **Q:** In FastAPI, what Python feature is used to associate a URL path with a function that handles requests for that path?
    **A:** Decorators.
11. **Q:** What decorator is used to create a route that responds to HTTP GET requests for the root URL (`/`)?
    **A:** `@app.get("/")`.
12. **Q:** When a Python dictionary is returned from a FastAPI route function, what data format is it automatically converted to in the HTTP response?
    **A:** JSON.
13. **Q:** What FastAPI CLI command is used to run the development server with auto-reload enabled for `main.py`?
    **A:** `fastapi dev main.py`.
14. **Q:** What is the primary benefit of using `fastapi dev` instead of `fastapi run` during development?
    **A:** It includes auto-reload, which automatically restarts the server when code changes are saved.
15. **Q:** Which command, `fastapi dev` or `fastapi run`, is optimized for performance and should be used in production environments?
    **A:** `fastapi run`.
16. **Q:** By default, on which port does the FastAPI development server run?
    **A:** Port 8000.
17. **Q:** What is the default URL path to access the interactive Swagger UI documentation for a FastAPI application?
    **A:** `/docs`.
18. **Q:** What is the default URL path to access the alternative, more modern-looking ReDoc documentation for a FastAPI application?
    **A:** `/redoc`.
19. **Q:** The interactive documentation at `/docs` allows you to test API endpoints directly in the browser and provides an equivalent _____ command for terminal use.
    **A:** `curl`.
20. **Q:** If a FastAPI endpoint returns a Python list of dictionaries, what will be the structure of the resulting JSON response?
    **A:** A JSON array of objects.
21. **Q:** To return an HTML response from a FastAPI route, what class must be imported from `fastapi.responses`?
    **A:** `HTMLResponse`.
22. **Q:** In an `@app.get()` decorator, what parameter must be set to return HTML content properly?
    **A:** `response_class=HTMLResponse`.
23. **Q:** How can you assign multiple URL paths, such as `/` and `/posts`, to a single handler function in FastAPI?
    **A:** By stacking multiple decorators (e.g., `@app.get("/")` and `@app.get("/posts")`) on top of the same function.
24. **Q:** What parameter should be added to a route decorator to exclude that route from the automatic API documentation?
    **A:** `include_in_schema=False`.
25. **Q:** Setting the _____ parameter to `False` in a route decorator will hide the route from `/docs` and `/redoc` but keep it functional in the browser.
    **A:** `include_in_schema`.
26. **Q:** Why is it good practice to exclude routes that serve HTML pages from the API documentation?
    **A:** To keep the API documentation clean and focused on JSON endpoints intended for programmatic access.
27. **Q:** FastAPI can handle both synchronous (`def`) and asynchronous (`_____`) functions for route handlers.
    **A:** `async def`.
