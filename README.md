Official website of Nguyen Laboratory - Japan Advanced Institute of Science & Technology, Japan
======================================
## Structure
Directory | Purpose|
------------- | ------------- |
/css/ | All style sheets, for ordinary member, you should not modify content in this directory
/img/ | Image should be put here
/js/ | Javascript source code
/md/ | All the content of the site is written in "markdown" format.
/member/   | All HTML pages of lab's members
/section/   | All other HTML pages exclude
/template/  | Every pages of this site are built from the template in this directory
/index.html | Homepage HTML

## How to edit

### Create a new .md file
Duplicate any .md file in **/md/**

Rename your file such that it is unique and the name should be related to the content. Ex: your name...

Edit content of your .md file

### Create a new page
Duplicate any HTML file in **/member/** or **/section/** corresponding to your purpose.

Edit the link in **line 22** of your HTML file, this should link to your **.md** file that you have just created.

> data = loadPage('https://nguyenlab.github.io/md/alumi.md');

### Link the page to navigation bar

The navigation bar contain two level as shown in the image, please carefully read the instruction in the **/template/body.html** file.

Duplicate (do not uncomment the instruction line) the "commented" line of the appropriate level, then edit the `href` attribute which links to your HTML file.

> **This part require you a base knowledge of HTML, make sure what you commit.**

> Edit this file https://github.com/nguyenlab/nguyenlab.github.io/blob/master/template/body.html


