# Debugging Quick Reference
## Vibe Coding Thursday | Fix Errors Fast

> **Common problems and instant solutions**

Hit an error? Find the fix here in under 30 seconds.

---

## 🚨 Most Common Errors

### Error: "Syntax Error" or "Unexpected Token"

**What it means:** Missing parenthesis, bracket, or quote

**Quick fix:**
1. Check for matching pairs: `( )`, `[ ]`, `{ }`, `" "`
2. Look at the line number in the error
3. Ask AI: "Fix this syntax error: [paste error message]"

**Example:**
```javascript
// ❌ Wrong
console.log("Hello;

// ✅ Right
console.log("Hello");
```

---

### Error: "Cannot read property of undefined"

**What it means:** Trying to use data that doesn't exist yet

**Quick fix:**
1. Check if data is loading
2. Add optional chaining: `data?.property`
3. Add a check: `if (data) { ... }`

**Example:**
```javascript
// ❌ Wrong
const name = user.name;

// ✅ Right
const name = user?.name || "Guest";
```

---

### Error: "Failed to fetch" or "Network Error"

**What it means:** API call isn't working

**Quick fix:**
1. Check your internet connection
2. Verify API key is correct
3. Check if API URL is right
4. Look for CORS issues

**Ask AI:**
```
My fetch request is failing with this error: [ERROR].
Here's my code: [PASTE CODE]
How do I fix it?
```

---

### Error: "Module not found" or "Cannot find module"

**What it means:** Missing dependency or wrong import path

**Quick fix:**
```bash
# Install the missing package
npm install [package-name]

# Or if using different tool:
yarn add [package-name]
```

**Check import:**
```javascript
// ❌ Wrong
import Button from './components/Button';

// ✅ Right (if file is Button.jsx)
import Button from './components/Button.jsx';
```

---

### Error: Nothing appears on screen

**What it means:** Component not rendering or hidden

**Quick fix checklist:**
- ☐ Is the component imported?
- ☐ Is it used in the JSX?
- ☐ Check CSS (is it `display: none`?)
- ☐ Check console for other errors

**Ask AI:**
```
My component isn't showing up on the screen.
Here's the code: [PASTE CODE]
```

---

## 🔧 Quick Debugging Steps

### The 30-Second Debug:
1. **Read the error message** (it often tells you exactly what's wrong)
2. **Check line number** mentioned in error
3. **Copy error to AI** and ask for fix
4. **Apply the fix**
5. **Test again**

### The 2-Minute Debug:
1. Read error carefully
2. Check browser console for details (F12)
3. Look for typos in variable names
4. Verify all imports are correct
5. Check if all dependencies are installed
6. Ask AI with full error and code

### The 5-Minute Debug:
1. Console.log everything to see what's happening
2. Comment out code until error disappears
3. Isolate the problem area
4. Search error message online
5. Ask organizer or pair up with someone

---

## 🌐 Browser-Specific Fixes

### Page is blank / white screen

**Check:**
1. Open browser console (F12 or Cmd+Option+J)
2. Look for red error messages
3. Common causes:
   - JavaScript error preventing render
   - Wrong file path
   - Missing HTML element with id

**Quick fix:**
```
Ask AI: "My page is blank. Console shows: [ERROR]"
```

---

### Styles not applying

**Check:**
1. Is CSS file imported?
2. Are class names spelled correctly?
3. Is there a typo in the CSS?
4. Check browser dev tools "Elements" tab

**Quick fix:**
```javascript
// Replit: Make sure style.css is linked in index.html
<link rel="stylesheet" href="style.css">

// React: Import the CSS
import './App.css';
```

---

### Button clicks don't work

**Check:**
1. Is onClick handler attached?
2. Is function defined?
3. Check console for errors

**Example fix:**
```javascript
// ❌ Wrong
<button onClick="handleClick()">Click</button>

// ✅ Right (React)
<button onClick={handleClick}>Click</button>

// ✅ Right (Vanilla JS)
<button onclick="handleClick()">Click</button>
```

---

## 🛠️ Tool-Specific Issues

### Replit Problems

**Issue: "Out of memory" or app is slow**
- **Fix:** Click "Stop" then "Run" again to restart

**Issue: Changes not showing**
- **Fix:** Hard refresh (Ctrl+Shift+R or Cmd+Shift+R)

**Issue: Ghostwriter not working**
- **Fix:** Check if you're in free tier limit, try rephrasing prompt

**Issue: Can't install package**
- **Fix:** Use the Packages tool in sidebar, not terminal

---

### Lovable Problems

**Issue: Can't deploy**
- **Fix:** Check if you're at free project limit (3 projects)

**Issue: Database not working**
- **Fix:** Verify Supabase connection in settings

**Issue: Design changes not applying**
- **Fix:** Click "Regenerate" instead of editing directly

---

### v0 Problems

**Issue: Code doesn't work when copied**
- **Fix:** Copy the entire component, including imports

**Issue: Styles look different**
- **Fix:** Make sure Tailwind CSS is installed in your project

**Issue: Can't use the component**
- **Fix:** v0 generates components, not full apps - you need to integrate them

---

## 💬 How to Ask AI for Help

### ❌ Bad Request:
```
It's not working. Fix it.
```

### ✅ Good Request:
```
I'm getting this error: [EXACT ERROR MESSAGE]

Here's my code:
[PASTE CODE]

What I'm trying to do: [DESCRIBE GOAL]

What's happening instead: [DESCRIBE PROBLEM]

Can you help me fix this?
```

### ⭐ Best Request:
```
Error: "Cannot read property 'map' of undefined"

Code:
[PASTE CODE WITH LINE NUMBERS]

Context:
- I'm fetching data from an API
- The data should be an array of posts
- This worked yesterday but broke today

What I've tried:
- Added console.log (data is undefined on first render)
- Checked API (API returns data correctly)

How do I fix this?
```

---

## 🔍 Console Commands (Debugging Tools)

### Open Browser Console:
- **Chrome/Edge:** F12 or Ctrl+Shift+J (Cmd+Option+J on Mac)
- **Firefox:** F12 or Ctrl+Shift+K
- **Safari:** Cmd+Option+C

### Useful Console Commands:
```javascript
// Print variable to see its value
console.log(variableName);

// Print with label
console.log("User data:", user);

// Print type of variable
console.log(typeof variableName);

// Print all properties of object
console.dir(objectName);
```

---

## 🎯 Error Message Decoder

| Error Message | Probably Means | Quick Fix |
|---------------|----------------|-----------|
| "undefined is not a function" | Typo in function name or not imported | Check spelling and imports |
| "Unexpected token" | Missing bracket or quote | Check matching pairs |
| "Cannot read property" | Using data that doesn't exist | Add safety check |
| "CORS error" | API blocking your request | Use proxy or different API |
| "404 Not Found" | File or URL doesn't exist | Check path/URL |
| "401 Unauthorized" | Wrong API key or not logged in | Verify API key |
| "Maximum call stack exceeded" | Infinite loop | Find recursive function |

---

## 📋 Debugging Checklist

**Before asking for help:**

- ☐ Read the error message completely
- ☐ Checked browser console (F12)
- ☐ Tried refreshing the page
- ☐ Checked for typos
- ☐ Verified file paths are correct
- ☐ Confirmed packages are installed
- ☐ Tried console.log to see what's happening
- ☐ Copied exact error message

**When asking for help:**

- ☐ Describe what you're trying to do
- ☐ Explain what's happening instead
- ☐ Provide exact error message
- ☐ Share relevant code
- ☐ Mention what you already tried

---

## 🚑 Emergency Fixes

### "Everything broke and I don't know why"

**Nuclear option (saves you every time):**
```bash
# If using Git (recommended!)
git status
git diff  # see what changed
git checkout -- .  # DANGER: reverts all changes!

# Or restore from last working commit
git log
git checkout [COMMIT_HASH]
```

**If not using Git:**
- Use your tool's history/undo feature
- Replit: Click "History" button
- VS Code: Ctrl+Z repeatedly

---

### "API key not working"

**Check:**
```javascript
// Is it actually loaded?
console.log("API Key:", process.env.REACT_APP_API_KEY);

// Did you restart after adding .env file?
// Many tools require restart to load env variables
```

**Common mistakes:**
- Typo in variable name
- Forgot to add to .env file
- Forgot to restart dev server
- Using wrong variable prefix (REACT_APP_, VITE_, etc.)

---

### "Can't commit to Git"

```bash
# See what's wrong
git status

# Common fix: stage files first
git add .
git commit -m "Your message"

# If commit fails due to large files
git rm --cached [large-file]
```

---

## 🆘 Still Stuck?

### At the Event:
1. **Ask an organizer** - that's what they're there for!
2. **Pair up** - two heads are better than one
3. **Show your screen** - visual debugging is faster
4. **Take a break** - fresh eyes see errors

### Outside the Event:
1. **Google the exact error** - someone else had it
2. **Ask on Discord/Slack** - community channels
3. **Check tool's documentation** - might be a known issue
4. **Start fresh** - sometimes easier to rebuild

---

## 💡 Prevention Tips

### While Coding:
- ✅ Save frequently
- ✅ Test small changes immediately
- ✅ Commit working code to Git
- ✅ Use console.log liberally
- ✅ Read error messages carefully

### Before Building:
- ✅ Plan your features first
- ✅ Start with simplest version
- ✅ Test each feature before adding next
- ✅ Keep prompts simple and clear

---

## 🎓 Learn from Errors

**Good mindset:**
- Errors are learning opportunities
- Everyone gets errors (even experts!)
- Each error teaches you something
- Debugging makes you better

**Bad mindset:**
- "I'm bad at coding"
- "This should just work"
- "AI should do everything perfectly"
- "I'll never figure this out"

**Remember:** Professional developers spend 50% of their time debugging. It's a normal part of coding!

---

## 🔗 More Help

**Comprehensive guides:**
- [Debugging Guide](../reference/debugging-guide.md) - Deep dive
- [Tips & Tricks](../guides/TIPS-AND-TRICKS.md) - Advanced debugging

**Quick references:**
- [Prompt Cheatsheet](PROMPT-CHEATSHEET.md) - Better prompts = fewer errors
- [Tool Picker](TOOL-PICKER.md) - Maybe try different tool?

**Get help:**
- Ask event organizers
- Check tool documentation
- Community Discord/Slack

---

*Vibe Coding Thursday | Milwaukee Tech Community*
*[Back to Event Day](README.md) | [Main Guide](../README.md)*
