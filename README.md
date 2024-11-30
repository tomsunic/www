# Tom Sunic

Tom Sunic's website source repository.


To run on macbook locally:

#!/bin/bash
# Activate virtual environment
source venv/bin/activate
# Upgrade pip
pip install --upgrade pip
# Install MkDocs and necessary plugins
pip install mkdocs mkdocs-material mkdocs-meta-descriptions-plugin "mkdocs-material[imaging]"
# Verify installation (optional)
pip list | grep mkdocs
# Start MkDocs server
mkdocs serve
