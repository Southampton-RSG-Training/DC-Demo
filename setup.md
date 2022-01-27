
### Text Editor

A text editor is the piece of software you use to view and write code. If you
have a preferred text editor, please use it. Suggestions for text editors are,
Notepad++ (Windows), TextEdit (macOS), Gedit (GNU/Linux), GNU Nano, Vim.
Alternatively, there are IDE's (integrated developer environments) that have
more features specifically for coding such as VS Code; there are also IDEs
specific to languages will be listed in the appropriate section(s) below.

### Best Practices in Data Organisation Using Spreadsheets


#### Data
The data used in this lesson comes from a project observing a small mammal community in southern
Arizona, US. This is part of a project studying the effects of rodents and ants on the plant
community that has been running for almost 40 years. The rodents are sampled on a series of 24 plots,
with different experimental manipulations controlling which rodents are allowed to access which plots.
This is a real dataset that has been used in over 100 publications. It is published at [Ecological Archives](http://esapubs.org/archive/ecol/E090/118/) and can be found on [Portal Project Database](https://github.com/weecology/PortalData). This data is open and free to use for research purposes.

For the purposes of training, this data has been simplified a bit (you can still download the full dataset and work with it using exactly the same tools we will learn here). This simplified version of data is available from the [Portal Project Teaching Dataset](http://figshare.com/articles/Portal_Project_Teaching_Database/1314459). In this lesson, you will need to download the following five files from the [Portal Project Teaching Dataset](http://figshare.com/articles/Portal_Project_Teaching_Database/1314459):
-  [messy_survey_data.xls](/data/messy_survey_data.xls) - this is the main file we will work with. It includes messy survey data
(in Excel's `.xls` format) that you will clean during the lesson and use to learn some best practices in
data organisation.
- [surveys.csv](https://ndownloader.figshare.com/files/2292172) - the cleaned survey data
    Fields: `record_id`, `month`, `day`, `year`, `plot_id`, `species_id`, `sex`, `hindfoot_length`, `weight`
- [plots.csv](https://ndownloader.figshare.com/files/3299474) - clean information on plot number and type
    Fields: `plot_id`, `plot_type`
- [species.csv](https://ndownloader.figshare.com/files/3299483) - clean information on species codes and scientific names
    Fields: `species_id`, `genus`, `species`, `taxa`
- [combined.csv](https://ndownloader.figshare.com/files/10717186) - clean data from surveys, plots and species data
files combined into one clean file (a good example of what a clean data file should look like)
Fields: `record_id`, `month`, `day`, `year`, `plot_id`, `species_id`, `sex`, `hindfoot_length`, `weight`, `genus`,
`species`, `taxa`, `plot_type`

> ## For Interest Only: Portal Project Teaching Dataset
> [The Portal Project Teaching Database](http://figshare.com/articles/Portal_Project_Teaching_Database/1314459) is a simplified version of the
> [Portal Project Database](https://github.com/weecology/PortalData) designed for teaching. It provides a real world example of life-history, population, and ecological data, with sufficient complexity to teach many aspects of data analysis and management, but with many complexities removed to allow students to focus on the core ideas and skills being taught. The database is currently available in csv, json, and sqlite formats.
>
> The Portal Project Teaching Database's GitHub repository can be found at: [https://github.com/weecology/portal-teachingdb](https://github.com/weecology/portal-teachingdb),
> where suggested changes or additions to this dataset can be requested or contributed.
> This database is not designed for research as it intentionally removes some of the real-world complexities. The Python code used for converting the original database to this teaching version can be found in [create_portal_teach_dataset.py](https://github.com/weecology/portal-teachingdb/blob/master/create_portal_teaching_dataset.py).
>
> **CITATION:** Ernest, Morgan; Brown, James; Valone, Thomas; White, Ethan P. (2017): Portal Project Teaching Database. Figshare. [https://doi.org/10.6084/m9.figshare.1314459.v6](https://doi.org/10.6084/m9.figshare.1314459.v6)
{: .testimonial}

#### Software

To interact with spreadsheets, you can use various software - for example Microsoft Excel,
LibreOffice, Gnumeric, OpenOffice.org, Google Spreadsheets. Commands may differ a bit between programs,
but the general ideas for thinking about spreadsheets are the same.

For this lesson, if you do not have a spreadsheet program already, you can use a free and open source tool
[LibreOffice](https://www.libreoffice.org/download/libreoffice-fresh/)
as it can open Excel spreadsheets, which is the format of the data we will work with during the lesson
(also all examples used refer to Excel).

{% comment %}
##### Windows

- Download the Installer
  - Install LibreOffice by going to [the installation page](https://www.libreoffice.org/download/libreoffice-fresh/). The version for Windows should automatically be selected. Click Download Version X.X.X (whichever is the most recent version). You will go to a page that asks about a donation, but you do not need to make one. Your download should begin automatically.
- Install LibreOffice
- Once the installer is downloaded, double click on it and LibreOffice should install.

##### Mac OS X

- Download the Installer
  - Install LibreOffice by going to [the installation page](https://www.libreoffice.org/download/libreoffice-fresh/). The version for Mac should automatically be selected. Click Download Version X.X.X (whichever is the most recent version). You will go to a page that asks about a donation, but you do not need to make one. Your download should begin automatically.
- Install LibreOffice
- Once the installer is downloaded, double click on it and LibreOffice should install.

##### Linux

- Download the Installer
  - Install LibreOffice by going to [the installation page](https://www.libreoffice.org/download/libreoffice-fresh/). The version for Linux should automatically be selected. Click Download Version X.X.X (whichever is the most recent version). You will go to a page that asks about a donation, but you do not need to make one. Your download should begin automatically.
- Install LibreOffice
- Once the installer is downloaded, double click on it and LibreOffice should install.
{% endcomment %}

#### Now what?

{% if site.carpentry == "rsg" %}
    {% assign lessonlink = "spreadsheets-introduction" %}
{% else %}
    {% assign lessonlink = "https://southampton-rsg.github.io/spreadsheets-data-organisation-and-management/00-intro/index.html" %}
{% endif %}


Once you have downloaded the files and have a spreadsheet programme, you can [start the lesson]({{ lessonlink }}).

### Data Cleaning with OpenRefine


#### Data
The data used in this lesson comes from a project observing a small mammal community in southern
Arizona, US. This is part of a project studying the effects of rodents and ants on the plant
community that has been running for almost 40 years. The rodents are sampled on a series of 24 plots,
with different experimental manipulations controlling which rodents are allowed to access which plots.

The Portal Project Teaching Dataset is a real dataset that has been used in over 100 publications. We have simplified it
for the purposes of this lesson, but you can download the full dataset (see below for details) and work with it
using exactly the same tools we will learn here.

For this lesson, you will need to download the following file (remember where you downloaded the file!):
*  [portal_project_rodents.csv](data/portal_project_rodents.csv)

Data in some of the columns of the above file (e.g. `geolocation`, `locality`, `county`, `country`, `JSON`) are contrived for the purpose of the lessons and are in no way related to the original dataset.

> ## For Interest Only: Portal Project Teaching Dataset
> [The Portal Project Teaching Database](http://figshare.com/articles/Portal_Project_Teaching_Database/1314459) is a simplified version of the
> [Portal Project Database](https://github.com/weecology/PortalData) designed for teaching. It provides a real world example of life-history, population, and ecological data, with sufficient complexity to teach many aspects of data analysis and management, but with many complexities removed to allow students to focus on the core ideas and skills being taught. The database is currently available in csv, json, and sqlite formats.
>
> The Portal Project Teaching Database's GitHub repository can be found at: [https://github.com/weecology/portal-teachingdb](https://github.com/weecology/portal-teachingdb),
> where suggested changes or additions to this dataset can be requested or contributed.
> This database is not designed for research as it intentionally removes some of the real-world complexities. The Python code used for converting the original database to this teaching version can be found in [create_portal_teach_dataset.py](https://github.com/weecology/portal-teachingdb/blob/master/create_portal_teaching_dataset.py).
>
> **CITATION:** Ernest, Morgan; Brown, James; Valone, Thomas; White, Ethan P. (2017): Portal Project Teaching Database. Figshare. [https://doi.org/10.6084/m9.figshare.1314459.v6](https://doi.org/10.6084/m9.figshare.1314459.v6)
{: .testimonial}

#### Software

For this lesson you will need [OpenRefine](http://openrefine.org/) (formerly GoogleRefine) and a web browser.
Download the most recent version of [OpenRefine](http://openrefine.org/download.html) for your operating system,
then follow the instructions below.

[OpenRefine](http://openrefine.org/) is a Java program that runs locally on your machine (i.e. you are not accessing a remote service on the Internet). Most recent versions of
OpenRefine for Windows and Mac come with embedded Java, in which case you do not need a separate Java installation.

Once it is running on your machine, you access it via your browser at the address [http://localhost:3333](http://localhost:3333). No Internet connection is needed for this as the programme is running locally.

##### Windows
- If you have Internet Explorer (or Edge) set as your default web browser, check that you have Firefox or Chrome installed and set either of them as your default browser. OpenRefine runs in your default browser, but may not run correctly in Internet Explorer. You can check how to set your browser as default for [Google Chrome](https://support.google.com/chrome/answer/95417?co=GENIE.Platform%3DDesktop&hl=en-GB) or [Firefox](https://support.mozilla.org/en-US/kb/make-firefox-your-default-browser).
- Unzip the downloaded file into a directory by right-clicking and selecting `Extract...`. Name that directory something like OpenRefine.
- Locate `openrefine.exe` in the extracted folder and launch OpenRefine by double-clicking on it. This will launch a command prompt window first.
- Wait for OpenRefine to launch in your default Web browser, which is where you will interact with the program. If this does not happen, head to [http://localhost:3333](http://localhost:3333) in your Web browser of choice.

##### Mac

- Check that you have Firefox or Chrome browser installed and set as your default browser. You can check how to set your browser as default for [Google Chrome](https://support.google.com/chrome/answer/95417?co=GENIE.Platform%3DDesktop&hl=en-GB) or [Firefox](https://support.mozilla.org/en-US/kb/make-firefox-your-default-browser).
- Locate the downloaded `.dmg` file and Ctrl-click it. You may get the warning "macOS cannot verify the developer of “OpenRefine.app”. Are you sure you want to open it?" Click 'Yes'/'Open' to this.
- Drag `OpenRefine.app` into your Applications folder, and Ctrl-click to open it. You may get the warning "macOS cannot verify the developer of “OpenRefine.app”. Are you sure you want to open it?" Click 'Yes'/'Open' to this.
- Wait for OpenRefine to launch in your default Web browser, which is where you will interact with the program. If this does not happen, head to [http://localhost:3333](http://localhost:3333) in your Web browser of choice.

##### Linux

- This requires Java to be installed on your computer. If you do not already have it, download [OpenJDK Java](https://openjdk.java.net/).
- Check that you have Firefox or Chrome browser installed and set as your default browser. You can check how to set your browser as default for [Google Chrome](https://support.google.com/chrome/answer/95417?co=GENIE.Platform%3DDesktop&hl=en-GB) or [Firefox](https://support.mozilla.org/en-US/kb/make-firefox-your-default-browser).
- Unzip the downloaded file into a directory. Go to this directory from terminal and type ./refine to start.
- Wait for OpenRefine to launch in your default Web browser, which is where you will interact with the program. If this does not happen, head to [http://localhost:3333](http://localhost:3333) in your Web browser of choice.

#### Now what?

{% if site.carpentry == "rsg" %}
    {% assign lessonlink = "openrefine-data-cleaning-introduction" %}
{% else %}
    {% assign lessonlink = "https://southampton-rsg.github.io/openrefine-data-cleaning/00-getting-started/index.html" %}
{% endif %}

Once you've downloaded the file above, you can [start the lesson]({{ lessonlink }}).

### Automating Tasks with the Unix Shell

#### Shell Setup 

You need to download some files to follow this lesson. First, you need to open a terminal:

- **On Windows:** run "Git Bash", which you installed as part of the software prerequisites
- **On Mac OS X:** accessed by opening the “Terminal” application, which can be found in the “Utilities” folder which is in your “Applications” folder
- **On Linux:** this will depend on the Linux distribution you are running, but you should be able to find a "Terminal" application in your desktop's application menu

Once you've done this, a window should appear. Type the following into the prompt that appears (pressing enter/return after each line):

~~~
$ cd
$ git clone https://github.com/Southampton-RSG/shell-novice.git
~~~
{: .language-bash}

Alternatively, if you have SSH authentication with GitHub enabled (if you don't know what this means don't worry, it is covered in the Git SWC course if you want to know more!) you can use the following:

~~~
$ cd
$ git clone git@github.com:Southampton-RSG/swc-shell-novice.git
~~~
{: .language-bash}

This should download all the content for the lesson to a new directory.
Please let the instructors know if you run into any problems.

{% include links.md %}

### Version Control with git

#### Git Setup 

{% if site.carpentry == "rsg" %}
  {% assign slidelink = "slides/git-novice-lesson/index.html" %}
{% else %}
  {% assign slidelink = "../slides/index.html" %}
{% endif %}

[The slides to accompany this material can be found here.]({{ slidelink }})
Before we get started, we'll have to do a few things.

![Setup](fig/slides/setup.png){:width="20%"}

Later on in the session, we'll be demonstrating how to share work with collaborators using GitHub. You'll need to create an account there: [https://github.com/](https://github.com/).

As your GitHub user name will appear in the URLs of your projects there, it's best to use a short, clear version of your name if you can.

In addition we will need to set up SSH access to GitHub from your computer. This is how GitHub checks that you are who you say you are when you try to add things from your computer.

When we do this, we generate a pair of keys - one public, one private. We want to add the public key to GitHub, whilst the private one stays on our computer.

There are full guides here [https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent](Make an SSH Key) and [https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account](Add an SSH key).

However today we have simplified it like so:

First we need to create a variable to store your GitHub email. Copy this command, substituting the email you signed up to GitHub with for `your_github_email@example.com`:
~~~
$ my_gh_email=your_github_email@example.com
~~~
{: .language-bash}

Then we can run the following command to generate a key-pair and display the public half:
~~~
$ ssh-keygen -t ed25519 -C $my_gh_email; eval "$(ssh-agent -s)"; ssh-add ~/.ssh/id_ed25519; cat ~/.ssh/id_ed25519.pub
~~~
{: .language-bash}

You will need to press enter a few times to select default options and set the passphrase to empty.

Copy the last output line that starts with `ssh-ed25519` and ends with your email (it may have gone over multiple lines if your terminal isn't wide enough).

![SSH-Output](fig/SSH-Output.png){:width="50%"}

Finally, go to [https://github.com/settings/ssh/new](https://github.com/settings/ssh/new) (you will need to be logged into GitHub with the account you have created). Give the key a memorable name (the name of the computer you are working on is often a good choice) and paste the key from your clipboard into the box labelled key. Then, click add SSH key and you are done!

![SSH-Add](fig/SSH-Add.png){:width="50%"}

Now we are ready to download the code that we need for this lesson, using Git on the command line. Open a terminal on your machine, and enter:
~~~
$ cd
$ git clone https://github.com/Southampton-RSG/swc-git-novice
~~~
{: .language-bash}


`cd` will move to your home directory, and `git clone` will download a copy of the materials.
Once you're all set up, [we can start the course](git-novice-what-is-version-control).

{% include links.md %}

### Data Analysis and Visualization in R

#### Data Analysis and Visualization in R
