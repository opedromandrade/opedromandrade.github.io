+++
date = '2026-09-27T21:28:44+01:00'
draft = true
title = 'Md to Pdf - Converting simple Markdown to Styled pdf'
+++

{{< figure src="md2pdf.svg" alt="md2pdf" >}}


It wasn't an easy task to properly export my first **bland** CV to PDF. 📄 Markdown, as [said previously](https://opedromandrade.github.io/posts/refining-narrative/), is super simple, clear, and intentional. But its output in terms of style can be lacking, to say the least. 🎨

So, [Pandoc](https://pandoc.org/) can do something about it—if—and it’s a big if—you have a good styling `.css` file. 💅

The approach is quite simple:

1. **Check the MD content** (let's call it `resume.md`): Once you're happy with the content, move on to the next phase. Always ask multiple trusted friends, your partner, or whoever to take a look at the information in `resume.md`. Read it and rework it _ad nauseam_.
2. **Get your hands on a good, or at least better, stylesheet.** I found this randomly when I searched for MD-to-PDF resume templates, and I was given the answer of using a CSS file. 🎭
3. **Testing and improving CSS:** Pretty self-explanatory. 🛠️

Now, the process to produce a fine, simple CSS-styled `resume.pdf` is quite easy:

1. **Have all files in one folder.**
    ```code
   📁 resume/
    ├── 📝 resume.md
    └── 🎨 resume.css
	```
    
2. **Run the command** that will output your MD into a simple `.html` file:
    
    ```powershell
	pandoc .\resume.md --from=gfm --standalone --css=".\resume.css" -o .\resume.html
    ```
    
3. **Open your HTML** in your default browser of choice:

    ```powershell
	start .\resume.html
	```

4. Proceed to `Ctrl+P` to print the HTML to PDF. 🖨️
    

And that's it for the most part. Simple, right? You have a really custom-made resume in PDF. Since it's Markdown, you can also use it to host online. 🌐

Now, I've found out that printing/exporting from HTML to PDF removes the hyperlinks on the resume (though they show on the created and previewed `.html`), nor will it create PDF bookmarks (for those overachievers) that allow one to navigate the PDF. 🔗

So, after searching online, here came AI 🤖 to the rescue.

After much trial and error, I got my final answer: to achieve bookmarks and keep links, one needs to use a Chromium-based browser, like Chrome or Edge (I chose Edge since it shipped by default on Windows machines). It **cannot** be Firefox, sadly, due to its processing limitations regarding PDF/HTML rendering. 🦊

Here are the steps to get PDF bookmarks and keep hyperlinks:

1. Run the command that will output your MD into a simple `.html` file:

    ```powershell
	pandoc .\resume.md --from=gfm --standalone --css=".\resume.css" -o .\resume.html
	```
    
2. After having your Chromium-based browser installed, use the following (on a Windows machine):
    
    ```powershell
	& "C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --headless --disable-gpu --no-pdf-header-footer --generate-pdf-document-outline --run-all-compositor-stages-before-draw --print-to-pdf="$PWD\resume.pdf" "file:///$PWD\resume.html"
	```
    
It took me ages to get this working, but it does. And you don't need to install anything else than Pandoc, or at the limit, have a second browser.

But it works. Simple and effective. No extensions, nada. 🚀