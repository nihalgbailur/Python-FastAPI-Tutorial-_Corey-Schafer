# FastAPI Tutorial (Part 1) — Practice Challenges

Based on the **"Python FastAPI Tutorial (Part 1)"** video. Work through the phases in order.

---

## Phase 1: Installation and Basic Setup
**Goal:** Get a basic "Hello World" application running.

1. **Environment setup**
   - Create a new project directory (e.g., `fastapi_blog`).
   - Install FastAPI:
     - Using UV (as the instructor does): `uv add fastapi[standard]`
     - Using pip: `pip install "fastapi[standard]"`
2. **Create the app**
   - Create `main.py`.
   - Import `FastAPI` and create an instance: `app = FastAPI()`.
3. **First JSON route**
   - Add `@app.get("/")`.
   - Define a function (e.g., `home`) that returns `{"message": "Hello World"}`.
4. **Run the server**
   - Start dev server: `fastapi dev main.py` (or `uv run fastapi dev main.py`).
   - Confirm the server starts successfully.

---

## Phase 2: Building the API Endpoint
**Goal:** Create a route intended for programmatic access that returns structured data.

1. **Mock data**
   - Create a list of dictionaries to represent posts.
   - Each post should include: `id`, `title`, `content`, `author`.
2. **API route**
   - Add a route at `/api/posts`.
   - Implement `get_posts` to return the list.
3. **Verification**
   - Visit `/api/posts` in the browser and confirm FastAPI returns a JSON array.

---

## Phase 3: Returning HTML for Humans
**Goal:** Serve HTML pages instead of only raw data.

1. **Import HTMLResponse**
   - `from fastapi.responses import HTMLResponse`
2. **HTML route configuration**
   - Add `response_class=HTMLResponse` to the route decorator.
   - Return a string of valid HTML (e.g., an `<h1>` with a post title).
3. **Stacked decorators**
   - Use multiple decorators so both `/` and `/posts` render the same HTML.

---

## Phase 4: Documentation Cleanup
**Goal:** Separate API endpoints from browser views in the docs.

1. **Check the docs**
   - Visit `/docs` (Swagger UI).
   - Note that HTML routes currently appear with API routes.
2. **Hide HTML routes**
   - Add `include_in_schema=False` to the HTML route decorators.
3. **Verify cleanup**
   - Refresh `/docs` and confirm only `/api/posts` appears.
4. **Test the API**
   - Use **Try it out** in Swagger UI to call `/api/posts` and view the JSON response.

---

## Exploration Tasks
- **Locate the curl command**: In `/docs`, after **Try it out**, copy the generated `curl` command and run it in your terminal.
- **Check ReDoc**: Visit `/redoc` to see the alternative documentation UI.

---

## Interview Questions (Non-Overlapping Additions)

Based on the provided tutorial transcript, here are additional questions that do not duplicate existing sections above.

1. **What are the key features that make FastAPI a "modern" framework?**
   - **Answer:** FastAPI is designed to be fast and modern, with automatic API docs, built-in data validation, and native async/await support.
2. **Does FastAPI require `async` functions for every route?**
   - **Answer:** No. FastAPI supports both synchronous (`def`) and asynchronous (`async def`) route handlers.
3. **What is the difference between running an app with `fastapi dev` versus `fastapi run`?**
   - **Answer:** `fastapi dev` is for development with auto-reload and verbose output, while `fastapi run` is optimized for production performance.
4. **What is `uv`, and how was it used in the tutorial?**
   - **Answer:** `uv` is a fast Python package manager used to install dependencies like `fastapi[standard]`.
5. **What is included when you install `fastapi[standard]`?**
   - **Answer:** It includes FastAPI, the FastAPI CLI tools, and `uvicorn` (the ASGI server).
