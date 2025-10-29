# Prompt Builder
## Vibe Coding Thursday | Build Custom Prompts

> **Create powerful prompts using questions and options**

Learn to build custom prompts that get exactly what you want from AI.

---

## 🎯 The Prompt Formula

Every great prompt has these parts:

```
[WHO] + [WHAT] + [HOW] + [CONSTRAINTS] + [OUTPUT]
```

**Example:**
```
[WHO] As a React developer,
[WHAT] build a todo list app
[HOW] using functional components and hooks
[CONSTRAINTS] with TypeScript and no external libraries
[OUTPUT] and explain each part of the code
```

---

## 💡 Method 1: Questions-Based Prompting

**Strategy:** Let AI answer questions first, THEN generate code based on those answers.

### Template:
```
I want to build [TYPE OF APP].

Questions for you:
1. [TECHNICAL QUESTION]
2. [DESIGN QUESTION]
3. [FEATURE QUESTION]
4. [DATA QUESTION]
5. [CONSTRAINT QUESTION]

Please answer these questions first, then generate the code based on your recommendations.
```

### Example: Weather App
```
I want to build a weather app.

Questions for you:
1. What's the best free weather API to use?
2. Should I use React, Vue, or plain JavaScript?
3. Should I add a 5-day forecast or just current weather?
4. How should I handle cities that don't exist?
5. What's the simplest way to handle API keys securely?

Please answer these questions first, then generate the code based on your recommendations.
```

### Why This Works:
- ✅ AI considers all requirements before coding
- ✅ You learn WHY certain choices are made
- ✅ Can approve/reject decisions before implementation
- ✅ Reduces back-and-forth iterations

---

## 🎛️ Method 2: Options-Based Prompting

**Strategy:** Give AI multiple options to choose from, let it pick the best one.

### Template:
```
Build a [PROJECT TYPE] with these preferences:

Styling approach (pick best):
- Option A: [STYLE 1]
- Option B: [STYLE 2]
- Option C: [STYLE 3]

Complexity level:
- Simple: [DESCRIPTION]
- Medium: [DESCRIPTION]
- Advanced: [DESCRIPTION]

Technology stack (recommend one):
- Stack A: [TECH LIST]
- Stack B: [TECH LIST]
- Stack C: [TECH LIST]

Based on these options, build the app and explain your choices.
```

### Example: Portfolio Website
```
Build a portfolio website with these preferences:

Styling approach (pick best):
- Minimalist: Clean, lots of whitespace, muted colors
- Creative: Bold colors, animations, unique layouts
- Professional: Corporate feel, traditional layout

Complexity level:
- Simple: Single page, static content
- Medium: Multiple pages, contact form, blog section
- Advanced: CMS integration, admin panel, analytics

Technology stack (recommend one):
- Stack A: Plain HTML/CSS/JavaScript
- Stack B: React + Tailwind CSS
- Stack C: Next.js + Sanity CMS

Based on these options, build the app and explain your choices.
```

### Why This Works:
- ✅ Gives AI clear boundaries
- ✅ Ensures you're happy with approach
- ✅ AI can justify its recommendations
- ✅ Flexible - AI can suggest combinations

---

## 🔧 Method 3: Constraints-First Prompting

**Strategy:** Define what you CAN'T do, then let AI figure out the rest.

### Template:
```
Build [PROJECT] with these CONSTRAINTS:

Must have:
- [REQUIRED FEATURE 1]
- [REQUIRED FEATURE 2]
- [REQUIRED FEATURE 3]

Cannot use:
- [PROHIBITED TECH/APPROACH 1]
- [PROHIBITED TECH/APPROACH 2]

Must avoid:
- [ANTI-PATTERN 1]
- [ANTI-PATTERN 2]

Time limit: [DURATION]
Skill level: [BEGINNER/INTERMEDIATE/ADVANCED]

Now build the best solution within these constraints.
```

### Example: Timer App
```
Build a Pomodoro timer with these CONSTRAINTS:

Must have:
- 25-minute work timer
- 5-minute break timer
- Start/pause/reset buttons
- Audio notification when timer ends

Cannot use:
- No external libraries (vanilla JavaScript only)
- No backend/database
- No authentication

Must avoid:
- Complex state management
- Over-engineering the solution

Time limit: 1 hour
Skill level: Beginner

Now build the best solution within these constraints.
```

### Why This Works:
- ✅ Prevents scope creep
- ✅ Matches your skill level
- ✅ Fits time constraints
- ✅ Avoids prohibited approaches

---

## 🎨 Method 4: Example-Driven Prompting

**Strategy:** Show examples of what you like, let AI replicate the style.

### Template:
```
Build [PROJECT] with a style similar to:
- [EXAMPLE 1 URL/DESCRIPTION]: I like [SPECIFIC ASPECT]
- [EXAMPLE 2 URL/DESCRIPTION]: I like [SPECIFIC ASPECT]
- [EXAMPLE 3 URL/DESCRIPTION]: I like [SPECIFIC ASPECT]

Key elements to capture:
1. [DESIGN ELEMENT]
2. [INTERACTION PATTERN]
3. [VISUAL STYLE]

Build a [YOUR PROJECT] that captures these elements.
```

### Example: Dashboard
```
Build an analytics dashboard with a style similar to:
- Stripe Dashboard: I like the clean card-based layout and subtle shadows
- Linear App: I like the keyboard shortcuts and minimal interface
- Vercel Dashboard: I like the deployment status indicators and dark mode

Key elements to capture:
1. Card-based metric display
2. Dark mode by default
3. Subtle animations on hover
4. Real-time updating feel

Build a project analytics dashboard that captures these elements.
```

### Why This Works:
- ✅ Visual communication is clearer
- ✅ AI understands design patterns
- ✅ Captures "vibe" not just features
- ✅ Learns from successful examples

---

## 🧩 Method 5: Iterative Refinement

**Strategy:** Start broad, refine with follow-up prompts.

### Prompt Sequence:

**Prompt 1 (Broad):**
```
Build a [BASIC DESCRIPTION]
```

**Prompt 2 (Add Feature):**
```
Add [SPECIFIC FEATURE] to this app
```

**Prompt 3 (Improve):**
```
Make [SPECIFIC ELEMENT] more [ADJECTIVE]
```

**Prompt 4 (Polish):**
```
Add [POLISH ITEM] and ensure [QUALITY ASPECT]
```

### Example Sequence: Recipe Finder
```
**Prompt 1:**
Build a recipe search app

**Prompt 2:**
Add filtering by dietary restrictions (vegetarian, vegan, gluten-free)

**Prompt 3:**
Make the recipe cards more visually appealing with images and cook time icons

**Prompt 4:**
Add a save feature using localStorage and ensure mobile responsiveness
```

### Why This Works:
- ✅ Easy to start
- ✅ Incremental complexity
- ✅ Can change direction mid-build
- ✅ Matches creative process

---

## 📝 Prompt Templates by Project Type

### Simple App (Calculator, Timer, etc.)
```
Build a [APP NAME] with:
- [CORE FEATURE 1]
- [CORE FEATURE 2]
- [CORE FEATURE 3]

Use [FRAMEWORK] and [STYLING].
Make it [ADJECTIVE] and [ADJECTIVE].
```

### Data-Driven App (Weather, News, etc.)
```
Build a [APP NAME] that:
1. Fetches data from [API NAME]
2. Displays [DATA POINTS]
3. Has [INTERACTION FEATURES]

Handle errors gracefully and add loading states.
Use [FRAMEWORK] and [STYLING].
```

### Form-Based App (Survey, Contact, etc.)
```
Create a [FORM TYPE] with:

Fields:
- [FIELD 1]: [TYPE] (required/optional)
- [FIELD 2]: [TYPE] (required/optional)
- [FIELD 3]: [TYPE] (required/optional)

Validation:
- [RULE 1]
- [RULE 2]

Submit behavior:
- [WHAT HAPPENS ON SUBMIT]

Use [FRAMEWORK] and make it accessible.
```

### Dashboard App
```
Build a [DASHBOARD NAME] showing:

Metrics:
- [METRIC 1]: [VISUALIZATION TYPE]
- [METRIC 2]: [VISUALIZATION TYPE]
- [METRIC 3]: [VISUALIZATION TYPE]

Features:
- [FEATURE 1]
- [FEATURE 2]
- Date range selector

Use [CHARTING LIBRARY] and [FRAMEWORK].
```

---

## 🎓 Advanced Techniques

### Technique 1: Persona-Based Prompting
```
You are a [ROLE] building a [PROJECT] for [AUDIENCE].

As this role:
- Prioritize [PRIORITY 1]
- Ensure [QUALITY ASPECT]
- Follow [BEST PRACTICE]

Build [SPECIFIC REQUEST].
```

**Example:**
```
You are a senior React developer building a component library for junior developers.

As this role:
- Prioritize code readability and comments
- Ensure each component is well-documented
- Follow React best practices and hooks patterns

Build a set of form components (Input, Select, Checkbox) with examples.
```

---

### Technique 2: Requirement Elicitation
```
I want to build [VAGUE IDEA].

Before you start coding, ask me 5-7 clarifying questions about:
- Target users
- Core features
- Technical constraints
- Success criteria
- Timeline

Then provide a project plan based on my answers.
```

---

### Technique 3: Technical Specification
```
Create a technical specification for [PROJECT] including:

1. Architecture overview
2. Data models
3. API endpoints (if applicable)
4. Component hierarchy
5. Tech stack justification
6. Development phases

Then build the first phase.
```

---

## ✅ Prompt Checklist

**Before hitting Enter, check:**

- ☐ Is my goal clear?
- ☐ Did I specify technology preferences?
- ☐ Did I mention constraints (time, skill level)?
- ☐ Did I describe the desired output?
- ☐ Did I include examples or references?
- ☐ Am I being specific enough?

**Good prompt indicators:**
- ✅ Contains concrete details
- ✅ Specifies technologies
- ✅ Mentions target users
- ✅ Sets clear boundaries
- ✅ Defines success criteria

**Bad prompt indicators:**
- ❌ Too vague ("make it good")
- ❌ No technical details
- ❌ Assumes AI knows your preferences
- ❌ Multiple unrelated requests
- ❌ No context provided

---

## 🚀 Quick Start Prompt Builder

**Fill in the blanks:**

```
Build a [PROJECT TYPE] that [MAIN PURPOSE].

Technical details:
- Framework: [REACT/VUE/VANILLA/etc.]
- Styling: [TAILWIND/CSS/BOOTSTRAP/etc.]
- Data: [API/LOCAL STORAGE/NONE]

Must have features:
1. [FEATURE 1]
2. [FEATURE 2]
3. [FEATURE 3]

Nice to have:
- [OPTIONAL FEATURE 1]
- [OPTIONAL FEATURE 2]

Design style: [MINIMAL/COLORFUL/PROFESSIONAL/etc.]
Target users: [WHO WILL USE THIS]

Time to build: [DURATION]
My skill level: [BEGINNER/INTERMEDIATE/ADVANCED]

Additional notes: [ANY OTHER REQUIREMENTS]
```

---

## 💡 Pro Tips

### Do's:
- ✅ Start specific, you can always simplify
- ✅ Mention your skill level
- ✅ Ask AI to explain its choices
- ✅ Request comments in the code
- ✅ Specify mobile responsiveness if needed

### Don'ts:
- ❌ Don't assume AI knows your tech stack
- ❌ Don't request 10 features at once
- ❌ Don't be vague about requirements
- ❌ Don't forget to mention constraints
- ❌ Don't skip the "why" behind features

---

## 🔄 Iterating on Prompts

**If the output isn't what you wanted:**

**Bad response:**
```
That's not right. Try again.
```

**Good response:**
```
This is close, but I need [SPECIFIC CHANGE].
Specifically:
- [CHANGE 1]
- [CHANGE 2]
Can you update it?
```

**Even better:**
```
I like [WHAT YOU LIKED], but [WHAT NEEDS CHANGE].
Instead of [CURRENT BEHAVIOR], make it [DESIRED BEHAVIOR].
Keep [ELEMENTS TO PRESERVE].
```

---

## 📚 Example Conversations

### Example 1: Refining Through Questions
```
USER: Build a blog

AI: I need more information. What kind of blog? What features?

USER: Build a personal tech blog with:
- Markdown post support
- Code syntax highlighting
- Dark mode
- No backend (static)

AI: [Generates blog with requested features]

USER: Add a search feature that searches post titles and content

AI: [Adds search functionality]

USER: Make the search highlight matching text in yellow

AI: [Adds highlight feature]
```

### Example 2: Using Options
```
USER: Build a dashboard with these options:

Chart type (pick best for showing trends over time):
- Line chart
- Bar chart
- Area chart

Data source:
- Mock data for demo
- Real-time API
- CSV file upload

Features:
- Simple: Just show the chart
- Medium: Add filters and export
- Advanced: Add predictions and alerts

AI: I recommend:
- Area chart (best for trends with volume)
- Mock data (fastest to implement)
- Medium features (useful without complexity)
Proceeding with implementation...

[Generates dashboard]
```

---

## 🎯 Ready-to-Use Prompts by Experience

### Beginner:
```
I'm a beginner. Build a [SIMPLE APP] using [FRAMEWORK].
Include lots of comments explaining what each part does.
Use simple, easy-to-understand code.
```

### Intermediate:
```
Build a [PROJECT] using [FRAMEWORK] and [LIBRARIES].
Follow best practices for [SPECIFIC ASPECT].
Make it production-ready with error handling and loading states.
```

### Advanced:
```
Create a [COMPLEX PROJECT] with:
- [ARCHITECTURE PATTERN]
- [TESTING STRATEGY]
- [PERFORMANCE OPTIMIZATION]
Document the architectural decisions and trade-offs.
```

---

## 🆘 Troubleshooting Bad Prompts

### Problem: AI builds something totally different
**Fix:** Be more specific about features and tech stack

### Problem: Code is too complex
**Fix:** Add "keep it simple" and "I'm a beginner"

### Problem: Missing features you wanted
**Fix:** List features explicitly, don't assume AI will add them

### Problem: Wrong styling
**Fix:** Include design specifications and references

### Problem: No error handling
**Fix:** Add "include proper error handling and loading states"

---

## 🔗 Next Steps

**Ready to use your prompts?**

1. **Start building:** [QUICK-SETUP.md](QUICK-SETUP.md)
2. **Copy templates:** [PROMPT-CHEATSHEET.md](PROMPT-CHEATSHEET.md)
3. **Plan project:** [PLANNING-TEMPLATE.md](PLANNING-TEMPLATE.md)
4. **Get help:** [DEBUGGING-QUICKREF.md](DEBUGGING-QUICKREF.md)

**Want more examples?**
- [Prompts Library](../reference/prompts-library.md) - More templates
- [Tips & Tricks](../guides/TIPS-AND-TRICKS.md) - Advanced prompting
- [Spec-Kit Guide](../guides/SPEC-KIT-GUIDE.md) - Structured approach

---

*Vibe Coding Thursday | Milwaukee Tech Community*
*[Back to Event Day](README.md) | [Main Guide](../README.md)*
