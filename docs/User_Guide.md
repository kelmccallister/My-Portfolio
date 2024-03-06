#  User Guide: Publishing to GitHub Pages 
GitHub Pages are public webpages hosted and published through GitHub. The following sections provide instruction on how to set up a GitHub pages site. Complete them in order.

??? note "Important Note"
    These instructions are for Windows only.

## Prerequisites

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
2. CLick **New** at the top of the dashboard.

    ![](../assets/images/userguide_newbutton.png)

3. Enter the new repository name within the corresponding field.
4. Provide any additional settings.
5. CLick **Create repository** at the bottom of the screen.

## Clone the Repository

1. Click **<> Code**.
   
    ![](../assets/images/userguide_codebutton.png)

2. Copy the URL.
3. Open GitHub Desktop.
4. Select the **Current repository** drop-down menu.

    ![](../assets/images/userguide_currentrepo.png)

5. Click **Ad** > **Clone repository**.

    ![](../assets/images/userguide_clonerepo.png)

6. Select the **URL** tab.
7. Paste the URL into the corresponding field.
8. Click **Clone**.

    ![](../assets/images/userguide_cloneurl.png)

## Create a New Branch

1. Select the cloned repository from the **Current repository** drop-down menu.
2. Select the **Current branch** drop-down menu.
3. Ensure the current branch selected is "main".
4. Click **New branch**.

    ![](../assets/images/userguide_newbranch.png)

5. Enter the branch name into the corresponding field.
6. Click **Create branch**.

    ![](../assets/images/userguide_createbranch.png)

7. Click **Publish branch**.

## Create a Virtual Environment

??? info
    Setting up a virtual environment within a repository's directory using python's venv module provides the ability to preview changes made before making a commit by running a web server that exposes the website at [`http://127.0.0.1:8000`](http://127.0.0.1:8000).

1. Click **Open in Visual Studio Code** in GitHub desktop.
2. Open the terminal in Visual Studio Code.
3. Enter the following commands into the terminal:

    ```sh
    python -m venv ./venv
    ./venv/scripts/activate
    ```

4. Run:

    ```sh 
    mkdocs serve
    ```

5. Open the provided `http://127.0.0.1:8000` link.

## Configure the Repository

1. Run the following command in the VS Code terminal to create the **docs** folder and the *mkdocs.yml* and *index.md* files:
    
    ```sh
    mkdocs new .
    ```

2. Open the *mkdocs.yml* file.
3. Add the following plugins to the file:

    === "MkDocs Material Plugins"
    
        ```sh
        theme:
          name: material
          icon:
            repo: fontawesome/brands/github
            edit: material/pencil
          features:
            - navigation.tabs
            - navigation.tracking
            - navigation.expand
            - toc.integrate
            - content.action.edit
          language: en
        ```

    === "Python Plugins"

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
        - md_in_html
        - sane_lists
        - tables
        ```

4. Save the changes.
5. Create a new **.github** folder.
6. Create a **workflows** sub-folder within the **.github** folder.
7. Create a new *ci.yml* file within the **workflows** folder.
8. Paste the following into the *ci.yml* file:

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
          - run: mkdocs gh-deploy --force
    ```

9. Save the changes.
10. Commit the changes to Main.

## Publish to GitHub Pages

1. Access GitHub Browser. 
2. Navigate to the repository being used.
3. Select the **Settings** tab at the top of the screen.

    ![](../assets/images/userguide_settings.png)

4. Select **Pages** from the left-hand side menu.
5. Select **gh-pages** from the **branch** drop-down menu and select **/(root)** from the **file** drop-down menu under the page's Branch section.

    ![](../assets/images/userguide_branchsettings.png)

6. Click **Save**.
7. Click **Visit Site** at the top of the page; no further action needed.

    ![](../assets/images/userguide_visitsite.png)
