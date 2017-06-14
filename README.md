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
    Duplicate any .md file in /md/
    Rename your file such that it is unique and the name should be related to the content. Ex: your name...
    Edit content of your .md file

### Create a new page
    Duplicate any HTML file in /member/ or /section/ corresponding to your purpose.
    Edit line 22 of that file that refer to you

```
data = loadPage('https://nguyenlab.github.io/md/alumi.md');

```

### Link the page to navigation bar
To-be-written

### Integrate content file to the page
To-be-written

