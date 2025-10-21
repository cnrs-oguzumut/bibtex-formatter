# LaTeX & BibTeX Tools

A free, open-source web toolkit with two powerful tools for formatting academic documents. **Now with drag & drop figure renaming!**

🔗 **[Try it now!](https://cnrs-oguzumut.github.io/bibtex-formatter/)**

![LaTeX & BibTeX Tools Screenshot](screenshot.png)

## 🛠️ Two Tools in One

### 1. 📊 Figure Organizer
Automatically rename and organize your LaTeX figures with drag & drop simplicity - no scripts needed!

### 2. 📚 BibTeX Formatter
Format BibTeX and BBL bibliography files with abbreviated author names and journal titles. Handles special characters and LaTeX commands perfectly.

---

## 📊 Figure Organizer

### Features
- 🎯 **Drag & Drop Renaming**: Drop your figure files, get a ZIP with renamed figures
- 🔢 **Sequential naming**: Renames figures to Fig1, Fig2-a, Fig2-b, etc.
- 📦 **ZIP Download**: All renamed figures in one convenient package
- 💬 **Comment-aware**: Ignores commented-out figures in LaTeX
- 📝 **Auto-updates paths**: Updates all `\includegraphics` references
- 🐧 **Bash script option**: For command-line enthusiasts
- 🔒 **100% Local**: All processing in your browser, no uploads

### How It Works

#### Before:
```latex
\begin{figure}
    \includegraphics{./Figures/old_image_v2_final.pdf}
\end{figure}
\begin{figure}
    \includegraphics{./Images/chart1.pdf}
    \includegraphics{./Images/chart2.pdf}
\end{figure}
```

#### After:
```latex
\begin{figure}
    \includegraphics{./Figures_ordered/Fig1.pdf}
\end{figure}
\begin{figure}
    \includegraphics{./Figures_ordered/Fig2-a.pdf}
    \includegraphics{./Figures_ordered/Fig2-b.pdf}
\end{figure}
```

### Quick Start - Easy Way (NEW!)
1. Open the **Figure Organizer** tab
2. Drag and drop your `.tex` file
3. Review the renaming preview
4. **Drag and drop your figure files** into the golden drop zone
5. Click **"Download Renamed Figures (ZIP)"**
6. Extract the ZIP and use the renamed figures!

### Alternative: Bash Script Method
1. Open the **Figure Organizer** tab
2. Drag and drop your `.tex` file
3. Download the bash script
4. Run it in your project directory:
   ```bash
   bash organize_figures.sh
   ```

---

## 📚 BibTeX Formatter

### Features
- 📝 **Abbreviate author names**: "Jianqiao Hu" → "J. Hu"
- 🌍 **Special character support**: Handles accented names (García, Müller, Petäjä, etc.)
- 🔤 **LaTeX command preservation**: Preserves `{\"a}`, `{\'e}`, and other LaTeX accents
- 📚 **Abbreviate journal names**: "Computational Materials Science" → "Comput. Mater. Sci."
- 🗑️ **Remove duplicates**: Automatically detects and removes duplicate entries
- 📊 **Real-time statistics**: See how many entries were processed
- 🧪 **Test cases included**: Verify formatting with built-in examples
- 🔒 **100% Private**: All processing in your browser

### Advanced Features
- **Nested brace handling**: Correctly processes complex LaTeX commands in author names
- **Smart name detection**: Distinguishes between "Last, First" names and other comma-separated data
- **Already-abbreviated detection**: Skips names that are already in abbreviated form

### Supported Journals

The formatter includes abbreviations for 10+ common journals:
- Computational Materials Science → Comput. Mater. Sci.
- Acta Materialia → Acta Mater.
- International Journal of Plasticity → Int. J. Plast.
- Journal of the Mechanics and Physics of Solids → J. Mech. Phys. Solids
- And more... (easily extensible)

### How It Works

#### Before:
```bibtex
@article{example,
  author = {Jianqiao Hu and Zhuo Zhuang and V. Pet{\"a}j{\"a}},
  journal = {Computational Materials Science},
  ...
}
```

#### After:
```bibtex
@article{example,
  author = {J. Hu and Z. Zhuang and V. Pet{\"a}j{\"a}},
  journal = {Comput. Mater. Sci.},
  ...
}
```

### Quick Start
1. Open the **BibTeX Formatter** tab
2. Drag and drop your `.bib` or `.bbl` file
3. Select formatting options:
   - ✅ Abbreviate author names
   - ✅ Abbreviate journal names
   - ✅ Remove duplicates
4. Click "Process File"
5. Your formatted file downloads automatically!

---

## 🚀 Installation & Usage

### Option 1: Use Online (Recommended)
Visit: https://cnrs-oguzumut.github.io/bibtex-formatter/

### Option 2: Download and Run Locally
1. Download `index.html` from this repository
2. Double-click to open in your browser
3. Both tools work **completely offline** - no internet required!

---

## 💻 Technical Details

### Figure Organizer
- Parses LaTeX `\begin{figure}...\end{figure}` environments
- Handles whitespace and tabs in `\includegraphics` commands
- Removes LaTeX comments before processing
- Supports multiple images per figure (auto-letters: a, b, c...)
- **NEW**: Browser-based file renaming with JSZip
- **NEW**: Drag & drop interface with visual feedback
- **NEW**: Smart file matching by filename
- Generates bash script with safety checks (optional)

### BibTeX Formatter
- Supports both `.bib` and `.bbl` formats
- Handles various author name formats (First Last, Last, First)
- **NEW**: Proper nested brace counting for LaTeX commands
- **NEW**: Preserves special characters (`{\"a}`, `{\'e}`, etc.)
- **NEW**: Smart detection of already-abbreviated names
- Detects duplicates by content hash
- Extensible journal abbreviation dictionary

---

## 🎯 Use Cases

### Figure Organizer
- Preparing manuscripts for journal submission
- Organizing figures from multiple sources
- Cleaning up messy figure naming conventions
- Creating consistent figure numbering across documents
- **NEW**: Quick renaming without command line knowledge

### BibTeX Formatter
- Standardizing bibliography format for journals
- Converting full names to abbreviated format
- Handling international author names with accents
- Cleaning up bibliographies with duplicates
- Batch processing multiple bibliography files

---

## 🔧 Customization

### Adding Journal Abbreviations

Edit the `JOURNAL_ABBREV` dictionary in the HTML file:

```javascript
const JOURNAL_ABBREV = {
    'Your Journal Name': 'Abbrev.',
    'Another Journal': 'Another J.',
    // Add more here...
};
```

### Modifying Figure Naming

Change the naming scheme in the `processTexFile()` function:

```javascript
// Current: Fig1, Fig2-a, Fig2-b
const newName = `Fig${figureNumber}${ext}`;

// Example alternative: Figure_01, Figure_02a
const newName = `Figure_${figureNumber.toString().padStart(2, '0')}${ext}`;
```

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Figure Organizer
- Support for subfigure environments
- Additional figure environments (wrapfigure, etc.)
- Custom naming schemes
- Batch processing for multiple .tex files

### BibTeX Formatter
- Add more journal abbreviations
- Support for more author name formats
- Additional file formats
- Custom abbreviation rules
- More comprehensive special character handling

### How to Contribute

1. Fork this repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Commit (`git commit -m 'Add amazing feature'`)
5. Push (`git push origin feature/amazing-feature`)
6. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

Created to solve common formatting problems faced by researchers when preparing academic manuscripts.

Special thanks to the open-source community for:
- JSZip library for creating ZIP files in the browser
- Feedback and bug reports from researchers worldwide

---

## 📧 Support

- 🐛 **Found a bug?** [Open an issue](https://github.com/cnrs-oguzumut/bibtex-formatter/issues)
- 💡 **Have a feature request?** [Start a discussion](https://github.com/cnrs-oguzumut/bibtex-formatter/discussions)

---

## 📊 Statistics

![Downloads](https://img.shields.io/github/downloads/cnrs-oguzumut/bibtex-formatter/total)
![Stars](https://img.shields.io/github/stars/cnrs-oguzumut/bibtex-formatter)
![Issues](https://img.shields.io/github/issues/cnrs-oguzumut/bibtex-formatter)

---

⭐ **If you find these tools useful, please star this repository!**

---

## 🔄 Recent Updates

### Version 2.0.0 (Latest)
- ✨ **NEW**: Drag & drop figure file renaming with ZIP download
- ✨ **NEW**: Visual feedback for file matching
- 🐛 **FIXED**: Proper handling of nested braces in BibTeX (special characters)
- 🐛 **FIXED**: Correct processing of LaTeX accent commands
- 🎨 Improved UI with golden drop zone for figures
- 📦 Added JSZip library for in-browser ZIP creation
- 🧪 Added test cases tab for BibTeX formatter

### Version 1.0.0
- ✨ Initial release with two tools
- 📊 Figure Organizer: Sequential renaming with folder organization
- 📚 BibTeX Formatter: Author and journal abbreviation
- 🔒 100% client-side processing for privacy
- 📱 Responsive design for mobile devices

---

## 🌟 Why Use These Tools?

### No Installation Required
- Works directly in your browser
- No Python, no Node.js, no dependencies
- Cross-platform: Windows, Mac, Linux

### Privacy First
- All processing happens locally
- Your files never leave your computer
- No accounts, no tracking, no data collection

### Academic-Focused
- Built by researchers, for researchers
- Handles real-world LaTeX quirks
- Supports international characters and special formatting

### User-Friendly
- Drag & drop interface
- Visual previews before downloading
- Clear feedback and error messages

---

**Made with ❤️ for the academic community**
