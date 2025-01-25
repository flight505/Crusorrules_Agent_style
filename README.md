# CursorRules-Agent-Style

A sophisticated tool for managing AI agents in complex codebases through intelligent file-tree partitioning. It prevents conflicts and maintains coherence by creating clear boundaries for each AI assistant.

## Overview

CursorRules-Agent-Style solves the challenge of coordinating multiple AI assistants in large projects by:

1. Creating distinct domains (frontend, backend, etc.)
2. Generating domain-specific context files
3. Enforcing strict boundaries through file-tree partitioning
4. Providing clear rules and context for each AI assistant

Here are the key changes:

-  **Added `--project-path` argument** to specify the target project directory.
-  **Separated config directory** (where the script runs) from the project directory (where files are generated).
-  **Implemented automatic copying** of `.cursorrules` to the project directory.
-  **Updated all path handling** to work with external project paths.
-  **Maintained config files** in the tool's directory while generating output files in the project directory.

## Usage Instructions 🛠️

Now you can use it like this:

1. **Clone the repo anywhere:**
   ```bash
   git clone https://github.com/s-smits/agentic-cursorrules.git
   cd agentic-cursorrules
   ```

2. **Set up the environment:**
   ```bash
   uv venv
   source .venv/bin/activate
   uv pip install -r requirements.txt
   ```

3. **Create your `config.yaml`** in the `agentic-cursorrules` directory.

4. **Run with project path:**
   ```bash
   python main.py --project-path /Users/Projects/Dev_projects/"your project dir"
   ```
Or add the --recurring flag 
   ```bash
   python main.py --recurring --project-path /Users/Projects/Dev_projects/"your project dir"
   ```

### What the Tool Will Do 🔧

-  Keep configuration files in the `agentic-cursorrules` directory.
-  Generate and copy agent files to your project directory.
-  Automatically copy `.cursorrules` to your project if needed.

## Configuration

Define your project structure in `config.yaml`:

```yaml
project_title: "my-project"
tree_focus:
  - "frontend"    # UI components
  - "backend"     # API services
  - "database"    # Data layer
  - "shared"      # Common utilities
```

## Generated Agents

The tool creates specialized markdown files for each domain:

- `agent_frontend.md`: UI development focus
- `agent_backend.md`: API and services focus
- `agent_database.md`: Data layer operations
- `agent_shared.md`: Common utilities

## Best Practices

1. **Domain Separation**
   - Keep domains focused and specific
   - Limit to 3-4 concurrent agents
   - Define clear boundaries

2. **File Organization**
   - Use semantic naming
   - Maintain clean directory structure
   - Document domain interfaces

3. **Agent Management**
   - One agent per domain
   - Regular boundary reviews
   - Clear communication paths

## IDE Support

Optimized for:
- Cursor IDE (primary)
- VS Code with AI extensions
- Other AI-enhanced editors

## Technical Details

- Written in Python
- YAML configuration
- Markdown-based context files
- Intelligent file-tree analysis
- Automatic boundary enforcement

## License

MIT License - See LICENSE file for details
