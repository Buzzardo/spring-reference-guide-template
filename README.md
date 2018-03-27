# spring-reference-guide-template
A template for Spring reference guides, including a pom.xml file to build four different outputs, a collapsible table of contents in the HTML outputs, and a custom stylesheet.

## Included Resoures

This project includes the following resources:

- `pom.xml`: The Maven pom file that you can use to build your reference documentation. You probably want to modify it to be a child project to your software project. Also, you should change the names of the finished files (in the `maven-antrun-plugin`) to reflect the name of your Spring project.
- `/src/main/asciidoc`: A directory structure for your documentation source files.
- `index.adoc`: The Asciidoc file that becomes `index.html` for the single-file HTML output. You need to modify this file to include the chapters in your reference guide, and you probably want to create some variables that you can use in your document files.
- `index-multi-adoc`: The Asciidoc file that becomes `index.html` for the multi-file HTML output.You need to modify this file to link to the chapters in your reference guide, and you probably want to create some variables that you can use in your document files.
- `overview.adoc` - A starter Overview chapter that you can customize to suit your project.
- `writing-advice.adoc` - A stand-alone file that contains some basic advice for writing a reference guide. You can delete it once you have written a draft of your reference guide.
- `getting-started.adoc` - A starter Getting Started chapter that you can customize to suit your project.
- `docinfo.html`: Contains style coding for the collapsible table of contents that is implemented by Tocbot. You should not need to modify this file
- `docinfo-footer.html`: Contains JavaScript that makes the collapsible table of contents work - by using the Tocbot libary. You should not need to modify this file.
- `stylesheets`: A directory that contains the custom stylesheet used by Spring reference guides.
 - `spring.css`: The custom CSS file that controls the appearance of the HTML versions of the Spring reference guides.
- `tocbot-3.0.2`: The JavaScript library that provides the collapsible table of contents for the HTML versions of the Spring reference guides.

**NOTE:** You should modify the pom.xml file and the Asciidoc (\*.adoc) files, including adding more asciidoc files. The other files should not need to be modified.

## Rendering Notes

When you build with Maven, the pom.xml file renders four outputs:
- Epub: An Epub version 3 file that contains the entire reference guide.
- HTML: A collection of HTML files (one per chapter plus an `index.html` file).
- PDF: A PDF file that contains the entire reference guide.
- Single HTML: A single HTML file (named `index.html`) that contains the entire reference guide.

After you build, the raw output goes into `target/generated-docs`. The build process puts the output files in `target/contents/reference`. During that process, some of the output files get renamed. Again, you should change the pom.xml file to reflect the names of your Spring project. Search for `your-project` to find the places where you should add the name of your Spring project.
