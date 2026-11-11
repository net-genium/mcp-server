# Tools

The server offers 21 tools in three groups. Which of them a client sees depends on the user and the permissions of the token or the sign-in:

| Group | Available when |
|---|---|
| Documentation | the user has administrator rights |
| Reading | the permission *Reading all data and the model via the MCP server* is granted (the tools for the model, permissions and diagnostics are available with the writing permission alone as well, so the current state can be read before a change) |
| Writing | the permission *Writing all data and the model via the MCP server* is granted |

Every tool carries the standard MCP annotations: **read-only** tools never change anything, **destructive** tools can overwrite or delete existing data or parts of the application.

## Documentation

| Tool | Annotation | What it does |
|---|---|---|
| `list_framework_docs` | read-only | lists the documentation pages of the platform bundled with the instance |
| `search_framework_docs` | read-only | full-text search in the documentation, returns the matching sections |
| `get_framework_doc` | read-only | returns a documentation page or one of its sections |

## Model, permissions and diagnostics

| Tool | Annotation | What it does |
|---|---|---|
| `get_model` | read-only | the implementation model — application groups, applications, edit forms, view pages, controls, scripts and queries — narrowed to one application or form |
| `get_model_history` | read-only | saved versions of a script, a database query or the code of an HTML or JavaScript control |
| `get_permissions` | read-only | user groups and rights groups |
| `get_data_model` | read-only | the SQL data model as `CREATE TABLE` statements |
| `get_usage_statistics` | read-only | execution counts and times of forms, view pages, queries and scripts over the last 30 days |
| `get_record_counts` | read-only | the number of records of every table |
| `get_index_analysis` | read-only | which columns are used in joins and conditions without an index |
| `get_user_settings` | read-only | portlets, favourite items and view table settings of a user |
| `list_tables` | read-only | the tables available for reading and writing |

## Data

| Tool | Annotation | What it does |
|---|---|---|
| `read_data` | read-only | reads records of a table, including its change history, with an optional condition |
| `count_data` | read-only | counts records with an optional condition |
| `read_attachment` | read-only | returns the content of an attachment (image, text or file) |

## Writing

| Tool | Annotation | What it does |
|---|---|---|
| `write_data` | destructive | creates or updates a record, optionally recorded in the change history |
| `delete_data` | destructive | deletes records by id or condition |
| `create_attachment` | write | stores a new file and returns its id for a File or Image column |
| `rename` | destructive | renames an application group, application, category, form, view page or control, without changing its identifier |
| `write_model` | destructive | creates, changes and deletes application groups, applications, forms, view pages, controls, queries and scripts |
| `write_user_settings` | destructive | writes portlets, favourite items and view table settings of users |

The complete descriptions and parameters are returned by the server in `tools/list`. The behaviour of every tool is described in [The integrated MCP server](https://www.netgenium.com/en/docs/agentic-development/mcp-data-server?utm_source=github).
