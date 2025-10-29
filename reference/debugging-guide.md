# Reminders & Debugging Guidelines

Vibe‑coding often involves auto‑generated code, so it’s important to maintain good debugging practices.  The Lossless “Maintain Consistent Debugging Conventions” article describes a helpful debugging system for markdown and AST processing.  While the original system is built for static‑site generation, the principles apply more broadly to AI‑generated code.  Below is a distilled version of the key points.

## Enable debugging via environment variables

* `DEBUG_MARKDOWN=true` – turn on basic markdown debugging.
* `DEBUG_MARKDOWN_VERBOSE=true` – enable verbose output with full AST dumps.
* `DEBUG_AST=true` – enable file‑based AST output.
* `PUBLIC_DEBUG_AST=true` – client‑side flag for debugging in the browser.

These variables can be placed in your `.env` file or set in the shell before running your application.  You can also activate debugging in the browser via URL parameters such as `?debug-markdown`, `?debug-markdown-verbose` and `?debug-ast`.

## Progressive debugging levels

The debugging system supports multiple levels of verbosity:

1. **Basic logging** – log function entry/exit and key events.
2. **Transformation tracking** – log how your code transforms through each plugin stage.
3. **Full AST dumps** – capture entire abstract syntax trees for deep inspection.
4. **File‑based output** – write debug files to disk for persistent analysis.

Start with basic logging and increase the level only when needed.  Too much debugging information can overwhelm both you and the AI.

## Plugin instrumentation

If your workflow uses plugins (for example remark/rehype plugins in a markdown pipeline), instrument them with `startPlugin` and `endPlugin` hooks to mark when each plugin begins and ends.  Log transformations inside each plugin so you can trace how the input changes step by step.

## Organising debug output

Debug files are easier to navigate when they are stored systematically.  The article recommends creating date‑based directories (e.g. `YYYY‑MM‑DD_01`) and numbering files to reflect the pipeline stages.  Use JSON format for AST dumps because it is easy to inspect and diff.

## Browser vs. static‑site contexts

Ensure your debugging system can handle both client‑side and server‑side contexts.  For example, in a static‑site generator you should guard against `window` or `document` being undefined.  Similarly, if you run AI‑generated code in Node.js without a browser environment, avoid browser‑specific APIs.

By following these reminders you can keep your vibe‑coding sessions productive and maintainable.  Remember to **share your process** during the event—the community learns when you work in public.