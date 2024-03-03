# User Guide: Set Up GitHub Pages
GitHub Pages are public webpages hosted and published through GitHub. There are three types of GitHub Pages sites: project, user, and organization. Project sites are connected to a specific project hosted on GitHub, such as a JavaScript library or a recipe collection. User and organization sites are connected to a specific account on GitHub.com. This site is an example of a project site.

!!! note
    These instructions are for Windows only.

## Prequisites

### Installing Tools

Ensure that the following tools/programs have been installed:

- [Git](https://git-scm.com/downloads)
- [GitHub Desktop](https://desktop.github.com/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [MkDocs](https://www.mkdocs.org/getting-started/)
    - MkDocs requires [Python and Pip](https://www.python.org/downloads/) be installed. 
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/getting-started/)
- [Vale](https://tw-docs.com/docs/vale/install-vale/)
    - Vale is used to check spelling.

## Create a Repository

1. Access GitHub browser.
2. Select the **New** button on the top, left-hand side of the dashboard.
3. Provide the new repository name within the corresponding field.
4. Provide any additional settings.
5. Select the **Create repository** button on the bottom, right-hand side of the screen.

## Create a Virtual Environment

The following steps provide intstructions on setting up a virtual environment using python's venv module within a repository's directory. This provides the ability to preview changes made to the repository before making a commit. As a result of these steps, a web server will run that exposes the website at [`http://127.0.0.1:8000`](http://127.0.0.1:8000).

1. Clone the repository in GitHub Desktop.
2. Open the repository in Visual Studio Code ("VS Code") via GitHub Desktop.
3. Enter the following commands into the VS Code terminal:

    ```sh
    python -m venv ./venv
    ./venv/scripts/activate
    ```

4. Run:

    ```sh 
    mkdocs serve
    ```

## Configure the Repository

1. Open the terminal within VS Code.
2. Create the `mkdocs.yml` and `index.md` files by running:
    
    ```sh
    mkdocs new .
    ```

3. Access the `mkdocs.yml` file.
4. Add the following MkDocs Material plugin:

    ```sh
    theme:
      name:  material
    ```

5. Add the following features under the MkDocs Material plugin:
    ```
    icon:
      repo: fontawesome/brands/github
      edit: material/pencil
    features:
      - navigation.tabs
      - navigation.sections
      - toc.integrate
      - navigation.top
      - content.tabs.link
      - content.code.annotation
      - content.code.copy
      - content.action.net
    language: en
    ```

5. Add the following python plugins:

    ```sh
    markdown_extensions:
    - admonition
    - codehilite
    - smarty
    - pymdownx.magiclink
    - pymdownx.betterem
    - pymdownx.details
    - pymdownx.emoji
    - pymdownx.saneheaders
    - pymdownx.highlight
    - pymdownx.critic
    - pymdownx.caret
    - pymdownx.mark
    - pymdownx.tilde
    - pymdownx.inlinehilite
    - pymdownx.tabbed:
        alternate_style: true
    - pymdownx.tasklist:
        clickable_checkbox: true
    - pymdownx.superfences:
        custom_fences:
          - name: mermaid
            class: mermaid
            format: !!python/name:pymdownx.superfences.fence_code_format  
    - pymdownx.tasklist:
        custom_checkbox: true          
    - attr_list
    - sane_lists
    ```

6. Save the changes.
7. Create a new folder and name it `.github`.
8. Create a sub-folder within `.github` and name it `workflows`.
9. Create a new file within the `workflows` folder and name it `ci.yml`.
10. Paste the following into the `ci.yml` file:

    ```
    name: ci
    on:
      push:
        branches:
          - master
          - main
    permissions:
      contents: write
    jobs:
      deploy:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v3
          - uses: actions/setup-python@v4
            with:
              python-version: 3.x
          - uses: actions/cache@v2
            with:
              key: ${{ github.ref }}
              path: .cache
          - run: pip install mkdocs-material
    ```

11. Save the changes.
12. Commit the changes to `main`.

## Create a Website

1. Access Github Browser. 
2. Navigate to the repository being used.
3. Select **Settings** from the tabs at the top of the screen.
4. Select **Pages** from the left-hand side menu.
5. Under the *Branch* section, select `gh-pages` from the branch drop-down menu and select `/(root)` from the file drop-down menu.
6. Select the **Save** button.
7. Select the **Visit Site** button at the top of the page.

## Conclusion
GitHub pages has now been successfully setup.  

!!! warning
    Only add new site pages (i.e., files) under the `docs` folder.