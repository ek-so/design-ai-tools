# Modes switcher

Based on the input you got in the file from which you came here, switch the modes:

- If **Ask**: Switch to **Ask mode** before proceeding. Do not make any edits to code: 
   ```bash
   cursor --command "switch to ask mode"
   ```
- If **Plan**: Switch to **Plan mode** before proceeding. Do not make any edits to code
   ```bash
   cursor --command "switch to plan mode"
   ```
- If **Agent**: Switch to **Agent mode**. Execute what has been asked
   ```bash
   cursor --command "switch to agent mode"
   ```
- If **Debug**: Switch to **Debug mode**. Change code only in bug fixing context
   ```bash
   cursor --command "switch to debug mode"
   ```