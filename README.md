# Old School RuneScape × MyAnimeList



An **Old School RuneScape-inspired custom list theme for MyAnimeList**, created as an entry for the **MAL BUNKASAI 2026 List Design Contest**.

The goal of the project was to make a MyAnimeList anime/manga list feel more like an Old School RuneScape interface



The idea was partly inspired by the **Dungeons \& Dragons community list design by Half\_Bl00d**. That theme showed that a MAL list does not necessarily have to be visually connected to anime or manga, and can instead fully commit to another game's interface and aesthetic.

> \\\*\\\*Note:\\\*\\\* This is an unofficial fan-made theme by Tafixados. It is not affiliated with, endorsed by, or sponsored by Jagex or MyAnimeList.

\---

## Features

The theme currently includes:

* A full **Old School RuneScape-inspired visual redesign** for modern MyAnimeList anime and manga lists.
* Custom **RuneScape-style fonts, cursors, borders, panels, buttons, icons, colours, and interface details**.
* Anime and manga statuses presented as **quest states**
* Entry cards rebuilt into compact **OSRS-style information panels** while retaining MAL's normal list functionality.
* Separate handling for **anime and manga-specific data**.

  * Recommended column setup for the anime list includes: Numbers, Score, Type, Episodes, Rating, Tags, Image, Premiered.
  * Recommended column setup for the manga list includes: Numbers, Score, Chapters, Volumes, Tags, Type, Image, Published Date.
  * The stylesheet should support all available columns in both the common and modern-only settings that are not MAL Supporter exclusive.
* 
* Custom icons for progress, score, type, rating, dates, tags, volumes, and other information fields.
* A custom **sidebar** based on RuneScape interface icons.
* Custom dragon scimitar cursor reminiscent of the olden days of downloading viruses onto the family computer.
* A responsive **minimap** which imitates player movement with a unique path for both the anime and manga lists.
* A themed **Stats** ribbon and **Filters** interface, **quest completion dialog** when an entry reaches its final episode, styled **episode discussion/rating popup** with custom 1–5 star buttons, custom footer inspired by RuneScape's logout feedback interface, restyled score dropdowns and other smaller controls.
* Numerous smaller hover states, status colours, pixel-art details, and other visual references intended to make the list feel like an actual game interface.

\---

## Anime and Manga Lists

The same core design supports both MAL anime and manga lists, but the theme contains separate rules where the underlying MAL structure differs.

For example:

* Anime uses **episodes**, while manga uses **chapters and volumes**.
* Anime can display fields such as **studios** and **licensors**.
* Manga can display fields such as **magazine** and **retail manga**.
* The two list types can use their own visual details, banner artwork, and minimap routes while keeping the overall interface consistent.

This was important because MAL does not expose the exact same HTML structure or column set for both list types.

\---

## CSS-Only Design

The project is intentionally built around the restrictions of MyAnimeList's custom list system.

The theme is primarily **CSS-only**. No custom JavaScript is injected into the list.

That limitation made some of the more game-like elements slightly ridiculous to build, particularly the minimap. Its movement is produced through CSS scroll-driven animation and manually prepared map routes rather than a normal JavaScript position tracker.

It also means that some ideas which would have been fun — random events, clickable XP drops, AFK skilling widgets, persistent counters, randomly selected routes, or small interactive minigames — are outside the scope of the theme.

Some MAL interfaces also exist inside isolated frames or otherwise do not inherit the user's list CSS. The **Quick Add** contents are one example, so not every MAL-owned popup can be fully reskinned.

\---

## Design Philosophy

The project tries to stay recognisably MyAnimeList underneath the RuneScape skin.

The goal was not to replace MAL's functionality or turn the page into a novelty webpage at the expense of usability. Wherever possible, the theme keeps the original controls functional and changes only how they are presented.

The more decorative features are also deliberately kept out of the way. For example, the minimap only appears when there is enough unused space beside the list and disappears automatically when the viewport becomes too narrow.

\---

## Assets and Inspiration

This project uses and references visual material from **Old School RuneScape** and the **Old School RuneScape Wiki** for the purpose of recreating the game's interface style.

Old School RuneScape, RuneScape, and related game assets are the property of **Jagex Ltd.**

MyAnimeList and associated marks are the property of **MyAnimeList Co., Ltd.**

The theme is an **unofficial, non-commercial fan project** created for the MAL BUNKASAI 2026 List Design Contest. No ownership of Jagex or MyAnimeList assets is claimed.

Special inspiration credit goes to **Half\_Bl00d's Dungeons \& Dragons community list design**, which helped inspire the idea of building a MAL theme around a completely unrelated game aesthetic.

This repository contains an original CSS theme and fan-made layout work, but it also references third-party game assets.

The CSS and original project code may be reused or modified with attribution, but this repository does **not** grant rights to any Old School RuneScape, RuneScape, Jagex, MyAnimeList, or other third-party assets included or referenced by the theme.

For third-party assets, please refer to the rights and usage policies of their respective owners.

\---

## Repository Structure

The repository is organised around a main theme stylesheet and smaller CSS modules for individual components.

During development, older iterations may also be kept in legacy folders for reference and regression testing. The actively used files should be treated as the source of truth.

Because MAL and CDN caching can be aggressive, the main theme filename may occasionally be versioned when testing updates.

\---

## Status

The theme is feature-complete enough for contest submission, with the remaining work focused mainly on polishing, bug fixes, browser compatibility, small easter eggs, and making sure future changes do not break already-finished components.

At this point, adding more functionality is less important than keeping the overall design coherent and stable.

\---

## Usage

To apply this theme on your own list, simply paste the contents of the "MAL IMPORT CODE" text document into the "Add custom CSS" section of any of the MAL provided Modern List Design customization settings.



