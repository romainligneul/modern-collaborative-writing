

Academics spend a lot of their time writing papers, proposals, reports and other documents. Many are happy with traditional workflows combining a commercial word processors (e.g. Word) with a bibliography software such as Zotero or Mendeley. 
But academic writing is often collaborative and a lot of researchers actually use Google Docs (with some plugins) to do so.
The problem is that Google Docs offer little guarantees when it comes to privacy, and they are rather limited when it comes to templating, writing equations or simply using it offline. Moreover, Google Docs still constitute one more interface in the daily life of academics (and not the best). By reading step by step the document hereafter, you may set up an alternative writing workflow using Markdown, which will allow you (amongst others, to write publication-ready documents from your preferred code editor).

<!--To start, we learn how to write down a :blush: smiley. Top priority-->
This tutorial is obviously more complex than just logging in Google and opening a Google Doc, but it guides and explains you each step and it might still be of interest for those who want a more modern and efficient, privacy-conscious workflow, enabling real-time collaborative writing. 
Carefully implemented, this pipeline might be particularly useful for researchers who wish to move away from Google Docs for whatever reason without losing functionality (in fact, they will gain functionality). Let's not forget that careers and labs last for decades and that good workflows can save you from weeks or months of (cumulative) suboptimal procedures :blush:. 

<!--Here, the markup for bold fonts-->
Last but not least, this pipeline relies entirely on **free, open-source** software! 

The tutorial itself is divided in several parts: introduction, software installation and configuration, test and comments.

<!--Here you see how to make an h2 title :) other title sizes are # ## ### #### ##### ######. By the way, you might have noticed that Markdown comments are totally ignored: you won't even see empty lines in place of them in the rendered version. How convenient to exchange diverse feedback, ideas and references with colleagues, without cluttering the output!-->
## Introduction

<!--Here, you can see how an external URL can be linked in a Markdown file. In between the brackets [], you find the text which will be rendered and in parentheses () you see the actual URL that will be opened after clicking -->
Markdown is at the heart of our approach. It is *the* markup language that allows extremely quick and reproducible writing. Markdown is mostly defined by its syntax, where different symbols activate different functions. For example, the symbol # can be used to create titles of different size. # Will produce a huge title, whereas #### will produce a much smaller title. Symbols like \*, \_ , \~ or \^ allow to write bold, italics, subscript or superscript characters. Messaging apps like What's App also use some of these syntactic shortcuts, but Markdown goes much farther and allows to create citations, URL links, tables, lists, figures, etc using a similar approach. The [Markdown website](https://www.markdownguide.org/) is a good place to get started. Note that Github and many other Web development tools apps use Markdown routinely. Furthermore, Markdown allows formatting using in line HTML (very potent) and templating like conventional word processors (i.e. choice of fonts, font style, color, etc.) using a .css style file.

<!--Here, you can see how easy it is to generate a numbered list in Markdown! The leading 1. 2. etc are sufficient! -->
However, as efficient as it can be, Markdown alone is not sufficient for academic writing.
1. First of all, we need an editor to create and write .md files. For this, we will use [Visual Code](https://code.visualstudio.com/) for its stability and its versatility (thanks to its amazing set of extensions).
2. Second, we need to install and configure some tool to manage citations and bibliographies. For this, we will use [Zotero](https://www.zotero.org/) which has also an excellent support and great extensions.
3. Third, we need to install and configure a tool to export .md Markdown files to other formats such as .pdf, .dox or event .html files. For this, we will use the universal document converter [Pandoc](https://pandoc.org/).
4. Fourth, we will need to set up a pipeline to collaborate efficiently using Github and the LiveShare extension of Visual Code in order to allow real-time collaborative writing (the same approach also allows real-time collaborative coding). It is very well maintained by Microsoft and it is free.
5. Along the way, we may install other optional software such as [MikTex](https://miktex.org/) to facilitate the writing of equation and export to PDF, or [Mermaid](https://mermaid.js.org/) to write down graphs in Markdown.

<!--Here you can see an example of strong italic font (in between the *** *** symbols)=-->
If you open the current README.md file using an IDE (like Visual Code), you'll find a lot of comments that explain how Markdown was used to write it. You'll find examples for most markup techniques. If you are reading this document document from a browser, all this comments are hidden. If you're already curious to check out the simplicity and neatness of raw Markdown files you can look [here](https://raw.githubusercontent.com/romainligneul/modern-collaborative-writing/main/README.md) (note that the syntax ext will look ***much better*** and clearer if you create an empty example.md file in VS code and that you copy paste the raw Markdown into it!).

## Installation and configuration

Please install Visual Code, Zotero and Pandoc using the links provided above. If you want to export directly to PDF and/or write nice equations, install MikTex as well.
In what follow, I point towards the relevant set of extensions for each of these essential tools. Many other extensions exist, especially for Visual Code, but the focus here is really on developing an academic writing workflow. If you discover Visual Code with this tutorial, just keep in mind that it is a **very** complete [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment) which can do much more for scientists, developers and engineers.

### Set Visual Code

<!--Here an example of unordered list with simple hyphens, and an <a> element that is used as an anchor (method described later in these comments)-->
When working with Visual Code, you'll always have to open a base folder first (File menu). Think of your base folder as a unit that may be uploaded online (e.g. on Github or else) and shared with collaborators. Try to define these base folders as folders that represent autonomous projects (e.g. a research paper, an analysis pipeline, a website, etc.).
Anyway, at this stage, what matter is more to install the adequate extensions for VS code (just click the install button and continue). Click on the following links to install each extension (the order does not matter).
- [Markdown Lint](https://marketplace.visualstudio.com/items?itemName=ChrisChinchilla.vscode-pandoc): a nice tool to check the validity and quality of your Markdown syntax.
- [VScode-pandoc](https://marketplace.visualstudio.com/items?itemName=DougFinke.vscode-pandoc)<a name="VSpandocItem">:</a> a useful extension to automatize the exportation of documents written in Pandoc.
- [Citation Picker for Zotero](https://marketplace.visualstudio.com/items?itemName=mblode.zotero): a small utility to grab references from Zotero and include them in your Markdown files, exactly as you would do in Word or Google Docs.
- (for real time collaborative writing) [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare): a very fancing real-time collaborating app for Visual Code. Note that, unlike collaboration based on Google Docs, Live Share can be set to work **exclusively** with direct connection (no data or text transits through the cloud, Internet is only required to log into the service). Live Share is therefore compatible with the privacy demands that some of us might worry about.

Note that this tutorial proposes to use Visual Code as it really gives full functionality, but Markdown/Pandoc can also be used with other editors (e.g. Matlab IDE, Spyder, PyCharm, Notepad++, etc.). In this case, exportation (we'll say more about this step in below) would only be done from the command line and another widget (which may not yet exist) would be necessarily to get the easiest access to Zotero citation.

### Set up Zotero

Zotero only needs one extension:
[**Better Bibtext for Zotero**](https://retorque.re/zotero-better-bibtex/) to help keep its librairy updated and available for our Visual Studio / Markdown duo. The installation process is a bit unusual as you need to:
  -  Download an .xpi file from [here](https://github.com/retorquere/zotero-better-bibtex/releases/) (you may need to right click and "save the link target") and install it in Zotero (see below)
  -  Download a .lua file (possibly still available [here](https://retorque.re/zotero-better-bibtex/exporting/zotero.lua)) as recommended in this [tutorial](https://retorque.re/zotero-better-bibtex/exporting/pandoc/) (which is not very clear, but fortunately, no need to read it for now). Just place it somewhere simple on your computer (e.g. at `C://whateverfoldername/zotero.lua`). Avoid to spaces in the path as spaces make path more annoying in general (e.g.don't put it in G://My Drive/..). 

Make sure to complete the six steps below:  
1. Download the latest version of ZoteroBetterBibTeX (the .xpi file).
2. Install the .xpi file in Zotero (Tools >> Add-ons >> 'Cogwheel button' >> Install add-on from file).
3. In Zotero preferences, set the Better BibTeX citation key format to [auth:lower][year].
4. Select all your references in Zotero, right-click and make a BetterBibTeX refresh (“Refresh BibTeX key”).
5. Create an auto-updating library of your citation keys: Zotero >> File >> Export Library. Use "Better BibLaTeX" format. Tick “Keep updated”. Remember the folder where you put the library. Again, avoid having spaces in your path. For example, you might name and place the file so as to get it at `C://whateverfoldername/zoteroMyLibrairy.bib`
6. In Zotero, set Preferences >> Better BibTeX >> Automatic export >> Automatic export: On change. This keeps the .bib file updated with any new references that you add in Zotero.

Essentially, what we've done here is allow Zotero to communicate with Visual Code and Markdown. We have also prepared the process of exporting citations and creating nice bibliographies. 

### Set up Pandoc
<!-- In the following lines, we describe how to create a text anchor which allows to navigate directly to a specific area of the document (in this case the VS-code pandoc paragraph of a prior section (check the <a=name="XXitem">: </a> syntax there). Note that the automatic navigation does not work within VScode itself but it does everywhere else. 
We also see that we can use exactly the main technique to navigate to one of your title markup. To do so, we just need to write down the title in small caps and to replace spaces by hyphems. Simple! -->
For Pandoc, the process is really straightforward. Once you've installed it, the only thing we need to do is to tell our **VS-code pandoc** extension (if you forgot its role, check again [Set up Visual Code](#VSpandocItem)) how to generate citations/bibliography when exporting to Word (similarly process are described at the end of this tutorial for exporting to other format). 
***Note that this extension is not required if you plan to export your document using the command line only*** (in this case just go directly to the [corresponding subsection](#document-generation-using-the-command-line)). 

<!--Here you can see how to render inline code with Markdown, in between the backquote symbol ` (don't confuse it with the frontquote ´ !)-->
So, let's do as follow: 
1. Open VScode
2. Go to File --> Settings (or click the wheel at the bottom left!) and type *pandoc* in the search bar at the top.  
3. Scroll to the line Docx Opt String and copy-paste `--lua-filter=C://whateverfoldername/zotero.lua --metadata=zotero_scannable_cite:false --metadata=zotero_client:zotero --metadata=zotero_csl_style:apa --metadata=zotero_transferable:true` in it.

<!--Here, you can see how to apply color in Markdown. In my view, color management is only of the only weakness of Markdown, in the sense that it requires a lot of HTML characters for result that is simpler to reach using Word. But colorful texts are annoying anyway (plus there are ways of defining color themes in templates, which reduces quite a lot the amount of characters required!)-->
Note that `--lua-filter=C://whateverfoldername/zotero.lua` should be <span style="color:red">consistent</span> with the path you've actually chosen (you probably did not name the folder "whateverfoldername", so adjust accordingly! :sweat_smile:)
Essentially, these launch parameters will allow you to export **modifiable** citations and bibliography from Zotero to Word passing by Markdown. Note also that ```--metadata=zotero_csl_style:apa``` defines your default citation style. You will have 3 ways of changing style: (i) by changing this specific command (to ```--metadata=zotero_csl_style:nature``` for example), (ii) by using command line exportation, or (iii) by changing it after exporting to Word for the final touches (just before submitting to a journal or an Rxiv platform, for example).

At this point, you are 95% set to write in Markdown by yourself and generate clean documents. You have two main ways to do so. Let's assume you are writing a file named *example.md*

Just for the sake of this tutorial, let's create this example file and paste the following Markdown inside it: 

```
## Just an example

This is just an example document with one single reference [@anyauthor2021] and a super simple bibliography.

<div id="refs"></div>

```

If you don't know a specific citation key (you can open the .bib file to see how your citation keys are formatted), you can press Alt+Maj+Z to open a small Zotero window that will allow you to retrieve your references "as usual" (obviously, you must have Zotero running and some references in it!).

#### Document generation using the VScode-pandoc extension

<!--Here we see how a block of computer code can be create in between triple backquotes ```-->
1. In Visual Code, open the folder containing *example.md*.
2. Copy paste the following at the very top of the file:
```
---
bibliography: C://whateverfoldername/zoteroMyLibrairy.bib
title: 'Collaborative academic writing tutorial'
...
```
3. Click inside the *example.md* (in the main window) and do Ctrl+K and then press P. You will see a the top a drop down menu asking you in which format you want to save your document. Choose Word document (.docx). If you have Word installed on your computer you should see a Word window opening with a bibliography
Again, be <span style="color:red">consistent</span> with the actual path at which your exported .bib file is located.

#### Document generation using the command line

Open a command line / terminal, `cd` to the directory containing *example.md* and type `pandoc example.md --bibliography=C://whateverfoldername/zoteroMyLibrairy.bib --citeproc -o example.docx`

By exporting in this way, you won't have a modifiable Zotero bibliography. But if you **really** love the command line, you can type:
`pandoc example.md --bibliographic=C://whateverfoldername/zoteroMyLibrairy.bib --lua-filter=C://whateverfoldername/zotero.lua --metadata=zotero_scannable_cite:false --metadata=zotero_client:zotero --metadata=zotero_csl_style:apa --metadata=zotero_transferable:true -o example.docx`

This second command should create exactly the same document as that generated using the configured VScode-pandoc extension. If you are running into problems, you might have more luck by cloning the git repository of this tutorial (see here)


## Set up Github and Live Share for collaborative writing

At this point, you know almost everything you need for single-author writing. At the very end of this tutorial, we'll see how to export to PDF and we'll discuss a few more cool functionalities of Markdown but the priority (and the promess) of this tutorial is to set up a **real-time collaborative writing** solution. 

There are a bunch of ways to organize a collaborative writing workflow. Here, we'll stick to a relatively simple approach using Github for storing our document(s) and LiveShare to allow two persons to collaborate in real time on the same document. The exact same approach would work with Github alternatives such as Gitlab, Bitbucket, etc. However, a cool feature is that you can log into Live Share using your Github credentials. 

Later on, we'll see how to go even further and see how to maintain a shared collection of PDFs across different authors.

#### Github

1. If you don't have Github, create an account. 
2. Install the [Github CLI](https://cli.github.com/) utility that will allow you to connect your command line to your Github repository.
3. Restart your terminal (or Visual Code), reopen it, and type `gh auth login`. Choose Github.com, HTTPS, Login with a web browser (or use an auth token if you prefer)
4. CD to the directory where your *example.md* file is located and type `git init` in the command line. This preconfigures the folder as a Git repository.
5. In Github, create a new repository. For example, name it "example-collaborative-writing". If you create a public repository, everyone on the web will be able to see the repository and its content. If you create a private repository, only the Github contact that you will manually add to the repository will be able to see it and its content. Most often, you'll want to create private repositories to work with specific colleagues.
6. Back to your command line, type `git remote add origin https://github.com/yourGithubUsername/example-collaborative-writing.git` `git add .`, `git commit -m "first commit"`, `git branch -M main`, `git push -u origin main`. These steps are only needed for the creation of a new repository, then things will be much simpler. Refresh the web page of the newly create Github repository. You should see your *example.md* file appearing!

Now, each time that you'll want to start working on the file(s) contained in the folder/repository, you'll have to type `git pull` in the command line (make sure that our command line points to the correct folder, if not, `cd` to it), make your modification and then type: `git add .`, `git commit -m "any message"`, `git push` to upload your changes. You may even speed up this process further by using [this trick](#speed-up-the-saving-process-with-git).

#### Live Share using a simple connection

To use Live Share in Visual Code, there is almost nothing to do. Just click on the Live Share icon in the sidebar (it's a curved arrow with a dot right below). Click the "Share" button: this will automatically add a *sharing link* to your clipboard that you can copy-paste and send it to anyone (through any messenging app or email). Those who receive the link can join the collaborative writing session by clicking the "Join" button and copy-pasting the link you've sent. Any change made to the opened document by your collaborator(s) is saved on *your* version of the file.

The only downside of this approach is that, when you disconnect from the session, your collaborator will also be disconnected. So, make sure to run `git add .`, `git commit -m "any message"`, `git push` before disconnecting. If you do so, your collaborator(s) will be able to keep working on the documents by running a simple `git pull` command (they might first need to run `git clone https://github.com/yourGithubUsername/example-collaborative-writing.git` to get the repository on their own computer, if they did not do it yet).

Another downside is that this approach does not solve the problem of shared Zotero bibliographies. While your collaborator will be able to add citation keys in the document, you'll need to have these keys in your own .bib file (i.e., this file arbitrarily named `zoteroMyLibrairy.bib` above) to be able to include them in the generated bibliography. To go beyond this limitation (that also exists using a Google Docs workflow), you'll need either to pay Zotero to set up Group Librairies or use your own (very modest) webserver. If you are a researcher, there are chances that your institution can provide you with a free webserver. Other, you can get one from a provider like [Vultr](vultr.com) or else.

#### Live Share using a webserver and a shared collection hack

If someone (you, your PI, your IT, who knows) run VScode on a remote server in a persistent fashion, you will be able to log in at any time into a persistent LiveShare session.
Here, I won't cover the set up of a simple remote server, but many excellent tutorials are available for [Vultr](), [Google Cloud]() and many others. If you're team is not too big and if the only use of the server is for collaborative writing, you should be able to use a free or cheap plan at any operator.

##### Steps to launch VScode remotely (only one collaborator should go through these steps: e.g. the PI)
1. Assuming your remote server is Ubuntu-based, that it is running and that you have its command line opened in front of you, you need to install VS code by executing the following lines (you may embed them in a bash script)
`sudo apt-get install wget gpg`
`wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg`
`sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg`
`sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'`
`rm -f packages.microsoft.gpg`
`sudo apt install apt-transport-https`
`sudo apt update`
`sudo apt install code # or code-insiders`
If you have a problem, try to follow these [instructions](https://code.visualstudio.com/docs/setup/linux) ; maybe some URLs of package names have been changed since I wrote this tutorial.

2. Then, you'll have to install the command line interface (CLI) of Visual Code
`curl -Lk 'https://code.visualstudio.com/sha/download?build=stable&os=cli-alpine-x64' --output vscode_cli.tar.gz`
`tar -xf vscode_cli.tar.gz`

3. Finally, you'll just need to launch VScode with the "tunnel" option:
`.\code tunnel`

4. You'll be asked a few question (such as giving your tunnel a name) and then you'll be offered to visit the URL of your tunnelled instance. Click on the link provided. It should open a browser window in your local computer. If it does not, copy the link and paste it in your browser.  **Do not close** the terminal.

5. You'll see a VScode environment in your browser that give you full access to your VScode instance as it is running in the server. The only thing we need to do here is to install the LiveShare Extension for this remote instance of VScode (as we did earlier in this tutorial), open a folder, create a LiveShare session (LiveShare icon --> Share button) and get the link.

##### Steps to join a VScode live session

Joining the remote VScode session is extremely easy. You just have to use the link provided by the administrator or the session (i.e. the person who set it up using the instructions of the subsection above).

## Additional tips

#### Speed up the saving process with Git

You can follow the instructions of [this tutorial](https://medium.com/@asciibi.dev/how-to-add-commit-and-push-to-git-using-one-command-on-windows-25d756f444b7) to create a little push.bat file and export it to the git repository.
The repository of this tutorial already contains a gitpush.bat file, so feel free to use it (add it to your global OS path for use from any folder) by typing `gitpush "any message"` from the command line.
This is exactly equivalent to writing: `git add .`, `git commit -m "any message"`, `git push`

#### How to manage 