# Query Mind AI — Natural Language to SQL Converter

An interactive Jupyter notebook that turns plain-English questions into SQL, powered by the Groq API. It includes five tools in one notebook, each with a simple widget interface (dropdowns, text boxes, buttons).

✨ Features
#	Feature	What it does
1	🧠 Natural Language → SQL	Type a question, get a SQL query with an explanation, step-by-step breakdown and a performance tip
2	💬 Multi-turn Refinement	Refine a query by chatting ("only delivered orders", "sort by total", "limit to 5"). The conversation history is sent with each turn
3	📊 Smart Chart Picker	Paste CSV data and the notebook picks a suitable chart type automatically
4	🔄 SQL Dialect Converter	Convert queries between MySQL, PostgreSQL, SQLite, SQL Server and Oracle, with a list of changes made
5	📁 CSV → Schema Generator	Paste CSV data, infer column types and generate a CREATE TABLE statement
🗃️ Built-in sample schemas
🛒 E-Commerce: customers, orders, order_items, products
👥 HR System: employees, departments, attendance, payroll
🎓 School: students, courses, enrollments, instructors

You can edit the schema text in the widget to match your own tables.

🛠️ Tech stack

Python · Groq API (LLM) · Jupyter Notebook · ipywidgets · pandas · matplotlib

🚀 Getting started
1. Clone the repository
bash
git clone https://github.com/korsalasya/Query-mind-AI-natural-language-to-Sql-converter-.git
cd Query-mind-AI-natural-language-to-Sql-converter-
2. Install dependencies
bash
pip install -r requirements.txt
3. Get a free Groq API key
Go to console.groq.com and sign in.
Open API Keys → Create API Key and copy the key (it starts with gsk_).
4. Add your key

Copy .env.example to .env and paste your key:

GROQ_API_KEY=gsk_your_key_here

.env is listed in .gitignore, so your key is never uploaded.

5. Run the notebook

Open advanced_sql_generator.ipynb in VS Code or Jupyter and choose Run All.

Using VS Code? The first time the widgets load, click Enable Downloads when VS Code asks to fetch the @jupyter-widgets files.

🤖 Choosing a model

The default model is llama-3.1-8b-instant. To use another one, set GROQ_MODEL in your .env. Groq changes its model list over time, so check console.groq.com/docs/models for current names. A 404 model not found error means the name is no longer available.

💡 Example questions

Natural language → SQL (E-Commerce)

Show me the top 5 customers by total order value
Which product category has generated the most revenue?
Find customers who have never placed an order

Multi-turn refinement

Show all orders
Only show the delivered ones
Add the customer name
Sort by total, highest first
Limit to the top 5
🧩 How it works

Each feature sends a prompt with the schema (or SQL) to Groq's chat API, asks for a JSON reply, and renders the result in the notebook. Multi-turn mode keeps the full message history, so each follow-up modifies the previous query instead of starting over.

⚠️ Notes
Generated SQL should always be reviewed before running it on a real database.
The free Groq tier has rate limits.
Never commit your API key. If it is ever exposed, delete it in the Groq console and create a new one.
📄 License

MIT. See LICENSE.
