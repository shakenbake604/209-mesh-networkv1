# Copilot Instructions for 209-mesh-networkv1

## Repository Overview

This is the **209 Mesh Network** project — the first build of the 209 Network. The repository contains self-paced lab materials and infrastructure code for a mesh networking environment, including AI/ML lab exercises using Google Gemini.

## Project Structure

```
209-mesh-networkv1/
├── README.md                  # Project overview
└── self-paced-labs/           # Self-paced learning lab materials
    └── gemini/                # Google Gemini AI labs
        └── *.ipynb            # Jupyter notebooks for hands-on exercises
```

## Tech Stack

- **Jupyter Notebooks** (`.ipynb`) — used for self-paced lab exercises
- **Google Gemini** — AI/ML multimodal capabilities explored in labs
- **Python** — primary language used in notebooks

## Coding Conventions

- Jupyter notebooks should follow clear cell organization: markdown cells for explanations, code cells for implementation
- Use descriptive variable names and add inline comments for complex logic
- Keep notebooks reproducible: document dependencies clearly and avoid hardcoded paths
- Prefer modular code cells that can be run independently when possible

## Working with Notebooks

- To run notebooks locally, install Jupyter: `pip install jupyter`
- Launch Jupyter: `jupyter notebook` or `jupyter lab`
- Ensure required Python packages are installed before running cells (check the first cells of each notebook for setup instructions)

## Lab Content Guidelines

- Lab instructions should be written in clear, step-by-step markdown
- Include expected outputs or screenshots where helpful
- Provide context on what each section teaches before the code
- When updating Gemini labs, refer to the [Google Generative AI Python SDK](https://github.com/google/generative-ai-python) for the latest API usage
