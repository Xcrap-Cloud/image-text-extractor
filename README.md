# 🕷️ Xcrap Image Text Extractor

**Xcrap Image Text Extractor** is a package of the Xcrap framework that abstracts the extraction of texts from images using the [node-tesseract-ocr](https://www.npmjs.com/package/node-tesseract-ocr) library.

## 📦 Installation

There are no secrets to installing it, just use your preferred dependency manager. Here is an example using NPM:

```cmd
npm i @xcrap/image-text-extractor
```

## 🚀 Usage

**Xcrap Image Text Extractor** provides an *async extractor* that can be used in an HTML parsing model just like any extractor:

```ts
import { extractImageText } from "@xcrap/image-text-extractor"
import { HtmlParsingModel } from "@xcrap/parser"

const parsingModel = new HtmlParsingModel({
	imageTexts: {
		query: "img",
		multiple: true,
		extractor: extractImageText({ lang: "eng" })
	}
})
```

If you want to transform the `src` of the images to resolve relative paths or something like that, pass the `transformSrc` option in the options like this:

```ts
const parsingModel = new HtmlParsingModel({ 
    imageTexts: {
        query: "img",
        multiple: true,
        extractor: extractImageText({
            lang: "eng",
            transformSrc: (originalSrc) => {...}
        })
    }
})
```

> Check out more options at [node-tesseract-ocr](https://www.npmjs.com/package/node-tesseract-ocr).

## 🤝 Contributing

- Want to contribute? Follow these steps:
- Fork the repository.
- Create a new branch (git checkout -b feature-new).
- Commit your changes (git commit -m 'Add new feature').
- Push to the branch (git push origin feature-new).
- Open a Pull Request.

## 📝 License

This project is licensed under the MIT License.