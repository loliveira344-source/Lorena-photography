THE BOOK — EDITORIAL PHOTOGRAPHY PREVIEW
==========================================

What this is
   A separate page, /the-book/, previewing photography for the whole
   book — Primeira Parte (one flowing set of photos, not broken out by
   chapter, since you don't have images for every chapter yet), then
   Segunda Parte — Nômade Digital (México — already split into its
   three sections, Colômbia, Peru, Argentina, Brasil, filled in as
   each is finalized). It's built to sit beside your existing
   portfolio without touching it:

     - index.html (your portfolio) — completely untouched.
     - the-book/index.html — the new preview page, its own file.
     - the-book/photos/ — its own image folder, separate from the
       portfolio's images/ folder, so nothing gets mixed up.

   It is NOT linked from your site's main nav (Work / About / Contact).
   The only way anyone finds it is the direct URL, which is exactly
   what you want for something you're sharing with editors pre-launch:

     https://lorenaoliveira.com/the-book/

   (Note the trailing slash — that's what makes GitHub Pages serve
   the folder's index.html automatically.)

1. ADD PHOTOS
   Open the-book/index.html and find "const CHAPTERS = [" near the
   top of the <script> block. There are two shapes of entry:
     - Flat chapters (Primeira Parte, Colômbia, Peru, Argentina,
       Brasil) have their own `photos` array right on the chapter.
     - México is split into three `subsections` — Tudo Parece
       Diferente Agora, Aprendendo a Aceitar a Beleza do Imperfeito,
       and A Possibilidade de Viver Sem Amarras — each with its own
       `photos` array, so its Mexico City / Sayulita / Chiapas
       chapters of the trip stay visually separate.
   Either way, adding a photo is the same:
     - Drop the file into the-book/photos/
     - Add a line inside the right `photos` array:
         { file: "yourfile.jpg", w: 1600, h: 1066, caption: "..." }
       (w/h are the image's real pixel width/height — check via
       Preview.app's Tools > Show Inspector, or Get Info in Finder.)
   For Primeira Parte specifically: just keep adding photos to its one
   `photos` array in whatever order you want them to read — there's no
   need to sort them by chapter unless you want to.

   The `caption` is the description that appears directly under that
   photo on the page — this is the "so my editor and future readers
   can follow along" text. Write whatever you want there; leave it as
   "" if you're not ready to write it yet and the photo will still
   show, just with "No description added yet" under it as a reminder.
   Note this isn't a live typing box a visitor fills in — it's text
   you write into this file, the same way you already add photos;
   a page that saved what visitors typed would need a real backend,
   which a plain GitHub Pages site doesn't have.

2. ADD A NEW CHAPTER
   Copy one of the existing { part, slug, title, titleEN, note, photos }
   blocks and fill it in. It'll automatically get its own
   table-of-contents entry (grouped under whichever `part` you give
   it) and its own section on the page, in whatever order you place
   it in the array. If a chapter needs its own subsections the way
   México does, copy México's shape instead ({ part, slug, title,
   titleEN, note, subsections: [...] }).

3. PUBLISH IT
   This site doesn't have git set up in this exact folder, so publish
   the-book/ the same way you already publish updates to the rest of
   the site (GitHub Desktop, web upload, etc.) — just make sure the
   the-book/ folder (index.html + photos/) gets pushed alongside your
   next update. Once it's live, share the URL above with your editors
   directly — no need to announce it anywhere on the public site.

DESIGN NOTES
   Same visual language as the main portfolio (same fonts, same
   black-and-white palette, same click-to-preview lightbox) so it
   reads as one continuous body of work rather than a bolted-on page.
   The layout itself is different on purpose: chapters read as a photo
   essay — one full photo, then its caption, then the next — instead
   of the portfolio's multi-column masonry, since a grid doesn't leave
   room for a real description under each frame.
