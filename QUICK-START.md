# Quick Start Guide
## Build Your First App in 15 Minutes

> **Vibe Coding Thursday | Milwaukee Tech Community**

No installation. No setup. Just describe what you want and start building.

---

## Choose Your Starting Point

### Option 1: Super Fast (5 minutes)
**Best for:** Complete beginners, just want to see it work

1. Go to [Replit](https://replit.com)
2. Sign up (free)
3. Click "Create Repl"
4. Select "Generate with AI"
5. Type: "Build a simple todo list app"
6. Watch it generate!
7. Click "Run" to see your app

**Done!** You just created an app with AI.

---

### Option 2: Better Control (15 minutes)
**Best for:** Want to understand the process better

#### Step 1: Choose a Tool (1 minute)

Pick ONE of these:
- **[Lovable](https://lovable.dev)** - Best designs, fastest
- **[v0 by Vercel](https://v0.dev)** - Shows you how it works
- **[Replit](https://replit.com)** - Most beginner-friendly

#### Step 2: Get API Key (3 minutes)

1. Go to [OpenRouter](https://openrouter.ai/)
2. Sign up (free tier available)
3. Click "Keys" → "Create Key"
4. Copy the key (starts with `sk-or-...`)
5. **Save it somewhere safe!**

#### Step 3: Connect to Tool (2 minutes)

**For Replit:**
1. Open your Repl
2. Click "Secrets" (lock icon)
3. Add: `OPENROUTER_API_KEY` = your key

**For v0:**
1. Settings → API Keys
2. Paste your OpenRouter key

**For Lovable:**
1. Account → API Configuration
2. Add OpenRouter key

#### Step 4: Your First Prompt (5 minutes)

Try this prompt:

```
Build a simple note-taking app with these features:
- Text input field for new notes
- Add button to save notes
- List of all notes below
- Delete button for each note
- Use clean, modern styling
- Store notes in browser localStorage so they persist

Use React and Tailwind CSS.
```

#### Step 5: Review & Run (4 minutes)

1. **Review the code** - Read through what AI generated
2. **Ask questions** - "Explain how localStorage works here"
3. **Make changes** - "Make the buttons blue instead of gray"
4. **Run it** - Click Run/Preview
5. **Test it** - Add notes, delete them, refresh page

**Congratulations!** You just built a functional app.

---

### Option 3: Spec-Kit Power User (30 minutes)
**Best for:** Want to learn professional workflow

#### Prerequisites
- Git installed
- Terminal/command line access
- Basic comfort with commands

#### Step 1: Install Spec-Kit (5 minutes)

```bash
# Install uv package manager
curl -LsSf https://astral.sh/uv/install.sh | sh

# Install spec-kit
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# Verify
specify check
```

#### Step 2: Initialize Project (2 minutes)

```bash
# Create project
specify init my-first-app --ai claude

# Navigate to it
cd my-first-app
```

#### Step 3: Define Your App (8 minutes)

Open your AI tool (Claude Code, Cursor, etc.):

```
/speckit.constitution
```

Tell AI:
```
Project: Simple recipe manager
Tech: React + TypeScript + LocalStorage
Principles:
- Simple and fast
- Mobile-first design
- Offline capability
```

Then:
```
/speckit.specify
```

Tell AI:
```
User Stories:
1. Add recipe with name and ingredients
2. View list of all recipes
3. Search recipes by name
4. Delete recipes
```

#### Step 4: Let AI Plan (5 minutes)

```
/speckit.plan
```

AI will create complete technical plan.

#### Step 5: Build It (10 minutes)

```
/speckit.tasks
```

Review tasks, then:

```
/speckit.implement TASK-001
```

Continue for each task. AI builds systematically!

**You're now a spec-driven developer!**

---

## What to Do Next

### Beginner Path
1. **Build 3 simple apps** using browser tools
   - Todo list
   - Calculator
   - Contact form

2. **Read the guides**
   - [Beginner Learning Path](learning-paths/beginner/README.md)
   - [Prompt Engineering Tips](guides/TIPS-AND-TRICKS.md#prompt-engineering-mastery)

3. **Join the community**
   - [Milwaukee Tech Meetup](https://www.meetup.com/milwaukee-tech/)
   - Share on #VibeCodingThursday

### Intermediate Path
1. **Learn Spec-Kit**
   - [Complete Spec-Kit Guide](guides/SPEC-KIT-GUIDE.md)
   - [Todo App Example](examples/spec-kit-todo-example.md)

2. **Build a real project**
   - Blog platform
   - Inventory tracker
   - Team dashboard

3. **Practice workflows**
   - Constitution writing
   - Specification creation
   - Task breakdown

### Advanced Path
1. **Master CLI tools**
   - [Claude Code Guide](learning-paths/advanced/README.md#claude-code)
   - [Aider Workflow](learning-paths/advanced/README.md#aider)

2. **Automate everything**
   - Git workflows
   - Testing pipelines
   - Deployment automation

3. **Contribute**
   - Add examples to this guide
   - Help others learn
   - Share advanced techniques

---

## Common First-Time Questions

**Q: Do I need to know how to code?**
A: No! Vibe coding is designed for anyone. You describe what you want, AI writes the code.

**Q: Will this actually work for real apps?**
A: Yes! People build production apps this way. Start simple, grow from there.

**Q: How much does it cost?**
A: Browser tools have free tiers. OpenRouter charges per AI usage (usually pennies per project).

**Q: What if the AI makes mistakes?**
A: Tell it! "This button isn't working, fix it" or "Change the color to blue."

**Q: Can I see the code?**
A: Absolutely! All tools show you the code. You can learn by reading it.

**Q: Do I own what I build?**
A: Yes! AI-generated code is yours to keep and modify.

---

## Helpful Prompts for First Projects

### Simple Todo List
```
Create a todo list app where I can:
- Add new todos with text input
- Mark todos as complete with checkboxes
- Delete todos with a delete button
- See all todos in a list

Use modern styling and make it responsive for mobile.
Store todos in localStorage so they survive page refresh.
```

### Calculator
```
Build a calculator app with:
- Number buttons 0-9
- Operation buttons (+, -, ×, ÷)
- Equals button to show result
- Clear button to reset
- Display showing current input and result

Make it look like a real calculator with a clean design.
```

### Contact Form
```
Create a contact form with:
- Fields: Name, Email, Message
- Validation: all fields required, email must be valid format
- Submit button
- Success message after submission
- Error messages for invalid inputs

Style it professionally and make it mobile-responsive.
```

### Weather App
```
Build a weather app that:
- Takes city name as input
- Shows current temperature and conditions
- Displays a 5-day forecast
- Uses OpenWeatherMap API
- Has nice weather-themed design

Include loading states and error handling for invalid cities.
```

---

## Troubleshooting

**AI isn't generating code:**
- Check your API key is entered correctly
- Verify you have credits in OpenRouter
- Try rephrasing your prompt more specifically

**Code has errors:**
- Ask AI: "Fix the error on line 23"
- Try: "Debug this and explain what was wrong"
- Start over if completely stuck - it's faster!

**App doesn't look good:**
- Add: "Make this look modern and professional"
- Try: "Use Tailwind CSS for styling"
- Ask: "Make it responsive for mobile devices"

**Don't understand the code:**
- Ask: "Explain this code line by line"
- Try: "What does this function do?"
- Request: "Add comments explaining each part"

---

## Next Steps

### Immediate (Today)
1. ✅ Build your first app (15 min)
2. ✅ Test it thoroughly
3. ✅ Share with a friend
4. ✅ Celebrate! 🎉

### This Week
1. Build 2-3 more simple apps
2. Read [Beginner Guide](learning-paths/beginner/README.md)
3. Learn [prompt engineering basics](guides/TIPS-AND-TRICKS.md#prompt-engineering-mastery)
4. Join Milwaukee Tech community

### This Month
1. Progress to [Intermediate path](learning-paths/intermediate/README.md)
2. Try Spec-Kit workflow
3. Build something useful for yourself
4. Help another beginner

---

## Resources at Your Fingertips

**Complete Documentation:**
- [Guide Index](GUIDE-INDEX.md) - Everything organized
- [Complete Resource Guide](guides/COMPLETE-RESOURCE-GUIDE.md) - Deep dive into all topics
- [Tips & Tricks](guides/TIPS-AND-TRICKS.md) - 100+ practical strategies

**Learning Paths:**
- [Beginner](learning-paths/beginner/README.md) - Web-based tools
- [Intermediate](learning-paths/intermediate/README.md) - Spec-kit workflow
- [Advanced](learning-paths/advanced/README.md) - CLI mastery

**Get Help:**
- [Debugging Guide](reference/debugging-guide.md)
- [Milwaukee Tech Community](https://mketech.org)
- [GitHub Issues](https://github.com/crafty-arl/VibeCodingThursday/issues)

---

## Join the Community

**Vibe Coding Thursday**
- **When:** Every Thursday
- **Where:** Milwaukee Tech Hub
- **What:** Build together, learn together, share projects
- **Link:** [meetup.com/milwaukee-tech](https://www.meetup.com/milwaukee-tech/)

**Online:**
- Hashtag: #VibeCodingThursday
- GitHub: [crafty-arl/VibeCodingThursday](https://github.com/crafty-arl/VibeCodingThursday)
- Reddit: [r/milwaukee](https://reddit.com/r/milwaukee)

---

**You've got this! Start building! 🚀**

---

*Vibe Coding Thursday | Milwaukee Tech Community*
*Updated: October 2025 | [Main Guide](README.md) | [Full Index](GUIDE-INDEX.md)*
