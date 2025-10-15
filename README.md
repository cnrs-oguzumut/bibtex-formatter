# BibTeX Formatter

A free, open-source web tool to automatically format BibTeX and BBL bibliography files.

🔗 **[Try it now!](https://YOUR-USERNAME.github.io/bibtex-formatter/)**

![BibTeX Formatter Screenshot](screenshot.png)

## ✨ Features

- 📝 **Abbreviate author names**: Converts "Jianqiao Hu" → "J. Hu"
- 📚 **Abbreviate journal names**: "Computational Materials Science" → "Comput. Mater. Sci."
- 🗑️ **Remove duplicates**: Automatically detects and removes duplicate entries
- 🔒 **100% Private**: All processing happens in your browser - no data uploaded
- 💻 **Cross-platform**: Works on Mac, Windows, Linux
- 📦 **No installation**: Just open the HTML file or use the web version

## 🚀 Quick Start

### Option 1: Use Online (Recommended)
Visit: https://YOUR-USERNAME.github.io/bibtex-formatter/

### Option 2: Download and Run Locally
1. Download `index.html` from this repository
2. Double-click to open in your browser
3. Drag and drop your `.bib` or `.bbl` file
4. Click "Process File"
5. Your formatted file will be downloaded automatically!

## 📖 How It Works

### Before:
```bibtex
@article{example,
  author = {Jianqiao Hu and Zhuo Zhuang and Fengxian Liu},
  journal = {Computational Materials Science},
  ...
}
```

### After:
```bibtex
@article{example,
  author = {J. Hu and Z. Zhuang and F. Liu},
  journal = {Comput. Mater. Sci.},
  ...
}
```

## 🎯 Use Cases

- Preparing manuscripts for journal submission
- Standardizing bibliography format across multiple papers
- Converting full author names to abbreviated format
- Cleaning up bibliography files with duplicate entries

## 🛠️ Supported Formats

- **BibTeX files** (`.bib`)
- **BBL files** (`.bbl`) - compiled bibliography files

## 🔧 Customization

You can easily add more journal abbreviations by editing the `JOURNAL_ABBREV` object in the code:

```javascript
const JOURNAL_ABBREV = {
    'Your Journal Name': 'Abbrev.',
    // Add more here...
};
```

## 📊 Statistics

The tool provides real-time statistics:
- Number of authors formatted
- Number of journals abbreviated
- Number of duplicates removed

## 🤝 Contributing

Contributions are welcome! Please feel free to:

1. **Add more journal abbreviations** - Submit a PR with additional journals
2. **Report bugs** - Open an issue if you find any problems
3. **Suggest features** - Let us know what would make this tool more useful

### How to Contribute

1. Fork this repository
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add some amazing feature'`)
5. Push to the branch (`git push origin feature/amazing-feature`)
6. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

Created to solve a common problem faced by researchers when formatting bibliographies for academic papers.

## 📧 Contact

If you have any questions or suggestions, please open an issue on GitHub.

---

⭐ If you find this tool useful, please consider giving it a star on GitHub!
