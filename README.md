# Build your own Substack website

**Give this guide to Codex or Claude Code and have it help you create a website for your own publication. You don't need to know how to code.**

You choose the look, the content, and the details. The agent asks questions, builds a preview, makes your revisions, and helps you put it online when you're ready.

[See Anna's Le Index website for inspiration](https://le-index-substack.vercel.app/) · [Read Le Index](https://annanoellerinke.substack.com/)

This repository is a guide for creating a new website. Your finished site will have its own files, branding, article links, and deployment.

## 1. Open Codex or Claude Code

Start a new task. If the app asks for a project folder, create an empty folder called **My Substack Website** and select it.

Use a coding-agent session that can create files, run the site, and access the web. If you need help getting set up, ask the agent to walk you through it. Official setup help: [Codex projects](https://learn.chatgpt.com/docs/projects) and [Claude Code quickstart](https://code.claude.com/docs/en/quickstart).

## 2. Give it this guide

Copy the GitHub link:

```text
https://github.com/annanoellerinke/le-index-substack
```

If the agent cannot open the link, copy the contents of this README into the chat or download it and attach it. You can read this public guide without creating a GitHub account.

## 3. Copy and paste this prompt

```text
Read this guide first:
https://github.com/annanoellerinke/le-index-substack

Help me build my own Substack website using this guide.

Ask me for my exact personal links and design preferences before building.
Let me choose the layout, colors, typography, images, and how the articles are displayed.
Use my own publication, branding, and articles.

Once we're aligned, make a short plan and then build the website.
Show me a working preview and check how it looks on mobile.
Let me give feedback before publishing. Do not deploy until I approve it.
```

Have your Substack homepage link ready. You can also share your logo, photos, fonts, favorite websites, or screenshots of designs you like. It's okay to say, “I don't know yet—show me a few options.”

## 4. Answer the questions and make it yours

Give feedback in plain language:

- “Make the font bigger.”
- “Use a white background and black type.”
- “Show my articles as magazine covers.”
- “Use these cover images with the titles already on them.”
- “Keep the original illustration style.”
- “Put my newest articles first, reading left to right and then down.”
- “Put an article in every window, with no skipped article windows.”
- “Use five columns on desktop and three on mobile.”
- “Let people filter by my categories.”
- “Make the images larger on mobile.”
- “Show me what it looks like before you publish.”

Keep going until you like it. A grid, magazine, bookshelf, illustrated building, or another idea can all be starting points. Anna's building design is an example; your choices set the direction.

## 5. Ask to put it online

When you've approved the preview, copy and paste:

```text
I approve this version. Publish it on Vercel in my account.
Walk me through any sign-in steps and help me choose an available project name.
Check the live site on desktop and mobile, including the article links and filters.
Give me the public URL and explain how to update it when I publish new articles.
```

You may need to sign in to Vercel yourself. The agent's ability to publish depends on the tools and access available in your session. If it cannot deploy directly, it should prepare the finished project and guide you through publishing it.

Want your own code repository too? Say:

```text
Create a GitHub repository in my account for my finished website.
Ask whether I want it public or private, include a README, and explain how to update it.
```

---

## Instructions for the coding agent

When a user gives you this guide and asks for their own Substack website, carry the project through discovery, implementation, preview, revision, and approved publication. Create the user's website in their chosen project folder. Use this repository as the guide, not as a preconfigured application to deploy.

### A. Ask questions before building

Start with a few easy questions, then ask only the follow-ups needed. Confirm:

1. **Their publication:** exact Substack homepage URL, publication name, author name, and the personal links they want included. Verify About and Subscribe destinations from their publication; ask about anything ambiguous.
2. **Their visual direction:** layout, colors, typography, reference images or websites, logo, and any photos they want to use. If they are unsure, offer two or three concrete directions.
3. **Their article display:** all published articles or a selection; newest first or another order; category filters; the exact cover-image version they prefer; and separate desktop/mobile column counts. For illustrated layouts, ask whether every article window should be filled or some should remain decorative.
4. **Their extras:** an introduction, portrait, genuine testimonial, subscription link, animations, or other interactions. Ask for the actual text and attribution where needed.
5. **Their launch:** where the project should live and whether they already have a site that must be preserved. Choose the Vercel account and project name with them when publication is relevant.

Use the new user's information throughout. The Le Index name, Anna's portrait, subscriber quote, categories, fonts, article archive, and building artwork are not defaults for another person's website.

After the initial answers, summarize the agreed design and a short implementation plan. Then build within that agreed scope.

### B. Gather their article content

- Start with the user's public Substack publication and archive. Collect actual titles, publication dates, canonical article URLs, categories or tags, and cover images.
- Check completeness. A feed or first archive page may show only recent posts. Follow available pagination or use an owner-provided export when necessary, and report how many articles were imported.
- If a source cannot be accessed, explain what is missing and ask for the relevant links or files. If the owner needs to sign in to retrieve cover art, let them use their own browser/account.
- Use the cover variant the user chose. If they want the text-over-photo cover, use that composed image consistently. Preserve its text and aspect ratio; don't replace it with a plain photo or add a second title over it.
- Link readers to the original Substack article. Treat the new website as a front door to the publication unless the user requests a different content model.
- Keep an editable article data file and a repeatable update process. Ask whether they prefer manual updates or automatic syncing. Only call syncing automatic if it has actually been implemented and checked.

### C. Build their approved design

Use a maintainable implementation suited to the design. A static site is a good fit for an article collection; add more infrastructure only when the requested features need it.

Use the user's branding and approved artwork. For image-based layouts, preserve the intended illustration style and fit article covers into the agreed spaces. Keep layout, crop, image size, and background changes separate enough that feedback can be applied precisely.

For filled-window layouts, assign one unique article to every visible article window, in reading order from left to right and then down. Use the agreed column count separately on desktop and mobile. Handle a short final row by showing only the remaining article windows, without duplicating posts or leaving accidental empty slots. Preserve the illustration’s proportions when cropping rows. Decorative neighboring buildings and entrance artwork are separate from the article collection unless the user asks otherwise.

Build responsive behavior from the beginning. Give article links descriptive accessible names, make controls usable by keyboard, and respect reduced-motion preferences for animation. Confirm how categories should appear so readers can find them without guessing.

Use a normal link to the Substack destination underneath optional navigation animation. If an animation is unavailable or reduced motion is preferred, the link should still work.

### D. Show a working preview and revise it

Run the site and show the user a preview they can open. Include a screenshot when your tools support it. Check at least one desktop and one phone-sized layout.

Verify:

- The publication name, logo, personal links, and subscription destination belong to the user.
- Article covers load, match their titles, and open the correct posts.
- The article order is correct and imported records are not duplicated.
- Every requested article slot is populated, and desktop/mobile column counts match the design, including filtered results and short final rows.
- Category controls show the right articles and accurate counts.
- Text is readable, controls are usable, and the phone layout does not overflow horizontally.
- Any interactive illustration or animation reaches the intended destination and behaves with reduced motion.
- No sample identity, placeholder links, or unresolved content gaps remain without the user's knowledge.

Apply the user's feedback and show the updated preview. Be explicit about what you checked and any limitation you could not verify. Wait for the user's approval of the design before deployment.

### E. Publish after approval

Once the user approves publication, use their Vercel account and the intended project. Reuse an existing authorized sign-in when available; otherwise guide them through signing in. Keep sign-in credentials out of chat, project files, and GitHub.

Deploy the approved version and verify the public URL, assets, article navigation, category filters, and mobile layout on the live site. Distinguish a local preview, a protected preview, and a publicly accessible production site. Do not call a site live until the production URL works.

If the user also wants a GitHub repository for their generated website, create it in their account with their requested visibility. Include the working source, required assets, and instructions for previewing, deploying, and adding articles. Keep local environment files and credentials out of it.

### F. Hand over something they can maintain

Give the user the public website URL, the location of the project files, and a short explanation of how to add future articles. State whether updating is manual or automatic, where the article data lives, and what needs to be rerun or republished after a change.

The goal is a working, personal website the user understands how to update—not just a plan or a mockup.
