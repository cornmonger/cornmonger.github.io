
# &nbsp;

Welcome to my site!

## &#9000;&#65039; Bash: Emulate Git's Hash-Object Output

Here's a one-liner [bash](https://www.gnu.org/software/bash/manual/html_node/index.html) function that will output the same [SHA1 hash](https://man7.org/linux/man-pages/man1/sha1sum.1.html) that [git hash-object](https://git-scm.com/docs/git-hash-object) outputs for a file:

```bash
function git_hashobject { echo -e "blob $(wc -m $1 | awk '{print $1}')\0$(cat $1)" | sha1sum | awk '{print $1}'; }
```

Example usage:

```
$  echo 'hello world!' > hello.txt
$  git hash-object hello.txt
a0423896973644771497bdc03eb99d5281615b51
$  git_hashobject hello.txt 
a0423896973644771497bdc03eb99d5281615b51
```



## &#127794; This Week: Git Internals

One of the projects that I'm building is designed around [Git](https://git-scm.com). Recently, I've began studying [Git internals](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain) and drafting out use cases with [Rust's git crate](https://github.com/rust-lang/git2-rs).

One thing that I wasn't aware of is that there are manpage tutorials for Git: ```man gittutorial``` and ```man gittutorial-2``` are available on the commandline and they're very good introductions to general use and internals respectively.

## &#128212; mdBook is Online  

I've configured [GitHub Pages](https://pages.github.com) to point to an [mdBook](https://github.com/rust-lang/mdBook) installation, which now powers this little website. It was pretty easy to setup!
