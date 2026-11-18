# Template: classic-serif-cv

- **Type:** CV
- **Source extension:** .tex
- **Engine/toolchain:** lualatex
- **Page limit:** 1 page
- **Fonts:** Times New Roman (system font, loaded from C:/Windows/Fonts/ by file name - must be installed; on a machine without it, swap the `\setmainfont` line for `TeX Gyre Termes`)
- **Class/packages:** article, geometry, fontspec, hyperref, titlesec, enumitem (all standard in MiKTeX/TeX Live)

## Compile command

    cd cv && rm -f <file>.pdf && mkdir -p build && lualatex -interaction=nonstopmode -output-directory=build <file>.tex && mv build/<file>.pdf ./

## Style rules

- Single column, one page, 10pt Times New Roman, margins 0.6in left/right.
- Header: name centered in bold capitals at 24pt, then one centered contact line: the email as a clickable `mailto:` link whose visible text is the literal address, the phone as plain text, a clickable link reading just "LinkedIn" (full `https://` URL as the target), and the city, separated by `|`. Both links are styled blue and underlined (via the `\link` macro) so readers can see they are clickable. The email must stay visible as literal text for ATS; the LinkedIn URL is only in the link target.
- Section headings: bold, with a heavier (0.9pt) full-width rule beneath. Between entries inside a section put a subtle grey hairline with `\subrule` (before every `\entry` except the first in a section); never put a hairline directly above a section heading. Order: Education, Professional Experience, Projects & Leadership, Skills & Interests. No profile summary and no References or Languages sections.
- Each entry uses `\entry{Organisation}{Location}{Role}{Dates}`: organisation and location bold on the first line, role and dates italic on the second. Dates use an ASCII hyphen range, e.g. `Jul 2026 - Present`.
- Bullets: round, one to two lines, start with a verb and carry a number where one exists.
- Do NOT add hidden or white text, or a keyword block. Keywords go into real bullets only where truthful.

- File naming: save as `cv/Firstname_Lastname_<Company>_CV.tex` (PDF `Firstname_Lastname_<Company>_CV.pdf`), company words joined by underscores with original capitalisation, no role in the name unless a CV for that company already exists.

## Known pitfalls

- Escape `&` as `\&`, `%` as `\%`, `#` as `\#`.
- Do not put `\vspace` between `\item`s. If the page overflows, cut the lowest-relevance bullet or entry instead of shrinking margins or the font.
- The class has no page-break control: the one-page limit is enforced by content, so check the page count after every edit.
