### Comprehensive Guidance for Using Markdown to Push Cards to Anki and Avoid Duplicates

#### Prerequisites
1. **Anki** installed on your computer.
2. **AnkiConnect** plugin installed in Anki for communication with external tools.
3. **VSCode** with the **Anki for VSCode** extension (or a similar Markdown editor with Anki integration).

#### Installation Steps
1. **Install Anki**:
   - Download and install Anki from [https://apps.ankiweb.net/](https://apps.ankiweb.net/).

2. **Install AnkiConnect**:
   - Open Anki and go to `Tools > Add-ons`.
   - Click `Get Add-ons`.
   - Enter the following code: **2055492159**.
   - Click `OK`, and restart Anki after the installation is complete.

3. **Install VSCode and Anki for VSCode Extension**:
   - Download and install **Visual Studio Code** from [https://code.visualstudio.com/](https://code.visualstudio.com/).
   - Install the **Anki for VSCode** extension from the VSCode marketplace to enable pushing Markdown files to Anki.

#### Creating Markdown Files for Anki

1. **Specify the Deck Name**:
   - Start the Markdown file with a header to specify the deck.
     ```markdown
     # My Custom Deck
     ```

2. **Create Card Content**:
   - **Basic Cards**:
     ```markdown
     ## What is the capital of France?
     %
     Paris
     ```

   - **Cloze Cards**:
     ```markdown
     ## Fill in the blank
     The capital of France is {{c1::Paris}}.
     %
     **Explanation**: Paris is known as the "City of Light."
     ```

3. **Formatting Tips**:
   - Use `##` to denote the front of the card.
   - Use `%` or `--` to separate the front and back of the card.
   - For cloze deletions, use `{{c1::word}}` to indicate the hidden part of the sentence.

4. **Adding Hints**:
   - Provide context or hints to help recall the answer.
     ```markdown
     ## Fill in the blank
     **Hint**: A major European city
     The capital of France is {{c1::Paris}}.
     ```

5. **Tagging Cards**:
   - Add tags to organize your cards in Anki.
     ```markdown
     ## Famous Landmark
     The {{c1::Eiffel Tower}} is located in Paris.
     %
     **Tags**: #landmark #France
     ```

#### Avoiding Duplicate Cards

1. **Set Parameters in VSCode**:
   - Ensure the following settings are configured in the **Anki for VSCode** extension:
     - `anki.md.updateCards`: Set this to `true` to allow updates to existing cards instead of creating duplicates.
     - `anki.md.insertNewCardID`: Set this to `true` so that each card has a unique Note ID, allowing updates instead of duplication.

2. **Update Cards**:
   - If a card already exists in Anki (with a matching Note ID), pushing the Markdown file will update the existing card's fields and tags.

3. **Ensure Unique Note IDs**:
   - Verify that your cards have unique `NoteID` properties to prevent Anki from interpreting them as new cards.

#### How to Set Up Parameters in VSCode

1. **Open VSCode Settings**:
   - Go to `File > Preferences > Settings` or press `Ctrl + ,` (Windows) or `Cmd + ,` (Mac).
   - Search for "Anki" and locate `anki.md.updateCards` and `anki.md.insertNewCardID`.
   - Set both to `true`:
     ```json
     "anki.md.updateCards": true,
     "anki.md.insertNewCardID": true
     ```

2. **Ensure Markdown Files Are Configured**:
   - Ensure your Markdown content includes unique content or Note IDs that match existing Anki cards if updates are required.

#### Pushing Cards to Anki
1. **Save Your Markdown File**.
2. **Use VSCode to Push**:
   - Run the `Anki: Send To Deck` command to push cards to Anki.
   - Ensure Anki is open and AnkiConnect is running.

#### Best Practices
- **Regular Backups**: Always back up your Anki database before making large-scale changes.
- **Consistent Formatting**: Use a consistent structure in your Markdown files for easier management and updates.
- **Testing**: Start by pushing a few cards to ensure everything works as expected before importing larger sets.
