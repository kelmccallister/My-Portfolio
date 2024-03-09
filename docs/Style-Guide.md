# Style Guide

=== "Introduction"

    ## Introduction

    This *Style Guide* document defines basic grammatical formatting requirements involved in creating documentation. Using these standards allows writers to spend more time on content over formatting and layout, provide consistency across all content, and makes the writing process easier. This is a living document that evolves with the organization. Feedback and suggestions for improvement are valuable, and it is encouraged to actively participate in refining the formatting and writing standards.

    ??? note
        The following rules and conventions apply mostly to Markdown documents but should be applied where possible within other types of documentation (e.g., Microsoft Word files).
    
    ### When to Use Standards

    The standards in this document apply to all documentation; however, they can be tailored as necessary to accommodate exceptions.

    ### Purpose of Standards

    Document standards are rules, models, or examples that writers follow that allow focus to remain on content while creating quality, consistent, and professional documents. Standards help both the writer and the reader. Having and consistently using standards:

    - Reduces time spent on developing a look or layout
    - Allows time to be spent on content
    - Increases the professional look and feel of documents
    - Aids readers in navigating and understanding content
    - Provides a consistent look and feel throughout a library of materials

=== "Formatting Standards"

    ## Formatting Standards

    When working with Markdown, adhering to consistent formatting standards is essential for clarity and readability. Document conventions should be consistent throughout all documentation.

    ### Conventions

    The following table illustrates the conventions that should be used when writing procedures or describing features of software applications and UI objects. 

    | Features | Convention | Example |
    |----------|------------|---------|
    | Appendices | (1) Use Heading 1 (2) Use letters instead of numbers for numbering | Appendix A, Appendix B |
    | Buttons | (1) Bold (2) Do not use the word "the" or "button" (3) Use the term "click" when referring to buttons | Click **Ok** | 
    | Check boxes, spin boxes, and radio buttons | (1) Bold (2) Use the term “select” or “clear” not “click” | Select the **Current** radio button |
    | Code | Enter three backticks and "sh" to begin the code section and enter three backticks to end it | N/A |
    | Columns | (1) Bold (2) Name of the column goes before the word "column" | The **Contracts** column displays |
    | Directory or path | (1) Italics (2) Sentence styles; capitalization follows the UI | Vacation and and sick pay are located at *MyFiles/Accounting/Payroll/VacPay* |
    | Document names | Italics | Installation steps can be found in the *AGM v4.3 Installation Guide* |
    | Drop-down lists and related options | (1) Bold (2) Use the term "select"  when referring to drop-down lists (3) Hyphenate the term "drop-down" | Select **Address** from the **Search By** drop-down list |
    | Field entries and other text areas | Enclose text to be entered in quotation marks | Enter "1" into the **Days** filed |
    | Field names | (1) Bold (2) Use the terms "enter" when referring to entering text into fields; not "type" | Enter a title in the **Title** field |
    | File Names | Enclose the file name in backticks | Open the `document1.doc` folder |
    | Filter names | (1) Bold (2) Name or filter goes before the word "filter" |  The **Success Track** fileter allows |
    | Folder names | Italics | Select the *Examples* folder |
    | Icons | (1) Bold (2) Use the term "select" when referring to icons (3) Use the name of the icon; not the image | Select the **Word** icon to launch MS Word |
    | Keystrokes | (1) Bold (2) Use the "+" (no space) to indicate simultaneous keystrokes (3) Use the term "press" when referring to keystrokes | Press **Alt**+**F7** |
    | Links | Bold | Click the **Additional information** link | 
    | Means and menu options | (1) Bold (2) Use the term "select" when referring to menu names and options (3) For nested menu options use an (>) with a space on either side | Select **File** > **New** > **Document** |
    | Navigation | Bold the words and the arrow | Navigate to **Directories > Folders > Files** | 
    | Notes and warnings | Use collapsable admonition blocks | N/A |
    | Page names | (1) Bold (2) Use "displays" not "opens" | The **Home** page opens |
    | Parameter names | (1) Italics (2) Capitalization varies | *createNewOffer* |
    | Placeholder text | Use brackets | File should be named [Project] | 
    | Roles | (1) Bold (2) Capitalized | The **Requestor** must follow up |
    | Tabs and panels | (1) Bold (2) Use the term "click" and "displays" when referring to tabs and panels | Click the **Workload** tab |
    | Tiles | (1) Bold (2) Use "Select" | Select the **Cases** tile |
    | Windows | (1) Bold (2) Use the terms "open" and "close" when referring to a window; do not use "appear" or "disappear" (3) Use the term "in" when referring to objects in a window (4) Do not use "screen" | The **Customers** window opens |

    ### Covers, Headers, and Footers
    
    Covers, headers, and footers are not required for Markdown documents. 

    ### Font

    GitHub Pages does not have specific font settings that can be adjusted within its platform.

    ### Headings

     Headings alert the reader to the importance of information (e.g., Heading 1 contains general information, while Heading 4 contains more specific information). When used effectively, they also allow a reader to quickly navigate through a document to find required information.

     The numbering of headings is not required for documents where numbering would interfere with the usefulness of the document. For instance, Markdown documents should not have numbered headings because it would interfere with exporting them to PDF.

=== "Writing Standards"

    ## Writing Standards
    
    The standards and guidelines referenced below illustrate the correct use of grammar, spelling, and formatting that should be followed for all content.

    ### Abbreviations

    The following abbreviations are used in documentation:
    
    - For example: (e.g., xxx)
    - In other words; that is: (i.e., xxx)
    - And so on: etc.

    ### Acronyms

    An acronym is a word formed from the initial letters of a name. The first time an acronym is used in a document, it must be spelled out and followed by the acronym in parenthesis (e.g., Point of Contact (POC)). Then only the acronym is used throughout the remainder of the document. If a term is not repeated, then the acronym should not be defined.

    ### Contractions

    Do not use contractions.

    ### Cross References 

    Cross references refer to readers from one part of a document or file to another part of the same document or file containing related information. When cross-referencing material, use the term “refer to” preceding a reference; do not use “see”. Use the following standards to refer to specific information commonly referred to throughout documents. 

    #### Sections
    
    When referring to a section, include the title and italicize it. 
    
    #### Figures and Tables
    
    When referring to numbered figures or tables, include the word “Figure” or “Table” and the name, if any, and italicize it.
    
    #### Other Documents
    
    When referring to another document, the title of the document should display in italics. It is best practice is to avoid referring to chapters or sections in another document. If available, include a hyperlink.

    ### Dates

    It is best practice to use the long form of the date Write the full name of the month and Arabic numerals for the day and full year (e.g., March 8, 2024). Do not use military or international date formats unless it is mandated by a specific document’s requirements.

    ### Figures and Screenshots

    Figures and screenshots should be displayed after the steps that cause them to display. They should also have a dark gray boarder added before being uploaded to the repository.

    ### Jargon

    Jargon is a specialized term or technical language that is understood only by a particular group. Avoid using jargon.

    ### Lists 

    Lists are made up of three or more items and can be numbered or bulleted, and run-in or vertical. 

    #### Numbered Lists

    Numbered lists should be used to indicate an order of interdependent steps or a ranking of one item over another. A number or letter and a period precedes items in chronological lists to indicate a sequence. When used within a paragraph (i.e., run-in style), the number or italicized letter is placed in parentheses. 

    #### Bulleted Lists

    Bulleted lists are typically used for items that are of equal importance or when the sequence doesn't matter. Bulleted lists with fragmented statements should not include punctuation.

    ### Notes and Warnings

    Notes are used to highlight material with special importance. Warnings are used to warn readers about possible damage to equipment or data based on what they are doing and should be used sparingly to emphasize their importance. Notes and warnings must be written as collapsable admonitions in Markdown.

    ### Numbers

    Spell out all numbers from zero to ten. All other numbers are written out in Arabic form. When specifying a range of numbers, write all numbers in Arabic form regardless of the number (e.g., follow steps 1 through 5). When a sentence starts with a number, spell out the number regardless of its size. 

    ### Punctuation

    The following table provides examples of how and when to use commonly used punctuation.

    | Punctuation | Convention |
    |-------------|------------|
    | Period (.) | Use one space after the period |
    | Comma (,) | Separates a series of three or more items; when a conjunction seperates the last two items, place a comma before the conjuction ( e..g, red, white, and blue) |
    | Colon (:) | Use one space after a colon |
    | Semi-colon (;) | Use one space after a semi-colon |
    | Quotation marks (“) | Periods and commas are always placed inside; question mark placement is determined by whether the question is part of the quote (i.e., inside) or the sentence (i.e., outside); use only one ending punctuation mark (i.e., if the period is within the quotation mark, and a questions mark is outside the quotation mark, omit the period) |
    | Single quotation marks (‘) | Use only for quoting within other quotes; period is always placed inside | 

    ### Spelling

    Misspelled words are easy to correct. Use spell check (e.g., Vale) on all documents.

    ??? note 
        Spell check will not correct a word that is used incorrectly and may miss legitimate words that are used incorrectly (e.g., I have to pens).

    ### Tables

    Tables allow writers to present information in an easy to view format. Tables in Markdown can be created by using a combination of vertical bars (|) and hyphens (-) to define the table structure. Alignment can be specified within cells using colons in the header row. (e.g., ":- - -" or "- - -" indicates left alignment, ":- - -:" indicates center alignment, and "- - -:" indicates right alignment.) Left-justified text is the default; it is recommended, but not required. Bulleted and numbered lists within tables are not available in Markdown. Instead, use the run-in style defined in *Lists* section of this document.

    ### Voice

    Write in the active voice. "You" is implied, but not used.

=== "Key Principles"

    ## Key Principles

    Well-crafted documentation should have the following qualities.

    ### Concise

    Instructions that are easy to understand are most effective. Avoid adding extraneous information. Keep sentences short. Strive for minimalist writing when appropriate.

    ### Consistent

    Consistency is key. Using the same labeling, terminology, writing styles, and voice throughout the documentation drives clarity.

    ### Grammatically Correct

    Grammatical errors in a document can create confusion among readers and can change the meaning of the content resulting in misinformation. Always perform a spell and grammar check.

    ### Well-Organized

    Content should be organized in a logical sequence. A well-organized document ensures that the audience can easily follow and find information.

    ### Technically Accurate

    It is important that document content is technically accurate, presented in a clear and concise manner, and is appropriate for the audience which it is intended for. To ensure accuracy, content should be reviewed by Subject Matter Experts, Product Owners, and any other interested parties. Inaccuracies in any part of the document can diminish a reader’s confidence in the content.

    ### Useful
    
    Content should advance the understanding of the product. Always check with leadership if there is any uncertainty.

| Sign-off Date | Name |
|------|------|
| 03/07/2024 | Mickey Mouse |
