# The Groto Font Family

**Groto** is an open-source OpenType font family that significantly expands upon the design of the popular [Roboto](https://github.com/google/roboto/) font. It offers a much **wider range of widths** and includes some redesigned glyphs, most notably the "l", to enhance its versatility and readability.

**Important Note:** All fonts in the Groto family are currently **experimental and unfinished**. They are provided for testing and evaluation purposes and are not yet recommended for production use. The designs and font files are subject to change.

## Who is Groto for?

*   **Designers:** Who need a Roboto-like typeface but require more flexibility in terms of text width for various layout challenges.
*   **Developers:** Looking for an open-source font with a broad selection of weights and widths for UI or web applications.
*   **Typographers:** Interested in exploring variations on a well-known sans-serif design.

## Why use Groto?

*   **Extended Width Range:** Groto's primary advantage is its comprehensive set of condensed and expanded styles, offering far more options than standard Roboto.
*   **Open Source:** Licensed under the Apache 2.0 License, allowing for broad use and modification.
*   **Improved Glyphs:** Specific characters, such as the "l", have been redesigned for better clarity and aesthetic appeal.
*   **Versatility:** Suitable for a wide array of applications, from print design to user interfaces and web content, once mature.

## Installation

The Groto font family can be installed in several ways depending on your needs:

### For Desktop Use (Designers, General Users)

The easiest way to use Groto on your desktop is to install the pre-built OpenType (OTF) or TrueType (TTF) fonts:

1.  **Download the font packages:**
    *   [Groto (81 OTF fonts)](https://github.com/twardoch/groto-fonts-apache2/raw/master/Fonts/Groto-OTF.zip)
    *   [Groto (81 TTF fonts)](https://github.com/twardoch/groto-fonts-apache2/raw/master/Fonts/Groto-TTF.zip)
2.  **Extract the ZIP file(s).**
3.  **Install the fonts** according to your operating system's standard procedure (e.g., using Font Book on macOS, right-clicking and selecting "Install" on Windows).

You can preview the entire family using these PDF documents:
*   [Groto Overview PDF](https://github.com/twardoch/groto-fonts-apache2/raw/master/Media/Groto-Overview.pdf)
*   [Groto Specimen PDF](https://github.com/twardoch/groto-fonts-apache2/raw/master/Media/Groto-Specimen.pdf)
*   [Groto Glyph Set PDF](https://github.com/twardoch/groto-fonts-apache2/raw/master/Media/Groto-Glyphset.pdf)

### For Web Developers

Groto web fonts are available in WOFF, WOFF2, EOT, SVG, and TTF formats. You can find them in the [`WebFonts/`](WebFonts/) directory. **Please note that the web fonts in this directory are an older version of the family.**

1.  **Choose your preferred format** (WOFF2 is generally recommended for modern browsers).
2.  **Include the font files** in your web project.
3.  **Use CSS `@font-face` rules** to define the font family, style, weight, and source URL for each font variation you intend to use.

**Example `@font-face` rule:**

```css
@font-face {
  font-family: 'Groto';
  src: url('path/to/your/webfonts/Groto-5No400Rg.woff2') format('woff2'), /* Modern Browsers */
       url('path/to/your/webfonts/Groto-5No400Rg.woff') format('woff');   /* Older Browsers */
  font-weight: 400; /* Regular */
  font-style: normal;
}

body {
  font-family: 'Groto', sans-serif;
}
```

*   **View the (older version) web specimen:** [Groto Web Specimen](https://twardoch.github.io/groto-fonts-apache2/WebFonts/demo/index.html)
*   **List of OTF-based web fonts (older version):** [Web OTF List](https://twardoch.github.io/groto-fonts-apache2/WebFonts/web-otf/index.html)
*   **List of TTF-based web fonts (older version):** [Web TTF List](https://twardoch.github.io/groto-fonts-apache2/WebFonts/web-ttf/index.html)

### For Font Developers & Contributors

If you plan to modify Groto or contribute to its development:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/twardoch/groto-fonts-apache2.git
    ```
2.  The primary source files are **`.glyphs` files** located in the [`Sources/`](Sources/) directory.
3.  You will need the **Glyphs font editor** ([https://glyphsapp.com/](https://glyphsapp.com/)) to work with these source files.

## Usage

Groto is primarily a font family, so its "usage" refers to how it's employed in design and development projects, or how its source files are managed.

### As a Font

Once installed (see [Installation](#installation)), Groto can be selected and used in any application that allows font choice, such as:

*   Graphic design software (Adobe Illustrator, Photoshop, Inkscape, etc.)
*   Word processors (Microsoft Word, Google Docs, Pages)
*   Presentation software (PowerPoint, Keynote, Google Slides)
*   Web pages (via CSS, as shown in the [Web Developers installation](#for-web-developers) section)
*   User interface design tools (Figma, Sketch, Adobe XD)

### Command-Line Usage (Font Development)

There isn't a direct Command Line Interface (CLI) tool for *using* the Groto fonts in the traditional sense of a software utility. Fonts are utilized by applications.

However, the project includes a Python helper script, `make-instancemap.py`, which is used in the font development process. This script is **not a standalone build tool** but rather generates configuration data for the Glyphs font editor.

*   **Purpose:** To create a list of all font instances (combinations of weight and width) that Groto supports.
*   **How to run it:**
    Navigate to the repository's root directory and execute:
    ```bash
    python Sources/make-instancemap.py
    ```
    (Note: This script is written for Python 2. Ensure you have a Python 2 environment to run it.)
*   **Output:** The script generates a file named `Groto.txt` (or similar, based on italics settings in the script, though currently it's set to produce `Groto.txt`) in the directory where it's run. This file contains a textual representation of the font instances.
*   **Usage of the output:** The content of `Groto.txt` is intended to be copied and pasted into the "Instances" pane of the Font Info window within the Glyphs application.

### Programmatic Usage (Conceptual)

As a font family, Groto isn't a software library that you would import and call functions from in, for example, Python or JavaScript.

"Programmatic usage" in the context of fonts typically means:

1.  **Referencing fonts in code:** Such as in CSS for web development:
    ```css
    .heading {
      font-family: 'Groto', sans-serif;
      font-weight: 700; /* Bold */
      /* Assuming 'Groto' with bold weight is defined via @font-face or installed */
    }
    ```
2.  **Manipulating font files with libraries:** Using font-specific libraries (like FontTools for Python) to programmatically modify or analyze the font files themselves. This is an advanced use case relevant to font developers. For example, one might write a script using FontTools to batch-modify metadata in the compiled OTF/TTF files. This repository does not currently include examples of such programmatic manipulation of the *compiled* fonts.

## Technical Details

This section describes the technical aspects of the Groto font family, its structure, and how it's built.

### Font Family Structure

Groto is designed as a large family with a wide array of weights and widths. The naming convention and structure are systematically generated.

*   **Weights:** The family includes 9 weights, typically ranging from Thin (100) to Black (900). These are defined in the `make-instancemap.py` script with names like "100 Th", "200 ExLt", "300 Lt", "400 Rg", "500 Md", "600 SmBd", "700 Bd", "800 ExBd", "900 Blk".
*   **Widths:** The family spans 9 widths, from Ultra Condensed to Ultra Expanded. These are also defined in `make-instancemap.py` with names like "1 UlCd" (Ultra Condensed), "2 ExCd" (Extra Condensed), "3 Cd" (Condensed), "4 SmCd" (SemiCondensed), "5 No" (Normal), "6 SmWd" (Semi Expanded), "7 Wd" (Expanded), "8 ExWd" (Extra Expanded), "9 UlWd" (Ultra Expanded).
*   **Instances:** The combination of these weights and widths results in 81 static font instances (9 weights x 9 widths). Each instance has a specific name, weight class, and width class, as detailed in the `Sources/Groto.txt` file (which is generated by `make-instancemap.py`).
*   **Glyph Coverage:** Groto is subsetted to approximately 1160+ glyphs, covering the Latin alphabet.

### Groto UI

The [`Extra/GrotoUI/`](Extra/GrotoUI/) folder contains **Groto UI** fonts. These are special versions of Groto optimized for user interface design, particularly for use at tiny screen sizes. They are available in three widths:
*   GrotoUI (Normal)
*   GrotoUICond (Condensed)
*   GrotoUIUltra (UltraCondensed)
These fonts are provided in TTF format and also include web font versions (`.vfb` source files, samples, and various compiled formats).

### Source Files and Build Process

The development of Groto relies on the Glyphs font editor and a helper Python script.

1.  **Primary Source Files:** The font outlines and design data are stored in **`.glyphs` files** located in the `Sources/v1/` and `Sources/v2/` directories (e.g., `GrotoVF-01.glyphs` to `GrotoVF-13.glyphs`). These files are edited using the Glyphs application.
    *   *Note: The "VF" in the filenames suggests that these might be source files intended for generating Variable Fonts. The original README states, "The variable OpenType font Gotho VF will be prepared later." (assuming "Gotho" is a typo for "Groto").*

2.  **Instance Definition (`make-instancemap.py`):**
    *   The Python script [`Sources/make-instancemap.py`](Sources/make-instancemap.py) is used to programmatically generate the definitions for all 81 static instances of the Groto family.
    *   **Input:** The script contains Python dictionaries defining the names, numerical values, and class names for each weight and width.
    *   **Process:** It iterates through all combinations of these weights and widths.
    *   **Output:** It produces a text file (currently `Groto.txt` in the root directory when run from there) formatted for direct pasting into the Glyphs application's "Font Info > Instances" section.

3.  **Manual Step in Glyphs:**
    *   The content generated by `make-instancemap.py` (i.e., the content of `Groto.txt`) must be **manually copied and pasted** into the instance definitions panel within the relevant `.glyphs` source file in the Glyphs app.

4.  **Font Generation (Exporting from Glyphs):**
    *   Once the instances are defined in a `.glyphs` file, the final font files (OTF, TTF, and potentially web fonts if configured) are **exported directly from the Glyphs application.** The exact export settings within Glyphs determine the format and characteristics of the outputted fonts.

### Key Design Changes from Roboto

*   **Wider Range of Widths:** This is the most significant difference, providing many more stylistic options than standard Roboto.
*   **Redesigned "l":** The lowercase "l" glyph has been specifically redesigned. Other glyphs may also have been modified, but the "l" is explicitly mentioned.
*   **Glyph Set Subsetting:** Groto is subsetted to 1160+ glyphs covering the Latin alphabet, which might differ from the full Roboto glyph set.

### Repository Structure

The repository is organized as follows:

*   [`Fonts/`](Fonts/): Contains the installable static fonts in OTF and TTF formats.
    *   `Groto-OTF/`: OpenType Format fonts.
    *   `Groto-TTF/`: TrueType Format fonts.
*   [`WebFonts/`](WebFonts/): Contains web-ready versions of the fonts (**older version**).
    *   `web-otf/`: OTF-based web fonts (WOFF, WOFF2, EOT, SVG, TTF).
    *   `web-ttf/`: TTF-based web fonts (WOFF, WOFF2, EOT, SVG, TTF).
    *   `demo/`: A web specimen page.
*   [`Sources/`](Sources/): Contains the source files and development tools.
    *   `v1/`, `v2/`: Directories containing `.glyphs` source files.
    *   `make-instancemap.py`: Python script to generate instance definitions.
    *   `Groto.txt`: Example output of `make-instancemap.py`, defining instances.
*   [`Extra/GrotoUI/`](Extra/GrotoUI/): Contains the Groto UI fonts, optimized for small screen sizes.
    *   `samples/`: Image samples of Groto UI.
    *   `src/`: Source files for Groto UI (e.g., `.vfb` which are FontLab Studio files).
    *   `ttf/`, `ttfah/`, `web-ttf/`: Various compiled formats of Groto UI.
*   [`Media/`](Media/): Contains PDF documents showcasing the font family.
    *   `Groto-Overview.pdf`
    *   `Groto-Specimen.pdf`
    *   `Groto-GlyphSet.pdf`
*   `LICENSE`: The Apache 2.0 License file.
*   `README.md`: This file.
*   `.gitignore`: Specifies intentionally untracked files for Git.
*   `_config.yml`: Jekyll configuration for the GitHub Pages site.

## Contributing

Contributions to the Groto font family are welcome! As an open-source project, community involvement can help improve and expand Groto. Given the experimental nature of the font, feedback, bug reports, and design suggestions are particularly valuable.

### General Guidelines

*   **Respect the Design:** When making design changes, aim to stay consistent with the established aesthetic of Groto and its relationship to Roboto.
*   **Glyphs App:** Modifications to font outlines or metrics should generally be done using the Glyphs application, as the `.glyphs` files are the primary source.
*   **Python Script:** If you modify weight or width definitions, or how instances are generated, update the `Sources/make-instancemap.py` script accordingly. Please note this is a Python 2 script.
*   **Testing:** Thoroughly test any changes by exporting the fonts from Glyphs and previewing them in various applications and environments. Check for rendering issues, kerning problems, or other visual defects.

### How to Contribute

1.  **Fork the Repository:** Create your own fork of the `groto-fonts-apache2` repository on GitHub.
2.  **Create a Branch:** Make a new branch in your fork for your changes (e.g., `feature/add-cyrillic` or `fix/kerning-issue`).
3.  **Make Your Changes:**
    *   Edit the `.glyphs` files in the `Sources/` directory.
    *   If you update the instance definitions (e.g., add new weights/widths or change their parameters), modify `Sources/make-instancemap.py`.
    *   Run `python Sources/make-instancemap.py` to regenerate the `Groto.txt` instance definition file (or ensure your changes to the script correctly produce the desired output).
    *   Ensure the contents of the generated `Groto.txt` (or equivalent) are applied to the instances in the relevant `.glyphs` file.
4.  **Test Your Changes:** Export the fonts from Glyphs and test them.
5.  **Commit Your Changes:** Write clear and descriptive commit messages.
6.  **Push to Your Fork:** Push your changes to your branch on GitHub.
7.  **Submit a Pull Request:** Open a pull request from your branch to the `master` branch of the main `twardoch/groto-fonts-apache2` repository. Provide a detailed description of your changes in the pull request.

### Areas for Contribution

*   **Glyph Design:** Adding missing glyphs, improving existing ones, or expanding character sets (e.g., Cyrillic, Greek).
*   **Kerning:** Refining kerning pairs.
*   **Hinting:** Improving hinting for better on-screen rendering, especially on Windows.
*   **Bug Fixes:** Identifying and fixing issues in the font files or source files.
*   **Documentation:** Improving this README or other documentation.
*   **Build Process:** Potentially automating more of the build process (e.g., scripting Glyphs exports if feasible).

### Future Development

The original README mentioned: *"The variable OpenType font Gotho VF will be prepared later."*
Assuming "Gotho" was a typo for "Groto", development of a **Groto Variable Font (VF)** is a potential future direction. The `.glyphs` filenames in `Sources/` (e.g., `GrotoVF-01.glyphs`) also suggest that variable font development might have been an initial goal. Contributions towards this would likely be valuable.

## License

Groto is licensed under the [Apache License Version 2.0](./LICENSE). A copy of the license is included in this repository. By contributing to Groto, you agree that your contributions will be licensed under the same terms.

---
Copyright © 2017 by [Adam Twardoch](https://github.com/twardoch/) and the original authors of Roboto.
The Groto font family is based on the Roboto font, which is licensed under the Apache License, Version 2.0.
