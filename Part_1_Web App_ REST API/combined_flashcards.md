# FastAPI Part 1 Master Flashcards

> [!IMPORTANT]
> **Part 1 Master Deck**
> **Format:** GitHub-friendly study sheet
> **Coverage:** `38 cards` · `6 sections` · Fully expanded Q&A

## Quick Navigation
- [1. Foundations and Setup](#1-foundations-and-setup)
- [2. App Initialization and First Route](#2-app-initialization-and-first-route)
- [3. API Endpoints and Data Shape](#3-api-endpoints-and-data-shape)
- [4. HTML Responses and Multi-Route Patterns](#4-html-responses-and-multi-route-patterns)
- [5. Documentation and Schema Control](#5-documentation-and-schema-control)
- [6. Development vs Production Workflow](#6-development-vs-production-workflow)

## How to Use This Deck
1. Read the **Q** and answer from memory before looking at the **A**.
2. Compare your response with the official answer and note gaps.
3. Lock the idea by repeating the **Key takeaway** in your own words.

## Progress Tracker
- [ ] 1. Foundations and Setup
- [ ] 2. App Initialization and First Route
- [ ] 3. API Endpoints and Data Shape
- [ ] 4. HTML Responses and Multi-Route Patterns
- [ ] 5. Documentation and Schema Control
- [ ] 6. Development vs Production Workflow

---

## 1. Foundations and Setup
**Section focus:** Master core FastAPI concepts, installation choices, and async/sync fundamentals.
**Cards:** `Card 01` to `Card 06`

### Card 01 · What Is FastAPI?
> [!NOTE]
> **Q:** What is FastAPI?
> **A:** FastAPI is a modern, high-performance Python web framework for building APIs.
> **Key takeaway:** FastAPI is designed for API development speed, clarity, and performance.

### Card 02 · Modern Features
> [!NOTE]
> **Q:** What key features make FastAPI a "modern" framework?
> **A:** Automatic API documentation, built-in data validation, and native async support.
> **Key takeaway:** FastAPI combines validation, docs, and concurrency features out of the box.

### Card 03 · First Project Setup
> [!NOTE]
> **Q:** What are the first setup steps for a new FastAPI project?
> **A:** Create a project directory (for example, `fastapi_blog`) and install FastAPI with either `uv add fastapi[standard]` or `pip install "fastapi[standard]"`.
> **Key takeaway:** Project folder + dependency install is the complete starting point.

### Card 04 · Standard Extras Package
> [!NOTE]
> **Q:** What does installing `fastapi[standard]` give you?
> **A:** FastAPI itself, FastAPI CLI tooling, and Uvicorn (ASGI server), plus common standard extras.
> **Key takeaway:** `fastapi[standard]` sets up the default practical stack in one install.

### Card 05 · UV in the Tutorial
> [!NOTE]
> **Q:** What is `uv`, and why was it used in the tutorial?
> **A:** `uv` is a fast Python package manager used as an alternative to pip for installing dependencies.
> **Key takeaway:** `uv` is a speed-focused toolchain choice, not a FastAPI requirement.

### Card 06 · Sync vs Async Routes
> [!NOTE]
> **Q:** Does FastAPI require `async def` for every route?
> **A:** No. FastAPI supports both synchronous (`def`) and asynchronous (`async def`) handlers.
> **Key takeaway:** Use `async` when it helps your workload; sync handlers are fully valid.

### Section Recap Prompts
- Which three features justify calling FastAPI a modern framework?
- When would you choose `uv` vs `pip` for your setup flow?
- How do you decide between `def` and `async def` handlers?

---

## 2. App Initialization and First Route
**Section focus:** Build the application skeleton and understand how a first route behaves end-to-end.
**Cards:** `Card 07` to `Card 13`

### Card 07 · Main File Convention
> [!NOTE]
> **Q:** What is the conventional filename for the main FastAPI app file?
> **A:** `main.py`.
> **Key takeaway:** Keeping entrypoint naming conventional improves team readability.

### Card 08 · App Instance Creation
> [!NOTE]
> **Q:** Which class do you import to create a FastAPI app, and what line creates it?
> **A:** Import `FastAPI` from `fastapi` and create the app with `app = FastAPI()`.
> **Key takeaway:** Everything in a FastAPI app starts from a single `FastAPI()` instance.

### Card 09 · Route Binding Mechanism
> [!NOTE]
> **Q:** What Python feature maps URL paths to handler functions in FastAPI?
> **A:** Decorators.
> **Key takeaway:** Decorators define request-method + path behavior directly above handlers.

### Card 10 · Root GET Decorator
> [!NOTE]
> **Q:** Which decorator handles a GET request to the root URL?
> **A:** `@app.get("/")`.
> **Key takeaway:** Route decorators define both HTTP method and path.

### Card 11 · First Hello World Return
> [!NOTE]
> **Q:** What should a basic "Hello World" FastAPI route return?
> **A:** A dictionary like `{"message": "Hello World"}`.
> **Key takeaway:** Returning Python data structures is the normal FastAPI pattern.

### Card 12 · Auto JSON Conversion
> [!NOTE]
> **Q:** What happens if a FastAPI route returns a Python dictionary?
> **A:** FastAPI automatically serializes it to JSON in the HTTP response.
> **Key takeaway:** FastAPI handles JSON response formatting automatically for dict/list returns.

### Card 13 · Dev Server Command
> [!NOTE]
> **Q:** How do you run the FastAPI development server with auto-reload?
> **A:** Use `fastapi dev main.py` (or `uv run fastapi dev main.py`) and verify the server starts.
> **Key takeaway:** `fastapi dev` is the default development execution path.

### Section Recap Prompts
- What is the minimum code required to start a FastAPI app?
- How does `@app.get("/")` map behavior to a function?
- Why does returning a Python dictionary automatically produce JSON?

---

## 3. API Endpoints and Data Shape
**Section focus:** Model list/object responses and validate endpoint behavior for programmatic consumers.
**Cards:** `Card 14` to `Card 18`

### Card 14 · Mock Post Data Shape
> [!NOTE]
> **Q:** How should mock post data be structured in this tutorial phase?
> **A:** As a list of dictionaries with keys such as `id`, `title`, `content`, and `author`.
> **Key takeaway:** Agreeing on a clear data shape early reduces downstream confusion.

### Card 15 · Programmatic Posts Endpoint
> [!NOTE]
> **Q:** Which route is used for programmatic access to posts?
> **A:** `/api/posts`, usually implemented by a handler like `get_posts` that returns the post list.
> **Key takeaway:** `/api/...` style paths make API intent explicit.

### Card 16 · List Serialization Result
> [!NOTE]
> **Q:** If a route returns a list of dictionaries, what does the client receive?
> **A:** A JSON array of objects.
> **Key takeaway:** Python list/dict structures map directly to JSON array/object structures.

### Card 17 · Endpoint Verification
> [!NOTE]
> **Q:** What is the quick manual check for the posts endpoint?
> **A:** Open `/api/posts` in a browser and confirm the JSON array response.
> **Key takeaway:** Fast smoke checks catch routing and serialization mistakes early.

### Card 18 · Phase 2 Goal
> [!NOTE]
> **Q:** What is the main goal of the API endpoint phase?
> **A:** Build a route intended for programmatic access that returns structured data.
> **Key takeaway:** API routes should be optimized for machine consumption.

### Section Recap Prompts
- What fields should your initial post objects contain, and why?
- Why is `/api/posts` a clearer API path than a generic route?
- How do you quickly verify that list responses serialize as expected?

---

## 4. HTML Responses and Multi-Route Patterns
**Section focus:** Serve browser-facing HTML and map multiple paths cleanly to handlers.
**Cards:** `Card 19` to `Card 24`

### Card 19 · HTML Response Import
> [!NOTE]
> **Q:** Which class is needed to return HTML from a FastAPI route?
> **A:** `HTMLResponse` from `fastapi.responses`.
> **Key takeaway:** HTML routes need an explicit response class for correct response typing.

### Card 20 · HTML Decorator Parameter
> [!NOTE]
> **Q:** What decorator parameter enables proper HTML responses?
> **A:** `response_class=HTMLResponse`.
> **Key takeaway:** Response class configuration is how FastAPI knows the intended content type.

### Card 21 · HTML Handler Return Value
> [!NOTE]
> **Q:** What should an HTML route return in this tutorial style?
> **A:** A valid HTML string, for example one containing an `<h1>` tag.
> **Key takeaway:** For basic pages, raw HTML strings are enough to demonstrate rendering.

### Card 22 · Multiple Paths, One Handler
> [!NOTE]
> **Q:** How do you map both `/` and `/posts` to one function?
> **A:** Stack decorators like `@app.get("/")` and `@app.get("/posts")` above the same handler.
> **Key takeaway:** Stacked decorators are the standard FastAPI pattern for alias routes.

### Card 23 · HTML vs JSON Route Intent
> [!NOTE]
> **Q:** Why keep both HTML and JSON routes in one app?
> **A:** JSON endpoints support programmatic clients, while HTML endpoints support browser users.
> **Key takeaway:** One backend can serve both humans and systems with clear route intent.

### Card 24 · Behavior Difference by Return Type
> [!NOTE]
> **Q:** What is the practical difference between returning dict/list and returning HTML content?
> **A:** Dict/list values are auto-converted to JSON, while HTML responses are explicitly configured and rendered as web page content.
> **Key takeaway:** Return type plus decorator configuration determines client-facing behavior.

### Section Recap Prompts
- What decorator settings are required for correct HTML responses?
- When does stacking decorators improve route design?
- How do you separate browser-oriented behavior from JSON API behavior?

---

## 5. Documentation and Schema Control
**Section focus:** Use built-in docs effectively and control schema visibility for clean API documentation.
**Cards:** `Card 25` to `Card 32`

### Card 25 · Built-In Documentation UIs
> [!NOTE]
> **Q:** Which documentation UIs does FastAPI generate by default, and where?
> **A:** Swagger UI at `/docs` and ReDoc at `/redoc`.
> **Key takeaway:** API docs are available immediately without manual setup.

### Card 26 · Swagger Try It Out
> [!NOTE]
> **Q:** What does the "Try it out" feature in `/docs` provide?
> **A:** It lets you execute endpoint requests in the browser and inspect responses directly.
> **Key takeaway:** Swagger UI is not just docs; it is also an interactive test surface.

### Card 27 · Generated Curl Command
> [!NOTE]
> **Q:** What terminal-ready artifact does Swagger UI generate when you test an endpoint?
> **A:** A `curl` command you can copy and run from the terminal.
> **Key takeaway:** Swagger-generated `curl` helps bridge browser testing and CLI testing.

### Card 28 · Excluding Routes from Docs
> [!NOTE]
> **Q:** How do you hide a route from automatic API documentation?
> **A:** Add `include_in_schema=False` to the route decorator.
> **Key takeaway:** Schema inclusion is controllable per route without disabling the route itself.

### Card 29 · Pre-Cleanup Docs Observation
> [!NOTE]
> **Q:** What do you typically notice at `/docs` before excluding HTML routes?
> **A:** HTML routes appear alongside API routes in the generated schema.
> **Key takeaway:** Without filtering, docs can mix browser pages and programmatic endpoints.

### Card 30 · Post-Cleanup Docs Result
> [!NOTE]
> **Q:** After applying `include_in_schema=False` to HTML routes, what should `/docs` show?
> **A:** Only API endpoints (for example, `/api/posts`) should remain visible.
> **Key takeaway:** Clean docs improve developer focus on real API contracts.

### Card 31 · Why Exclude HTML Routes?
> [!NOTE]
> **Q:** Why is excluding HTML routes from API docs considered good practice?
> **A:** It keeps documentation focused on JSON endpoints meant for programmatic access.
> **Key takeaway:** Good docs should represent the intended consumer of each route set.

### Card 32 · ReDoc Check
> [!NOTE]
> **Q:** What should you verify at `/redoc` during exploration?
> **A:** That the alternative documentation UI loads and reflects the same schema visibility rules.
> **Key takeaway:** ReDoc is a second validation point for API schema presentation.

### Section Recap Prompts
- What roles do `/docs` and `/redoc` each play during development?
- When should `include_in_schema=False` be applied?
- How does the generated `curl` command speed up testing workflows?

---

## 6. Development vs Production Workflow
**Section focus:** Choose the right run mode for each environment and operational workflow.
**Cards:** `Card 33` to `Card 38`

### Card 33 · Dev vs Run Command Roles
> [!NOTE]
> **Q:** What is the difference between `fastapi dev` and `fastapi run`?
> **A:** `fastapi dev` is for development with auto-reload and verbose debugging, while `fastapi run` is optimized for production execution.
> **Key takeaway:** Use commands according to environment intent, not interchangeably.

### Card 34 · Primary Dev Benefit
> [!NOTE]
> **Q:** What is the main benefit of `fastapi dev` during development?
> **A:** Auto-reload restarts the server when files change.
> **Key takeaway:** Auto-reload shortens edit-test feedback loops.

### Card 35 · Production Command Choice
> [!NOTE]
> **Q:** Which command should be used in production environments?
> **A:** `fastapi run`.
> **Key takeaway:** Production should prioritize stable performance-focused execution.

### Card 36 · Default Server Port
> [!NOTE]
> **Q:** What port does the FastAPI development server use by default?
> **A:** Port 8000.
> **Key takeaway:** Knowing default ports speeds up local verification and debugging.

### Card 37 · Uvicorn's Role
> [!NOTE]
> **Q:** What is Uvicorn used for in a FastAPI project?
> **A:** It is the ASGI server that runs the FastAPI application.
> **Key takeaway:** FastAPI is the framework; Uvicorn is the runtime server process.

### Card 38 · UV-Based Dev Launch
> [!NOTE]
> **Q:** What is the `uv`-based equivalent of `fastapi dev main.py`?
> **A:** `uv run fastapi dev main.py`.
> **Key takeaway:** You can keep `uv` in the workflow while using the same FastAPI CLI behavior.

### Section Recap Prompts
- Why is `fastapi dev` best for local iteration?
- What production concerns make `fastapi run` the right choice?
- What defaults (port/server runtime) should you verify first when debugging startup?
