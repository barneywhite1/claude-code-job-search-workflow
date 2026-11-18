# Template: classic-serif-letter

- **Type:** Cover letter
- **Source extension:** .tex
- **Engine/toolchain:** lualatex
- **Page limit:** 1 page
- **Fonts:** Times New Roman (system font, loaded from C:/Windows/Fonts/ by file name - must be installed; on a machine without it, swap the `\setmainfont` line for `TeX Gyre Termes`)
- **Class/packages:** article, geometry, fontspec, hyperref (all standard in MiKTeX/TeX Live)

## Compile command

    cd cover_letters && rm -f <file>.pdf && mkdir -p build && lualatex -interaction=nonstopmode -output-directory=build <file>.tex && mv build/<file>.pdf ./

## Style rules

- Single column, left-aligned, 11pt Times New Roman, no bullets, no bold in the body.
- Centered header: name (bold), city, then the email (clickable `mailto:` link, address visible), the phone as text, and a clickable "LinkedIn" link; both links are blue and underlined via `\link`. Then a date in UK form (e.g. `6 October 2026`), a salutation and 5-6 paragraphs separated by 9pt of space.
- Paragraph pattern: (1) role + credential + hook, (2) core evidence, quantified, (3) self-development, (4) breadth and transferable traits, (5) why this firm with two or three verified specifics, (6) short close. Close with "Yours sincerely," when the salutation names a person or team.
- Body is roughly 400-480 words so the letter fills one page.
- Wording follows 03-writing-style.md (no em-dashes, no cliches); only the layout and structure are borrowed from the reference letters.

- File naming: save as `cover_letters/Firstname_Lastname_<Company>_CoverLetter.tex` (PDF `Firstname_Lastname_<Company>_CoverLetter.pdf`), company words joined by underscores with original capitalisation, no role in the name unless a letter for that company already exists.

## Known pitfalls

- Escape `&` as `\&`, `%` as `\%`, `#` as `\#`; `£` is fine under lualatex.
- If the letter spills to a second page, cut the lowest-relevance sentence of the breadth paragraph first. Never shrink the font or margins.
