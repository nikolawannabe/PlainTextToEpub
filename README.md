> Q. What is plain text?

A.  Plain text is a collection of letters, grammatical markers (such as “,./;’[]\”) , and whitespace.  This gets complicated when we ask “What is a letter?” because while English has a simple collection of letters (a-zA-Z), many worldwide languages don’t.  These letters, grammatical markers, and whitespace are each assigned a unique number, and then these numbers are written down together in order to comprise a “file”.  Usually these string of numbers representing characters are saved with the extension (last few letters) of .txt.  An extension is really just a helper to the computer, so it knows what program it should try to open up the string of numbers with.  The program will then turn the string of numbers back into your recognizable letters, grammatical markers, and whitespace.

> Q. How is HTML Different?

A.  HTML allows authors to mark some parts of the plain text as having extra meaning, and allows you to specify what that meaning does and how it looks.  CSS can be used to specify the styling of certain elements that have been marked to have extra meaning.  HTML and CSS files are also stored as a string of numbers and written to your hard drive.  The extension of HTML files is usually “.html”.  When a program opens up an HTML file, it has two options.  It can try to “render” (draw) it as the reader might want, without the extra text used to tell how to draw it.  For example, you can open an HTML file in your computer’s browser, and just read it.   Another way of opening an HTML file is to look at the marked up text.  This is generally called a “source” view, because it is the “source” of what is drawn into your browser.  

> Q. What is the ePub format, and how does it relate to HTML?

A. An ePub is a collection of HTML files, any resources (like images or fonts), and styles, all zipped into a file with information about the order to display the chapters in.  The zip file is then given the extension “ePub”.  Most modern eBook formats use some form of compression to make the files smaller to reduce storage costs.  An ePub file can be opened by any software which knows how to unzip the file and render the html files in order.  Alternatively, anyone could unzip an ePub, open the chapters folder, and open the first chapter’s HTML file in any HTML renderer, like their favorite browser.

> Q. What is a Word document? 

A. There are multiple different kinds of Word documents since the format has changed over the years.  Old .doc files take your plain text and mark some parts of them as special using a set of rules (a language) created by Microsoft.  Newer .docx files use a strict (computer-controlled) form of HTML called XML to mark up your plain text.  Newer .docx files are also compressed (zipped) to take up less space, while older .doc files are uncompressed.   Word documents can be sent to the printer to be printed, which was typically how people interacted with Word documents outside of Word.  When Word wants to print, it converts its special format into a series of instructions that the printer knows how to handle (usually a special format called a postscript file), and then sends that to the printer.  These days, people interact with Word content in a few other ways as well:

Converting it into a PDF and sending that PDF to someone else, so that the document cannot be edited.
Converting it into HTML and putting it on the web for others to read.
Sending the Word doc to others, who open the .doc or .docx file in software that tries to understand the special language Microsoft created (like WordPerfect or LibreOffice).

> Q. How does Word interact with plain text and HTML? (And when and why do things go wrong?)

A.  Word has a set of rules built-in it that can convert its specially marked up text to other kinds of formats that it knows about.  Some parts of the word languages cannot convert easily to all parts of the XML language, because they were designed to control how the document looked when it was printed.  Not all formats are designed for printing, as some formats are designed only for reading on computer screens.

> Q. What is the Mobi format?

A. The mobi format is similar to the ePub format in that it takes HTML documents and resources (images, fonts, etc) and compresses them together into a single package.  However, the Mobi format has a specific way of compressing these files together that cannot be easily done with normal compression tools (like 7zip or Winzip) that people have on their system.  So Mobi files need to be constructed by a tool that knows how to do this construction.  

Mobi files are not actually read by modern Kindle readers, instead they are first converted to an AZW file.  

> Q. Why do PDFs look so weird on most eReaders?

A. PDF is very different from ePub and Mobi.  It does not use HTML.  Instead, a PDF is “rendered” (drawn) onto a page, which displays the content of the document.  This rendering (drawing) only happens once: when the PDF is created, so content that broke across the line when the PDF was created will always break exactly the same way.  

This is different from HTML, where the content is not rendered (drawn) until the screen shows it, and may be re-rendered if the screen changes size.  HTML can do this because it stores information about what the content is, and doesn’t tell the screen where every letter should go.  Instead, it relies on the rendering software inside the end user’s reader or browser to know what a title or paragraph should generally look like, and only specifies the difference between that default rendering and what the author wants.

> Q. What is the AZW format?

AZW is a more general format that Amazon has created for use primarily on their readers.  AZW was originally just a wrapper around mobi files, but now is much more complicated.  AZW files may contain an ePub inside of the book for Kindle readers that can read that format.  They also have a mobi inside the file for legacy readers that don’t support ePub.  (This doesn’t mean that you can give ePubs to Kindles, they will not recognize these files.)  AZW are also compressed formats and must be constructed with a special tool that know how to insert the files and metadata (information about the book), and it can’t be done by hand.

AZW also has a format for textbooks that is similar to PDF, because textbooks often have very complex layout requirements.  

> Q. What are other legacy formats, and when do they matter?

A. Many legacy formats such as lrf and pdb use HTML internally, and wrap the html with a mechanism to determine what order the chapters should be displayed in.  They often differ in their use or selection of compression algorithm.  Some formats, such as RTF, use a custom markup language.  Some formats store images inline, while others store them separately.  Because eReaders are expensive, when possible, it is best to provide a copy in each major format from the last ten years.  

> Q. What formats convert well to other formats, and why?

A.  Formats based in HTML can usually be converted without loss to other formats based in HTML.  So it is perfectly reasonable to convert your ePub to Mobi, or to AZW.  

Formats that pre-define how each character looks and where each line break is (like PDF) should not be converted to other formats that do not do this, because determining which line breaks can be ignored and which are required for the reader is not stored in the file.  Humans must manually correct these documents to look good, and this is an error-prone process which usually results in sub-standard files.  While there are some algorithms that attempt to do a better job of this process, it is unreliable and not recommended.

> Q.  What does a format validator like epubcheck do, and why would I care?

A.  HTML isn’t just a collection of text and markup.  The markup must occur in a specific structure that is considered valid.  For example, it is not valid to put text inside the body of an image with HTML, even though it would be physically possible to write that in an HTML file.  Validators such as epubcheck also verify that the zip isn’t corrupted, and that the resources requested in the html (like images) are in the file, and that the chapters specified in the table of contents are present.

These tools help to make sure that your book will look good on many reading devices.  Because each device may implement its reader in its own way, and deal with complexity slightly differently, it is important to verify that your file follows the required structure as closely as possible.

> Q.  How can I easily use Word to create better files for eReaders?

Unless you are only going to release your book in PDF, it is best to stick to the features of Word that match what is in available in HTML.  For example, do not use features like page numbering, page headers, and page footers, unless you plan to manually create an ePub file from your Word document and add those features by hand — which you probably don’t want to try!  When you are thinking about using a feature, try to see if that feature exists in your favorite browser.  If it doesn’t, it probably is not available in the eBook reader either, so don’t use it, or your book conversion will be made much more complex.

Use the semantic features of Word (such as paragraph, headers, and page break) to tell Word what you mean, rather than using manual styling to tell Word what you want the text to look like.  If you make text bigger manually in Word, that doesn’t tell the converting software why that text is important when it tries to turn your document into useful HTML that will look good on the user’s reader.  You want to give the conversion engine as much information as you can about why this text is different, not just that you want it to look different, so the reading software can determine what it should do with what you have given it.

You should probably turn off Word’s automatic helper tools.  It may generate special characters and markup that complicate the conversion.

Don’t assume that the reader’s screen will look similar to your screen.  It is best to use percentages to specify image widths instead of pixels or inches.  Usually, 95% for most image widths will make the most sense, because as long as your image has enough pixels, it will look good on small smartphone screens as well as desktop screens.  It is often good to pair a percentage width with a maximum width that is the width of your image, so it doesn’t get stretched on large screens.

Don’t assume that the reader’s screen will use the same color scheme as you may want to apply in Word.  Some devices are only black and white, and even among tablets, readers often prefer to reverse the text and use white text on a black background when reading at night.

Be consistent.  A book that uses fifty different styles of headings or paragraphs will look unprofessional to readers.

Simple is almost always better.  This may change in the future, but for now, it is better to try and simplify your text styling than to try and make something complicated work specially for each and every reader. Just focus on the text, and let the reader’s imagination do the rest!

> Q.  How can I use other tools to create better ePubs?  When should I bother?

For most fiction books, using other tools is not necessary, because Word provides what you need in terms of bold, italics, chapter headings, and simple images.  (I’m not saying Word is necessarily the best tool for writing books, but rather that if you use it now and write fiction, there’s probably no need for you to learn a new tool unless you really want to.) 

If you are making a more complicated book, such as poetry, cookbooks, children’s books, or travel guides, you may find that you need more fine-grained control of the html layout than Word is giving you.  In this case, there are many tools for creating ePubs such as Scrivener and Calibre’s eBook editor (which Sigil merged into).  These tools are WYSIWYG tools that only provide features that are available in HTML and ePubs, so they may be easier to use for books with complex layout.

> Q.  How does DRM work, and what does it do to the formats above?

DRM generally is applied to the string of numbers that represent all your content before or after they have been zipped.  It takes the numbers that represent letters, grammar, whitespace, and apply a bunch of math to turn them into very different numbers that can be reconstructed into your original numbers only if the correct key (string of numbers) is given.  When the reader has the right string of numbers, he can unshuffle the numbers and then use his reading software to read the book as usual.    

> Bonus: Q. What is an alternative markup language, and when might I want to use one?

You may notice that the book you are using does not have much complex formatting, and that you don’t feel the need to use any of the special features that Word offers.  In fact, most fiction books could be written in just plain text chapter files, with little lost!  For those who want to write in plain text, but still want to store very simple information in the plain text such as bold, italic, headers, and links, this is what Markdown is designed for.  Markdown can be easily converted later to other formats with more complex formatting such as Word documents and HTML with nothing lost.  Some authors may find that, particularly for the first draft, Markdown is less distracting than a full-fledged editor.
