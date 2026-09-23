# SVG → Android Vector Drawable Converter

A modern, browser-based tool for converting **SVG files into Android Vector Drawable XML**.

Convert SVG icons and illustrations into Android-compatible `vector` XML directly in your browser — **no backend, no uploads, and no installation required**.

## ✨ Features

* 🚀 **100% client-side** — your SVG files stay in your browser
* 🎨 Converts SVG colors to Android-compatible colors
* 🖌️ Supports inherited SVG properties
* 🌈 Supports common CSS color formats
* 🔄 Supports `currentColor`
* 📐 Supports SVG `viewBox`
* 🧩 Supports multiple SVG shapes
* 🛠️ Converts common SVG shapes into Android `pathData`
* 📦 Generates Android Vector Drawable XML
* ⚡ Live conversion
* 👀 SVG preview
* 📋 Copy generated XML
* 💾 Download generated XML
* 🖱️ Drag & drop SVG files
* 📝 Paste SVG source directly
* ⚠️ Detects unsupported SVG features and displays warnings

## 🧩 Supported SVG Elements

The converter currently supports common vector elements such as:

```text
<path>
<rect>
<circle>
<ellipse>
<line>
<polygon>
<polyline>
<g>
```

### SVG styling

The converter handles properties such as:

```xml
fill
stroke
stroke-width
stroke-linecap
stroke-linejoin
fill-opacity
stroke-opacity
opacity
fill-rule
color
style
```

It also supports **inherited SVG styles**.

For example:

```xml
<svg
    color="currentColor"
    fill="none"
    stroke="currentColor"
    stroke-width="1.5"
    stroke-linecap="round"
    stroke-linejoin="round">

    <path d="M3 12..." />

</svg>
```

The styles defined on `<svg>` are automatically applied to the child `<path>` elements.

---

## 🎨 `currentColor` Support

SVG icons commonly use:

```xml
stroke="currentColor"
```

The converter resolves `currentColor` and generates an Android-compatible color.

For example:

```xml
<path
    android:fillColor="#00000000"
    android:strokeColor="#FF000000"
    android:strokeWidth="1.5"
    android:strokeLineCap="round"
    android:strokeLineJoin="round"
    android:pathData="..." />
```

---

## 📱 Android Output

The generated output follows the Android Vector Drawable format:

```xml
<vector
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="24dp"
    android:height="24dp"
    android:viewportWidth="24"
    android:viewportHeight="24">

    <path
        android:fillColor="#00000000"
        android:strokeColor="#FF000000"
        android:strokeWidth="1.5"
        android:strokeLineCap="round"
        android:strokeLineJoin="round"
        android:pathData="M3.49902,14.9656..." />

</vector>
```

You can place the generated file inside:

```text
app/src/main/res/drawable/
```

For example:

```text
ic_clock.xml
```

Then use it in Android:

```xml
<ImageView
    android:layout_width="24dp"
    android:layout_height="24dp"
    android:src="@drawable/ic_clock" />
```

---

## 🚀 Getting Started

### Option 1 — Use the website

Open the HTML file in your browser.

No installation is required.

### Option 2 — Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/svg-to-android-vector.git
cd svg-to-android-vector
```

Then open:

```text
svg-to-android-vector-forge.html
```

in your browser.

---

## 🖥️ Usage

### 1. Upload an SVG

Drag and drop your `.svg` file into the converter.

Or click:

```text
Choose SVG
```

### 2. Paste SVG

You can also paste SVG source code directly into the editor.

### 3. Convert

The converter automatically generates Android Vector Drawable XML.

### 4. Copy or Download

Use:

```text
Copy XML
```

or:

```text
Download XML
```

to save the result.

---

## ⚠️ SVG Compatibility

SVG is a much larger format than Android Vector Drawable.

Some SVG features cannot be represented exactly by Android Vector Drawable.

The converter therefore uses a **best-effort conversion approach** and warns about potentially unsupported features.

### Supported / partially supported

| Feature           | Support |
| ----------------- | ------- |
| `path`            | ✅       |
| `rect`            | ✅       |
| `circle`          | ✅       |
| `ellipse`         | ✅       |
| `line`            | ✅       |
| `polygon`         | ✅       |
| `polyline`        | ✅       |
| Nested groups     | ✅       |
| `fill`            | ✅       |
| `stroke`          | ✅       |
| `currentColor`    | ✅       |
| SVG inheritance   | ✅       |
| Opacity           | ✅       |
| Basic transforms  | ⚠️      |
| Gradients         | ⚠️      |
| `clipPath`        | ⚠️      |
| `<use>`           | ⚠️      |
| Filters           | ❌       |
| Masks             | ❌       |
| Raster images     | ❌       |
| `<text>`          | ❌       |
| `<foreignObject>` | ❌       |

The converter displays warnings when it detects features that may require manual adjustment.

---

## 🔒 Privacy

This project runs entirely in the browser.

Your SVG files are **not uploaded to a server**.

The conversion happens locally using JavaScript.

```text
SVG file
   ↓
Browser
   ↓
SVG Parser
   ↓
Converter
   ↓
Android Vector XML
```

---

## 🛠️ Technologies

The project is intentionally lightweight.

Built with:

* HTML5
* CSS3
* JavaScript
* DOMParser
* SVG
* Android Vector Drawable XML

No backend is required.

No database is required.

No framework is required.

---

## 📁 Project Structure

```text
svg-to-android-vector/
│
├── svg-to-android-vector-forge.html
└── README.md
```

The project can therefore be hosted easily using:

* GitHub Pages
* Netlify
* Vercel
* Cloudflare Pages
* Any static web server

---

## 🌐 GitHub Pages

You can publish the converter using GitHub Pages.

After pushing the project to GitHub:

```text
Settings
   ↓
Pages
   ↓
Deploy from branch
   ↓
main
   ↓
/ root
```

GitHub will generate a public URL for the converter.

---

## 🧪 Example

Input:

```xml
<svg
    xmlns="http://www.w3.org/2000/svg"
    viewBox="0 0 24 24"
    color="currentColor"
    fill="none"
    stroke="currentColor"
    stroke-width="1.5"
    stroke-linecap="round"
    stroke-linejoin="round">

    <path d="M3.49902 14.9656C4.72475 18.4791..." />
    <path d="M11.999 7V12L14.999 14" />
    <path d="M7.49751 8.74363..." />

</svg>
```

Output:

```xml
<vector
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="24dp"
    android:height="24dp"
    android:viewportWidth="24"
    android:viewportHeight="24">

    <path
        android:fillColor="#00000000"
        android:strokeColor="#FF000000"
        android:strokeWidth="1.5"
        android:strokeLineCap="round"
        android:strokeLineJoin="round"
        android:pathData="M3.49902..." />

    <path
        android:fillColor="#00000000"
        android:strokeColor="#FF000000"
        android:strokeWidth="1.5"
        android:strokeLineCap="round"
        android:strokeLineJoin="round"
        android:pathData="M11.999,7V12L14.999,14" />

</vector>
```

---

## 🎯 Why This Project?

Android developers often download icons from websites that provide SVG files.

However, Android projects frequently need:

```text
SVG
↓
Vector Drawable XML
```

This project makes that conversion quick and convenient without requiring external software.

---

## 🔮 Future Improvements

Possible future improvements include:

* [ ] Full CSS selector support
* [ ] Better `<use>` / `<symbol>` handling
* [ ] Advanced transform conversion
* [ ] Gradient → Android AAPT gradient conversion
* [ ] Better `clipPath` support
* [ ] SVG path normalization
* [ ] SVG optimization
* [ ] Batch SVG conversion
* [ ] Multiple file upload
* [ ] Android Studio preview
* [ ] Dark/light theme
* [ ] Custom `currentColor` picker
* [ ] XML formatting options
* [ ] Copy drawable resource name automatically
* [ ] PWA support
* [ ] Offline installation

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a new branch

```bash
git checkout -b feature/my-feature
```

3. Make your changes
4. Commit them

```bash
git commit -m "Add my feature"
```

5. Push the branch

```bash
git push origin feature/my-feature
```

6. Open a Pull Request

---

## 📄 License

This project is open source.

Add your preferred license to the repository, for example:

```text
MIT License
```

---

## ⭐ Support

If this project is useful to you, consider giving the repository a ⭐ on GitHub.

Issues, feature requests, and pull requests are welcome.

---

**SVG → Android Vector Drawable, directly in your browser. 🚀**
