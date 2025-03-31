# Rafael Julio Lemos Silva's CV

This repository contains my CV in both English and Portuguese, generated using [RenderCV](https://github.com/sinaatalay/rendercv) - a YAML-to-PDF LaTeX-based CV/resume generator.

## Repository Structure

```txt
📁 src/
  📁 en-US/            # English version of CV
    📄 input.yaml      # CV content in YAML format (English)
  📁 pt-BR/            # Portuguese version of CV
    📄 input.yaml      # CV content in YAML format (Portuguese)
📁 .devcontainer/      # Development container configuration
📁 .github/workflows/  # CI/CD pipeline for automated releases
📁 .vscode/            # VS Code configuration
📄 requirements.txt    # Python dependencies (RenderCV)
```

## Setup and Usage

### Local Development

1. **Using DevContainer (recommended)**:
   - Open the repository in VS Code with the [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension
   - VS Code will automatically build the container with Python and required dependencies

2. **Manual Setup**:
   - Install Python 3.12+
   - Install dependencies: `pip install -r requirements.txt`

### Generating CVs

1. **Using VS Code Launch Configurations**:
   - Open the Run and Debug panel in VS Code
   - Select "Run RenderCV (English)" or "Run RenderCV (Portuguese)"
   - Press the play button to generate the CV

2. **Using the Command Line**:

   ```bash
   # Generate English CV
   rendercv render src/en-US/input.yaml

   # Generate Portuguese CV
   rendercv render src/pt-BR/input.yaml
   ```

3. **Output**:
   - Generated files are stored in the out directory
   - Each language has its own subdirectory (en-US and pt-BR)
   - Both PDF and TEX files are generated

### Automated Releases

This repository uses GitHub Actions to automatically generate and release CV versions:

1. **Release Process**:
   - When a new tag is pushed, the workflow generates both English and Portuguese versions
   - Generated PDFs and TEX files are attached to the GitHub release
   - Access the latest release from the [Releases](https://github.com/username/cv/releases) page

2. **Triggering Releases**:

   ```bash
   # Create a new tag
   git tag v1.0.0

   # Push the tag to trigger the release workflow
   git push origin v1.0.0
   ```

### Troubleshooting

If you encounter LaTeX rendering issues with RenderCV's built-in TinyTeX, you can use your local LaTeX installation:

```bash
# Using local LaTeX installation (recommended for complex documents)
rendercv render --use-local-latex-command lualatex src/en-US/input.yaml
```

## Customization

To modify CV content, edit the respective YAML files in the src directory:

- For English: input.yaml
- For Portuguese: input.yaml

The structure follows RenderCV's schema for sections like education, experience, skills, etc.
