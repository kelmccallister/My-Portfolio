#  User Guide: Publishing to GitHub Pages 
GitHub Pages are public webpages hosted and published through GitHub. The following sections provide instructions on how to set up a GitHub pages site. Complete them in order.

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

1. Open GitHub browser.
2. Click **New** at the top of the dashboard.

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

5. Click **Add** > **Clone repository**.

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
    Setting up a virtual environment within a repository's directory using Python's venv module provides the ability to preview changes made before making a commit. It will run a web server that exposes the website at [`http://127.0.0.1:8000`](http://127.0.0.1:8000).

1. Click **Open in Visual Studio Code** in GitHub Desktop.
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
5. Click the **New Folder** icon.
6. Enter ".github/workflows" into the name field.
7. Click the **New File** icon.
8. Enter "ci.yml".
9. Open the *ci.yml* file.
10. Paste the following into the file:

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

11. Save the changes.
12. Click the **Extensions** icon on the left-hand side navigation menu.
13. Enter "Vale" into the **Search** field.
14. Click **Install**.
15. Click the **Manage** icon.
16. Select **Extension Settings** from the drop-down list.
17. Check **Enable spell checking with Vale**.
18. Click the **Explorer** icon on the left-hand side navigation menu.
19. Click the **New File** icon.
20. Enter ".vale.ini".
21. Open the *.vale.ini* file.
22. Paste the following into the file.
    
    ```sh
    StylesPath = .github/styles

    MinAlertLevel = warning

    Vocab = vale

    [*.md]
    BasedOnStyles = Vale
    ignore = URL, Consistency

    Vale.Terms = NO
    ```

23. Save the changes.
24. Select the **.github** folder
25. Click the **New Folder** icon.
26. Enter "styles/config/vocabularies/vale". 
27. Click the **New File** icon.
28. Enter "accept.txt".

    ??? note
        The *accept.txt* file allows rule exceptions (e.g., what is considered a spelling error).

29. Save the changes.
30. Commit the changes to `Main`.

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
