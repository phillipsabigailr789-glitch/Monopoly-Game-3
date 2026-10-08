# STI-OPOLY — Start Game repair

This package fixes the incomplete `drawActions()` function in the original uploaded `app.js`, adds a directly attached Start Game click handler and visible action status, and cache-busts the script URL.

## Update the existing Render site

1. Extract this ZIP. Upload the project files (not the ZIP) to the root of your existing GitHub repository, replacing the old files. Keep `package.json`, `server.js`, `app.js`, `data.js`, `index.html`, `display.js`, and `display.html` together in the repository root.
2. Commit the changes. In Render, wait until the latest deployment says **Live**. Make sure it deployed that new GitHub commit.
3. Visit your site and press Ctrl+Shift+R. Create a **new room**; all players should join the new code. A Render redeploy erases previous in-memory rooms.
4. Click Start Game as the room creator. The page should show `Start button clicked. Contacting server…`, followed by the turn controls.
5. If no status appears, view page source and confirm it references `app.js?v=20261008-finalfix3`. If it doesn't, Render is serving an old deployment or the files were uploaded to the wrong folder.

## Smoke test

Run `node smoke-test.cjs` to verify that the waiting room renders, the Start button emits `start`, and a started game shows the Roll Dice control. Run `npm install` then `npm start` to run the complete server locally.

This game uses only the supplied Chapter 44 for its educational question content. The money is fictional game currency.
