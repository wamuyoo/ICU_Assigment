# Under Zambian Skies — A Star Gazing Guide for Lusaka

**Author:** Wamuyoo Ndiyoi
**Student ID:** SIN 1506172114
**Course:** Semester 2, IWD

## Project Overview

This is a single-page HTML website about star gazing from Lusaka, Zambia. It was built as a second-semester assignment to demonstrate understanding of HTML elements, attributes, semantic structure, and best practices. The website covers southern hemisphere constellations visible from Lusaka's latitude (15°25'S), dark-sky locations across Zambia, essential equipment, cultural sky lore, and practical tips for observers in and around Lusaka.

The website includes personal content such as my own photograph of the Southern Cross and Milky Way captured from Garden House Township, personal experiences at locations like the Lower Zambezi, and navigation techniques passed down by my father.

**File:** `index.html`

---

## Question 2: HTML Elements

### 1. Which 5 elements did you find most challenging to implement and why?

1. **`<table>` (with `<thead>`, `<tbody>`, `<caption>`, `<th>`, `<td>`)** — Tables were the most complex because they require multiple nested child elements to be structured correctly. I had to ensure every row had the correct number of columns, that headers used `<th>` with `scope="col"` for accessibility, and that the `<caption>` provided a meaningful title. The constellations table with five columns of data required careful planning to keep the information aligned and readable. I used two tables on the page — one for constellations and one for the 2026 astronomical events calendar — each with different column structures.

2. **`<details>` and `<summary>`** — These elements were challenging because they create interactive, collapsible content using only HTML with no JavaScript required. The challenge was deciding which FAQ item to leave open by default using the `open` attribute, and ensuring the summary text was descriptive enough that users would want to click and expand each item. I chose to leave the Southern Cross navigation question open since it is the most practical tip for someone star gazing in Lusaka.

3. **`<figure>` and `<figcaption>`** — Implementing figures required thinking about the relationship between the image and its caption as a single semantic unit. I used my own photograph of the Southern Cross and Milky Way that I captured from Garden House Township on 24 February 2019 using a mobile phone. The challenge was writing `alt` text that described the visual content for accessibility, while the `<figcaption>` provided the personal context of when and where the photo was taken.

4. **`<dl>`, `<dt>`, and `<dd>` (Definition Lists)** — I used definition lists in two places: for telescope types and for dark-sky locations across Zambia. The challenge was understanding when a definition list is more appropriate than an unordered list. I chose `<dl>` when each item had a clear term-and-description relationship (e.g., "South Luangwa National Park" followed by its description and personal notes), which better communicated the structure than a plain `<ul>` would have.

5. **`<nav>`** — While the `<nav>` element itself is simple, the challenge was creating a functional navigation system using anchor links (`href="#id"`) that correctly linked to each of the eight sections on the page. I had to make sure every `id` attribute on the target sections matched the corresponding `href` value exactly, including consistent use of lowercase and hyphens (e.g., `id="big5"` matching `href="#big5"`).

### 2. How did you use semantic elements to structure your content?

I used semantic elements to give the page a clear, meaningful structure that both browsers and screen readers can understand:

- **`<header>`** — Wraps the site title ("Under Zambian Skies"), subtitle, Lusaka's geographic coordinates, and the navigation menu. It identifies the introductory content of the page.
- **`<nav>`** — Contains the list of eight internal anchor links, clearly marking this as the site's navigation region.
- **`<main>`** — Wraps all the primary content, distinguishing it from the header and footer. There is only one `<main>` element on the page, as required by the HTML specification.
- **`<section>`** — Each major topic (Why Zambia, Constellations, Big 5, Equipment, When to Observe, Dark-Sky Locations, Sky Lore, FAQ, Resources) is wrapped in its own `<section>` with an `id` attribute for navigation.
- **`<article>`** — Used within sections where the content could stand alone as an independent piece of writing, such as the explanation of Lusaka's southern hemisphere advantage and the Stars in African Tradition narrative that includes my father's teaching about the Southern Cross.
- **`<aside>`** — Used for supplementary content like the "Did You Know?" moonbow fact about Victoria Falls and the "Quick Tips" countdown for a first night out in Lusaka.
- **`<footer>`** — Contains the copyright notice, back-to-top link, and my author information using the `<address>` element.

This hierarchy (`header` → `nav` → `main` → `section` → `article` → `footer`) creates a logical document outline that improves accessibility, SEO, and code readability.

### 3. Which element was most useful for organizing your layout and why?

The **`<section>`** element was the most useful for organising the layout. Since the website covers multiple distinct topics (constellations, equipment, viewing conditions, locations, cultural lore, FAQ), each topic naturally fits into its own `<section>`. This element allowed me to:

- Give each topic a unique `id` for anchor-link navigation from the `<nav>` menu.
- Visually and semantically separate content areas with `<hr>` dividers between them.
- Create a clear, scannable document structure where a reader can jump directly to any topic.

Without `<section>`, the page would have been a single continuous block of content with no meaningful grouping, making it harder to navigate and maintain.

---

## Question 3: HTML Attributes

### 1. Which 3 attributes were essential for making your website functional?

1. **`href`** — This attribute is the backbone of all navigation and linking on the website. It powers the internal anchor links in the `<nav>` menu (e.g., `href="#constellations"`), the external resource links that open in new tabs (e.g., the Lusaka-specific light pollution map, TimeAndDate Lusaka Night Sky, NASA Spot the Station for Lusaka), the `mailto:` link in the footer, and the back-to-top link. Without `href`, the website would have no interactivity or navigation at all.

2. **`id`** — The `id` attribute works hand-in-hand with `href` to enable internal page navigation. Each `<section>` has a unique `id` (like `id="about"`, `id="equipment"`, `id="faq"`), and the navigation links point to these IDs. I also used `id="top"` on the `<header>` so the footer's "Back to Top" link has a destination. This attribute must be unique across the entire page, ensuring each link leads to exactly one destination.

3. **`alt`** — The `alt` attribute on the `<img>` element provides alternative text for my photograph. This is essential for accessibility because screen readers read the alt text aloud for visually impaired users. It also displays in place of the image if the file fails to load. My image has `alt="A panoramic view of the Milky Way galaxy arching across a dark African sky"`, which conveys the content of the photograph to users who cannot see it.

### 2. How did you use the `class` and `id` attributes differently?

In this project, I primarily used the **`id`** attribute rather than `class`. The two serve different purposes:

- **`id`** — I used `id` to uniquely identify sections of the page for anchor-link navigation. For example, `id="top"` on the header, `id="constellations"` on the constellations section, and `id="faq"` on the FAQ section. Each `id` value appears only once on the entire page, which is a requirement of the HTML specification. The `id` attribute is also useful for CSS targeting when a style applies to one specific element.

- **`class`** — The `class` attribute was not used in this project because the website relies on internal CSS that targets element types directly (e.g., `p { text-indent: 40px; }`) rather than custom class names. If the website were to grow or if I needed to style specific paragraphs differently from others, I would introduce classes. For instance, I might add `class="no-indent"` to paragraphs inside the aside or blockquote where indentation should not apply. The key difference is that `class` can be reused across multiple elements, while `id` must be unique.

### 3. Which attribute helped improve user experience the most and why?

The **`target="_blank"`** attribute (used together with `rel="noopener"`) improved user experience the most. This attribute is applied to all external links — the light pollution map zoomed into Zambia, the TimeAndDate Lusaka night sky page, TheSkyLive Lusaka planetarium, NASA Spot the Station for Lusaka, Stellarium Web, and the ASSA Big 5 observing guide. It causes these links to open in a new browser tab, meaning the user can explore an external resource without losing their place on the star gazing website. Without `target="_blank"`, clicking any external link would navigate away from the page entirely, forcing the user to use the browser's back button to return. The companion attribute `rel="noopener"` is a security best practice that prevents the external page from accessing the originating page's `window` object.

---

## Question 4: Development Process

### 1. How did you plan your website structure before coding?

I followed a structured planning approach before writing any code:

1. **Topic selection and research** — I chose star gazing from Lusaka, Zambia as the topic because it is personally meaningful to me. I researched which constellations are visible from 15°S latitude, identified Zambia's best dark-sky locations (South Luangwa, Kafue, Lower Zambezi, Liuwa Plain), and gathered information on southern African sky lore and cultural interpretations of constellations.

2. **Content outline** — I mapped out the major sections the website would need: an introduction to why Zambia is ideal for star gazing, a constellations reference table, the African Big 5 deep-sky objects, an equipment guide, viewing conditions specific to Lusaka's dry and wet seasons, dark-sky locations, cultural context including personal anecdotes, and a FAQ. This outline ensured I had enough content to justify 25+ HTML elements.

3. **Personal content integration** — I planned where to include personal touches: my own photograph of the Southern Cross taken from Garden House Township, my father's teaching about using the Southern Cross for navigation, my experience at Time and Tide Safaris on the Lower Zambezi, and the practical tip about using mobile phone Professional mode for night sky photography.

4. **Element and attribute planning** — I created a checklist of the required 25 HTML elements and 15 attributes, then mapped each one to a specific piece of content. For example, the constellations data would use `<table>`, the FAQ would use `<details>`/`<summary>`, and the telescope types and dark-sky locations would use `<dl>`/`<dt>`/`<dd>`.

5. **Semantic structure sketch** — I sketched the document hierarchy: `<header>` with `<nav>`, `<main>` containing multiple `<section>` elements, `<article>` and `<aside>` for specific content types, and `<footer>` at the bottom.

### 2. What was your approach to testing and debugging your HTML?

- **Browser preview** — I opened the HTML file directly in a web browser after each major section to check that the layout, links, and content displayed correctly.
- **Anchor link testing** — I clicked every navigation link in the `<nav>` menu to verify that each one scrolled to the correct section on the page.
- **Image loading** — I confirmed that my personal photograph (`Southern Crux - milky way.jpg`) loaded correctly from the same directory as the HTML file, and that the `alt` text displayed when the image was temporarily renamed.
- **Interactive elements** — I tested the `<details>`/`<summary>` elements to confirm they expanded and collapsed correctly, and that the FAQ item with the `open` attribute (the Southern Cross navigation question) was expanded by default on page load.
- **External links** — I verified that all external links (TimeAndDate, TheSkyLive, NASA, Stellarium, ASSA, and the light pollution map zoomed to Zambia) opened correctly in new tabs.
- **Code review** — I reviewed the source code to ensure all tags were properly closed, all attribute values were quoted, and the nesting hierarchy was correct (e.g., `<tr>` inside `<tbody>`, `<li>` inside `<ol>`).

### 3. What challenges did you face and how did you overcome them?

1. **Selecting Zambia-specific content** — Generic star gazing guides focus on the Northern Hemisphere. I overcame this by specifically researching southern hemisphere constellations visible from 15°S, Zambia's dry and wet seasons, and local dark-sky sites. I also drew on my own experience — my photograph from Garden House Township, visits to the Lower Zambezi, and my father's navigation teachings — to make the content authentically Zambian.

2. **Including a personal photograph** — Using my own mobile phone photo of the Southern Cross and Milky Way required ensuring the image file was in the same directory as the HTML file and that the `src` attribute pointed to the correct filename. I also had to write appropriate `alt` text and a `<figcaption>` that gave context about when and where the photo was taken.

3. **Balancing element variety with natural content** — The requirement for 25+ elements meant I needed to use elements like `<mark>`, `<abbr>`, `<blockquote>`, `<cite>`, and `<address>` in places where they made semantic sense, not just for the sake of using them. I solved this by finding natural content opportunities: `<abbr>` for IAU, LMC, SMC, ASSA, and HTML; `<mark>` to highlight the key advantage of low light pollution; `<address>` for my author information in the footer.

4. **Table accessibility** — Making the data tables accessible required learning about the `scope` attribute on `<th>` elements and the `summary` attribute on the `<table>` element. I researched these attributes and applied them to ensure screen readers could correctly associate header cells with data cells.

---

## Question 5: Git & GitHub Implementation

### 1. What Git commands did you use during development?

The following Git commands were used throughout the project:

- `git init` — Initialised a new Git repository in the project folder.
- `git add index.html` — Staged the HTML file for committing. Also used `git add .` to stage all files (including the image and README).
- `git commit -m "message"` — Created snapshots of the project at each development milestone.
- `git status` — Checked which files were modified, staged, or untracked.
- `git log` — Reviewed the commit history to track progress.
- `git branch` — Verified the current branch (main).
- `git remote add origin <URL>` — Connected the local repository to the GitHub remote.
- `git push -u origin main` — Pushed the local commits to the remote GitHub repository.

### 2. How many commits did you make and what was your commit message strategy?

I made approximately **8 commits** during development, following a clear and descriptive commit message strategy:

1. `Initial commit: HTML boilerplate and header with Lusaka coordinates`
2. `Add constellations table for southern hemisphere from Lusaka`
3. `Add African Big 5 deep-sky objects section`
4. `Add equipment guide with telescope definition lists`
5. `Add viewing conditions, Zambia-specific light pollution map, and 2026 events`
6. `Add dark-sky locations with personal photo and Lower Zambezi experience`
7. `Add cultural sky lore with personal anecdote and FAQ section`
8. `Add quick tips, resources, footer, and internal CSS styling`

My strategy was to commit after completing each logical section of the website, using messages that start with a verb (Add, Update, Fix) and clearly describe what changed. This makes the commit history easy to read and allows me to roll back to any specific stage of development if needed.

### 3. Why is version control important for web development projects?

Version control is important for several reasons:

- **History and rollback** — Every commit is a snapshot of the project. If a change breaks something, I can revert to a previous working version instantly rather than trying to undo changes manually. For example, when I was integrating my personal photo, I could revert if the image broke the layout.
- **Collaboration** — In team projects, Git allows multiple developers to work on different features simultaneously using branches and merge their work together without overwriting each other's code.
- **Documentation** — The commit history serves as a development log, showing what was built, when, and why. This is valuable for understanding how a project evolved over time.
- **Backup** — Pushing to GitHub creates a remote backup of the project. Even if the local machine fails, the code is safely stored online.
- **Accountability** — In academic settings, version control proves the work was done incrementally over time rather than all at once, demonstrating a genuine development process.

---

## Question 6: Code Quality & Best Practices

### 1. How did you ensure your HTML was valid and error-free?

- **Proper document structure** — The file begins with `<!DOCTYPE html>` to declare the document type, followed by a properly nested `<html>`, `<head>`, and `<body>` structure.
- **Tag closure** — Every opening tag has a corresponding closing tag. Self-closing elements like `<meta>`, `<br>`, `<hr>`, and `<img>` are written correctly for HTML5.
- **Attribute quoting** — All attribute values are enclosed in double quotes (e.g., `charset="UTF-8"`, `id="about"`).
- **Nesting validation** — Elements are correctly nested (e.g., `<li>` only appears inside `<ul>` or `<ol>`, `<tr>` only inside `<thead>` or `<tbody>`, `<dt>` and `<dd>` only inside `<dl>`).
- **Unique IDs** — Every `id` value on the page is unique, preventing conflicts in anchor navigation and CSS targeting.
- **W3C Validator** — The code can be validated using the W3C Markup Validation Service at `https://validator.w3.org/` to check for any remaining errors or warnings.

### 2. What best practices did you follow for writing clean, readable code?

- **Consistent indentation** — All nested elements are indented with 4 spaces to clearly show the parent-child hierarchy.
- **HTML comments** — Major sections are preceded by descriptive comments (e.g., `<!-- SECTION 2: Constellations Visible from Lusaka -->`) that act as signposts when scrolling through the code.
- **Semantic element choice** — I used semantic elements (`<section>`, `<article>`, `<aside>`, `<nav>`, `<header>`, `<footer>`, `<figure>`, `<address>`) instead of generic `<div>` elements, which makes the code self-documenting.
- **Meaningful attribute values** — IDs use descriptive, lowercase names (e.g., `id="constellations"`, `id="big5"`) and alt text is written as a full descriptive sentence.
- **Element checklist** — I included a comprehensive HTML comment at the bottom of the file listing all 38 elements and 21 attributes used, making it easy for graders to verify the requirements are met.
- **Logical content ordering** — Sections flow in a natural learning progression: why Zambia → what to look at → what equipment to use → when to go → where to go → cultural context → FAQ → resources.

### 3. How would you improve your website if you had more time?

1. **Add more personal photographs** — Include my own photos of each constellation and dark-sky location I have visited, similar to how I included my Southern Cross photo from Garden House Township.
2. **Responsive design** — Add CSS media queries so the tables and navigation adapt gracefully to mobile phone screens, since many users in Zambia access websites primarily through their phones.
3. **Interactive star map** — Embed an interactive star map (using an iframe from Stellarium Web or TheSkyLive) set to Lusaka's coordinates so visitors can explore the sky in real time.
4. **Multi-page structure** — Split the content into separate pages (e.g., `constellations.html`, `equipment.html`, `locations.html`) linked together with a consistent navigation bar, creating a true multi-page website.
5. **Mobile phone photography guide** — Expand the tip about using phone Professional mode into a full section with step-by-step instructions for capturing the night sky with a smartphone, since this is how I took my own Southern Cross photograph.
6. **More Zambian cultural content** — Add more traditional sky stories from different Zambian ethnic groups, and possibly include audio recordings of elders sharing constellation stories in local languages.

---

## Element & Attribute Summary

### HTML Elements Used (38+ unique)

`html`, `head`, `meta`, `title`, `body`, `header`, `nav`, `main`, `section`, `article`, `footer`, `h1`, `h2`, `h3`, `p`, `a`, `ul`, `ol`, `li`, `strong`, `em`, `br`, `hr`, `img`, `figure`, `figcaption`, `table`, `thead`, `tbody`, `tr`, `th`, `td`, `caption`, `details`, `summary`, `aside`, `blockquote`, `cite`, `mark`, `small`, `dl`, `dt`, `dd`, `address`, `abbr`

### HTML Attributes Used (21 unique)

`lang`, `charset`, `name`, `content`, `href`, `src`, `border`, `alt`, `width`, `height`, `id`, `title`, `target`, `rel`, `cellpadding`, `cellspacing`, `scope`, `summary`, `open`, `loading`, `style`
