# Reminders & Debugging Guidelines

Vibe‑coding often involves auto‑generated code, so it’s important to maintain good debugging practices.  The Lossless “Maintain Consistent Debugging Conventions” article describes a helpful debugging system for markdown and AST processing【118962704377781†L169-L176】.  While the original system is built for static‑site generation, the principles apply more broadly to AI‑generated code.  Below is a distilled version of the key points.

## Enable debugging via environment variables

* `DEBUG_MARKDOWN=true` – turn on basic markdown debugging【118962704377781†L169-L176】.
* `DEBUG_MARKDOWN_VERBOSE=true` – enable verbose output with full AST dumps【118962704377781†L169-L176】.
* `DEBUG_AST=true` – enable file‑based AST output【118962704377781†L169-L176】.
* `PUBLIC_DEBUG_AST=true` – client‑side flag for debugging in the browser【118962704377781†L169-L176】.

These variables can be placed in your `.env` file or set in the shell before running your application.  You can also activate debugging in the browser via URL parameters such as `?debug-markdown`, `?debug-markdown-verbose` and `?debug-ast`【118962704377781†L178-L185】.

## Progressive debugging levels

The debugging system supports multiple levels of verbosity【118962704377781†L188-L196】:

1. **Basic logging** – log function entry/exit and key events.
2. **Transformation tracking** – log how your code transforms through each plugin stage.
3. **Full AST dumps** – capture entire abstract syntax trees for deep inspection.
4. **File‑based output** – write debug files to disk for persistent analysis【118962704377781†L188-L198】.

Start with basic logging and increase the level only when needed.  Too much debugging information can overwhelm both you and the AI.

## Plugin instrumentation

If your workflow uses plugins (for example remark/rehype plugins in a markdown pipeline), instrument them with `startPlugin` and `endPlugin` hooks to mark when each plugin begins and ends【118962704377781†L198-L203】.  Log transformations inside each plugin so you can trace how the input changes step by step.

## Organising debug output

Debug files are easier to navigate when they are stored systematically.  The article recommends creating date‑based directories (e.g. `YYYY‑MM‑DD_01`) and numbering files to reflect the pipeline stages【118962704377781†L204-L210】.  Use JSON format for AST dumps because it is easy to inspect and diff【118962704377781†L204-L211】.

## Browser vs. static‑site contexts

Ensure your debugging system can handle both client‑side and server‑side contexts.  For example, in a static‑site generator you should guard against `window` or `document` being undefined【118962704377781†L212-L217】.  Similarly, if you run AI‑generated code in Node.js without a browser environment, avoid browser‑specific APIs.

By following these reminders you can keep your vibe‑coding sessions productive and maintainable.  Remember to **share your process** during the event—the community learns when you work in public【30198705797314†screenshot】.