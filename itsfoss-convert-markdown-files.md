tl,dr

for i in *.html ; do echo "$i" && pandoc -s $i -o $i.md ; done

::: {.site-container}
-   [Skip to primary
    navigation](#genesis-nav-primary){.screen-reader-shortcut}
-   [Skip to main content](#genesis-content){.screen-reader-shortcut}
-   [Skip to primary
    sidebar](#genesis-sidebar-primary){.screen-reader-shortcut}
-   [Skip to footer](#genesis-footer-widgets){.screen-reader-shortcut}

::: {.wrap}
::: {.title-area}
[It\'s FOSS](https://itsfoss.com/)

A Linux and Open Source Web Portal
:::

::: {.wrap}
-   [[[About]{itemprop="name"}](https://itsfoss.com/about/)]{#menu-item-10108}
    -   [[[Contact
        Us]{itemprop="name"}](https://itsfoss.com/contact-us/)]{#menu-item-17559}
    -   [[[Get Featured On It's
        FOSS]{itemprop="name"}](https://itsfoss.com/get-featured-on-its-foss/)]{#menu-item-17560}
-   [[[Linux]{itemprop="name"}](https://itsfoss.com/category/linux/)]{#menu-item-10119}
    -   [[[Linux
        News]{itemprop="name"}](https://itsfoss.com/category/news/)]{#menu-item-10121}
    -   [[[Software]{itemprop="name"}](https://itsfoss.com/category/apps/)]{#menu-item-10112}
    -   [[[Gadgets]{itemprop="name"}](https://itsfoss.com/category/gadgets/)]{#menu-item-10116}
    -   [[[Desktop
        Customization]{itemprop="name"}](https://itsfoss.com/category/desktop/)]{#menu-item-10113}
-   [[[Linux
    Tutorials]{itemprop="name"}](https://itsfoss.com/category/how-to/)]{#menu-item-10118}
-   [[[Top
    X]{itemprop="name"}](https://itsfoss.com/category/list/)]{#menu-item-17561}
-   [[[Forum]{itemprop="name"}](https://itsfoss.community/)]{#menu-item-88005}
-   [[[Linux
    Deals]{itemprop="name"}](https://itsfoss.com/deals/)]{#menu-item-54578}
-   [[[Article needs
    update?]{itemprop="name"}](https://itsfoss.com/feedback/ "If you see a grammatical or technical error, please notify us on this link.")]{#menu-item-27195}
-   ::: {#menu-item-siq-selectbox}
    ::: {#siq-menu-searchbox-wrap .siq-menu-searchbox-wrap}
    ::: {#siq-expsearch-cont .siq-expsearch-cont}
    []{.siq-expsearch-icon style="color:#000000"}
    :::
    :::
    :::
:::
:::

::: {.site-inner}
::: {.content-sidebar-wrap}
::: {#genesis-content .content role="main"}
::: {.breadcrumb itemscope="" itemtype="https://schema.org/BreadcrumbList"}
You are here: [[[Home]{.breadcrumb-link-text-wrap
itemprop="name"}](https://itsfoss.com/){.breadcrumb-link}]{.breadcrumb-link-wrap
itemprop="itemListElement" itemscope=""
itemtype="https://schema.org/ListItem"}

[/]{aria-label="breadcrumb separator"}
[[[Tutorial]{.breadcrumb-link-text-wrap
itemprop="name"}](https://itsfoss.com/category/how-to/){.breadcrumb-link}]{.breadcrumb-link-wrap
itemprop="itemListElement" itemscope=""
itemtype="https://schema.org/ListItem"}

[/]{aria-label="breadcrumb separator"} Converting Multiple Markdown
Files into HTML or Other Formats in Linux
:::

Converting Multiple Markdown Files into HTML or Other Formats in Linux {#converting-multiple-markdown-files-into-html-or-other-formats-in-linux .entry-title itemprop="headline"}
======================================================================

Last updated April 3, 2021 By [[[Bill Dyer]{.entry-author-name
itemprop="name"}](https://itsfoss.com/author/bill/){.entry-author-link}]{.entry-author
itemprop="author" itemscope="" itemtype="https://schema.org/Person"} [[5
Comments](https://itsfoss.com/convert-markdown-files/#comments)]{.entry-comments-link}

::: {.entry-content itemprop="text"}
Many times, when I use Markdown, I work on one file and when I'm done
with it, I convert it to HTML or some other format. Occasionally, I have
to create a few files. When I do work with more than one Markdown file,
I usually wait until I have finished them before I convert them.

I use pandoc to convert files, and it's possible convert all the
Markdown files in one shot.

Markdown can convert its files to .html, but if there's a chance that I
will have to convert to other formats like epub,
[pandoc](https://pandoc.org/) is the tool to use. I prefer to use the
command line, so I will cover that first, but you can also do this in
[VSCodium](https://vscodium.com/) without the command line. I'll cover
that too.

Converting multiple Markdown files to another format with Pandoc \[command line method\]
----------------------------------------------------------------------------------------

To get started quickly, Ubuntu, and other Debian distros can type the
following commands in the terminal:

``` {.wp-block-code}
sudo apt-get install pandoc
```

In this example, I have four Markdown files in a directory called
md\_test.

``` {.wp-block-code}
[email protected]:~/Documents/md_test$ ls -l *.md
-rw-r--r-- 1 bdyer bdyer 3374 Apr  7  2020 file01.md
-rw-r--r-- 1 bdyer bdyer  782 Apr  2 05:23 file02.md
-rw-r--r-- 1 bdyer bdyer 9257 Apr  2 05:21 file03.md
-rw-r--r-- 1 bdyer bdyer 9442 Apr  2 05:21 file04.md
[email protected]:~/Documents/md_test$
```

There are no HTML files yet. Now I'll use Pandoc to do its magic on the
collection of files. To do this, I run a one-line command that:

::: {#eaa_after_nth_p .eaa-wrapper .eaa_after_nth_p .eaa_desktop}
::: {.eaa-ad style=""}
:::
:::

-   calls pandoc
-   reads the .md files and exports them as .html

This is the command:

``` {.wp-block-code}
for i in *.md ; do echo "$i" && pandoc -s $i -o $i.html ; done
```

If you are not aware already, `;` is used for [running multiple commands
at once in Linux](https://itsfoss.com/run-multiple-commands-linux/).

Here's what the display looks like once I have executed the command:

``` {.wp-block-code}
[email protected]:~/Documents/md_test$ for i in *.md ; do echo "$i" && pandoc -s $i -o $i.html ; done
file01.md
file02.md
file03.md
file04.md
[email protected]:~/Documents/md_test$
```

Let me use the `ls` command once more to see if HTML files were created:

``` {.wp-block-code}
[email protected]:~/Documents/md_test$ ls -l *.html
-rw-r--r-- 1 bdyer bdyer  4291 Apr  2 06:08 file01.md.html
-rw-r--r-- 1 bdyer bdyer  1781 Apr  2 06:08 file02.md.html
-rw-r--r-- 1 bdyer bdyer 10272 Apr  2 06:08 file03.md.html
-rw-r--r-- 1 bdyer bdyer 10502 Apr  2 06:08 file04.md.html
[email protected]:~/Documents/md_test$
```

The conversion was a success, and you have four HTML files ready to go
on the Web server.

Pandoc is quite versatile and you can convert the markdown files to some
other supported format by specifying the extension of the output files.
You can understand why it is considered among the [best open source
tools for writers](https://itsfoss.com/open-source-tools-writers/).

::: {.wp-block-ugb-container .ugb-container .ugb-container--width-small .ugb-a4f08a0 .ugb-container--v2 .ugb-container--design-basic .ugb-main-block}
::: {.ugb-inner-block}
::: {.ugb-block-content}
::: {.ugb-container__wrapper .ugb-a4f08a0-wrapper}
::: {.ugb-container__side}
::: {.ugb-container__content-wrapper .ugb-a4f08a0-content-wrapper}
**Recommended Read:**

::: {.wp-block-ugb-blog-posts .ugb-blog-posts .ugb-921b5c0 .ugb-blog-posts--v2 .ugb-blog-posts--design-list .ugb-blog-posts--columns-1 .ugb-main-block}
::: {.ugb-inner-block}
::: {.ugb-block-content}
![](https://i1.wp.com/itsfoss.com/wp-content/uploads/2016/10/Best-Markdown-Editors-for-Linux.jpg?fit=800%2C450&ssl=1){.jetpack-lazy-image
width="800" height="450"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}

::: {.ugb-blog-posts__content}
### [11 Best Markdown Editors for Linux](https://itsfoss.com/best-markdown-editors-linux/) {#best-markdown-editors-for-linux .ugb-blog-posts__title}

::: {.ugb-blog-posts__excerpt}
A list of best Markdown Editors for Linux distributions that not only
look good but are also feature rich.
:::
:::
:::
:::
:::
:::
:::
:::
:::
:::
:::

Converting Markdown files to HTML using VSCodium \[GUI method\]
---------------------------------------------------------------

Like I've said earlier, I normally use the command line, but I don't
always use it for batch conversions, and you don't have to either.
VSCode or [VSCodium](https://itsfoss.com/vscodium/) can do the job. You
just need to add one extension, called: *Markdown-All-in-One* which will
allow you to convert more than one Markdown file in one run.

There are two ways to install the extension:

-   VSCodium's terminal
-   VSCodium's plug-in manager

To install the extension through VSCodium's terminal:

1.  Click on `Terminal` on the menu bar. The terminal panel will open
2.  Type, or [copy-and-paste, the following command in the
    terminal](https://itsfoss.com/copy-paste-linux-terminal/):

``` {.wp-block-code}
codium --install-extension yzhang.markdown-all-in-one
```

**Note**: If you're using VSCode instead of VSCodium, replace the word,
`codium`, in the above command, with `code`

::: {.wp-block-image}
![](https://i0.wp.com/itsfoss.com/wp-content/uploads/2021/04/vscodium_terminal.jpg?resize=800%2C564&ssl=1){.wp-image-88180
.jetpack-lazy-image width="800" height="564"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}
:::

The second way to install is through VSCodium's plug-in, or extension,
manager:

1.  Click on the blocks on the left side of the VSCodium window. A list
    of extensions will appear. At the top of the list, there will be a
    search bar.
2.  In the search bar, type: `Markdown All in One`. The extension will
    be listed at the top of the list. Click on the `Install` button to
    install it. If it is already installed, a gear icon will appear in
    place of the install button.

::: {.wp-block-image}
![](https://i1.wp.com/itsfoss.com/wp-content/uploads/2021/04/vscodium_extension_select.jpg?resize=800%2C564&ssl=1){.wp-image-88182
.jetpack-lazy-image width="800" height="564"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}
:::

Once the extension is installed, you can open the folder that contains
the Markdown files you want to convert.

Click on the paper icon located on the left side of the VSCodium window.
You'll be given the opportunity to choose your folder. Once a folder is
open, you'll need to open at least one file. You can open as many files
as you want, but one is the minimum.

Once a file is open, bring up the Command Palette by pressing
`CTRL+SHIFT+P`. Then, start typing `Markdown`in the search bar that will
appear. As you do this, a list of Markdown related commands will appear.
One of these will be `Markdown All in One: Print documents to HTML`
command. Click on that one.

::: {.wp-block-image}
![](https://i1.wp.com/itsfoss.com/wp-content/uploads/2021/04/vscodium_markdown_function_options.jpg?resize=800%2C564&ssl=1){.wp-image-88184
.jetpack-lazy-image width="800" height="564"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}
:::

You'll be asked to choose a folder containing the files. This is so an
output directory (called `out`) can be made and this is where the HTML
files will go. The image below shows that the HTML was made after
exporting the Markdown documents. From here, you can open, view, and
edit the HTML as you wish.

![](https://i0.wp.com/itsfoss.com/wp-content/uploads/2021/04/vscodium_html_filelist_shown.jpg?resize=800%2C564&ssl=1){.wp-image-88185
.jetpack-lazy-image width="800" height="564"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}

By waiting to convert your Markdown files, you can concentrate more on
writing. Conversion to HTML can come when you're ready -- and you have
two ways to get that done.

\

::: {.apester-media data-random="5caa056167b3b4fc52f9ace9" data-context="true" data-fallback="true"}
:::

[]{.tve-leads-two-step-trigger
.tl-2step-trigger-0}[]{.tve-leads-two-step-trigger .tl-2step-trigger-0}

::: {#om-xtv5oq3odfthcxltxptg-holder}
:::

::: {.ss-inline-share-wrapper .ss-hover-animation-fade .ss-with-counter-border .ss-inline-total-counter-left .ss-left-inline-content .ss-regular-icons .ss-with-spacing .ss-slanted-icons .ss-both-labels}
Like what you read? Please share it with others.

::: {.ss-inline-share-content}
::: {.ss-inline-counter}
[ 18 Shares ]{.ss-total-counter .ss-total-shares
.ss-share-inline_content-total-shares data-ss-ss-post-id="88173"}
:::

-   [Facebook]{.ss-network-label} [ 0 ]{.ss-network-count}
-   [Twitter]{.ss-network-label} [ 18 ]{.ss-network-count}
-   [LinkedIn]{.ss-network-label} [ 0 ]{.ss-network-count}
-   [Reddit]{.ss-network-label} [ 0 ]{.ss-network-count}
:::
:::
:::

[Filed Under:
[Tutorial](https://itsfoss.com/category/how-to/)]{.entry-categories}

::: {#comments .comments-compat-genesis-sample}
::: {#thrive-comments .clearfix}
::: {.tcm-dot-loader}
[]{.inner1} []{.inner2} []{.inner3}
:::

::: {.thrive-comments-content}
::: {.tcm-comments-filter}
:::

::: {#respond .tcm-comments-create}
:::

::: {.tcm-comments-list}
::: {.comment-author .vcard}
![](https://secure.gravatar.com/avatar/902d2837a1ad6aacd799fdb4792fc734?s=32&d=mm&r=g){.avatar
.avatar-32 .photo .jetpack-lazy-image width="32" height="32"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}

![](https://secure.gravatar.com/avatar/902d2837a1ad6aacd799fdb4792fc734?s=32&d=mm&r=g){.avatar
.avatar-32 .photo width="32" height="32"
srcset="https://secure.gravatar.com/avatar/902d2837a1ad6aacd799fdb4792fc734?s=64&d=mm&r=g 2x"}

**Alvaro Figueiredo** [says:]{.says}
:::

::: {.comment-metadata}
[April 10, 2021 at 5:19
am](https://itsfoss.com/convert-markdown-files/#comments/350941)
:::

::: {.comment-content}
This is a suggestion to improve your for command:

for i in \*.md ; do echo "\$i" && pandoc -s \$i -o \`basename \$i
md\`.html ; done
:::

::: {.reply}
[Reply](https://itsfoss.com/convert-markdown-files/?replytocom=350941#respond){.comment-reply-link}
:::

-   ::: {#comment-351199}
    ::: {.comment-author .vcard}
    ![](https://secure.gravatar.com/avatar/9a8f0a6b5adf63b59f0e17fae44f5987?s=32&d=mm&r=g){.avatar
    .avatar-32 .photo .jetpack-lazy-image width="32" height="32"
    srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}
    ![](https://secure.gravatar.com/avatar/9a8f0a6b5adf63b59f0e17fae44f5987?s=32&d=mm&r=g){.avatar
    .avatar-32 .photo width="32" height="32"
    srcset="https://secure.gravatar.com/avatar/9a8f0a6b5adf63b59f0e17fae44f5987?s=64&d=mm&r=g 2x"}
    **Bill** [says:]{.says}
    :::

    ::: {.comment-metadata}
    [April 20, 2021 at 8:24
    am](https://itsfoss.com/convert-markdown-files/#comments/351199)
    :::

    ::: {.comment-content}
    Thank you; much appreciated! I'll be keeping this in my toolbox. The
    small change does a pretty good job of removing .md. from the name
    in the .html file.
    :::

    ::: {.reply}
    [Reply](https://itsfoss.com/convert-markdown-files/?replytocom=351199#respond){.comment-reply-link}
    :::
    :::

::: {.comment-author .vcard}
![](https://secure.gravatar.com/avatar/36263b91b6838b1e1be458f709fb7e30?s=32&d=mm&r=g){.avatar
.avatar-32 .photo .jetpack-lazy-image width="32" height="32"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}

![](https://secure.gravatar.com/avatar/36263b91b6838b1e1be458f709fb7e30?s=32&d=mm&r=g){.avatar
.avatar-32 .photo width="32" height="32"
srcset="https://secure.gravatar.com/avatar/36263b91b6838b1e1be458f709fb7e30?s=64&d=mm&r=g 2x"}

**Jan** [says:]{.says}
:::

::: {.comment-metadata}
[April 7, 2021 at 8:23
pm](https://itsfoss.com/convert-markdown-files/#comments/350875)
:::

::: {.comment-content}
What is a Markdown file?
:::

::: {.reply}
[Reply](https://itsfoss.com/convert-markdown-files/?replytocom=350875#respond){.comment-reply-link}
:::

-   ::: {#comment-351200}
    ::: {.comment-author .vcard}
    ![](https://secure.gravatar.com/avatar/9a8f0a6b5adf63b59f0e17fae44f5987?s=32&d=mm&r=g){.avatar
    .avatar-32 .photo .jetpack-lazy-image width="32" height="32"
    srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}
    ![](https://secure.gravatar.com/avatar/9a8f0a6b5adf63b59f0e17fae44f5987?s=32&d=mm&r=g){.avatar
    .avatar-32 .photo width="32" height="32"
    srcset="https://secure.gravatar.com/avatar/9a8f0a6b5adf63b59f0e17fae44f5987?s=64&d=mm&r=g 2x"}
    **Bill** [says:]{.says}
    :::

    ::: {.comment-metadata}
    [April 20, 2021 at 8:45
    am](https://itsfoss.com/convert-markdown-files/#comments/351200)
    :::

    ::: {.comment-content}
    A Markdown file is a text file (written in a text editor, not a word
    processor). To make it a Markdown file, you just add certain tags to
    the text.

    If you've got some school class notes, you might find some
    similarities -- in handwritten notes, there may be stars next to a
    statement you need to remember, underlined text, and so on -- little
    marks that tell you that the text serves a function in helping you
    study.

    For example, in Markdown, to show that a line is a title, you just
    add a \# to the beginning of the title:

    \# This is a Title

    To italicize a word, you just surround the word or phrase with a
    "\*":

    This is an \*italicized\* word

    A bold word has two asterisks surrounding the word or phrase:

    This is a \*\*bold\*\* word.

    There are other tags, but basically, it's really just a simple way
    of marking up your text. Once the file is marked up, you save it
    with a ".md" extension.

    Markdown then, was made to simplify writing, but also to convert the
    text into web pages.

    The Markdown text file can then be put through a Markdown conversion
    script that creates a .html version of your file. If you use a
    Markdown editor, it probably has an export to html feature built in
    so you don't even have to worry about installing or running a
    script. :)

    Markdown was originally meant to convert to .html, but there are
    other flavors of Markdown that can convert a Markdown file to other
    formats, such as .doc and .pdf

    I hope this helps. :)
    :::

    ::: {.reply}
    [Reply](https://itsfoss.com/convert-markdown-files/?replytocom=351200#respond){.comment-reply-link}
    :::

    -   ::: {#comment-351206}
        ::: {.comment-author .vcard}
        ![](https://secure.gravatar.com/avatar/36263b91b6838b1e1be458f709fb7e30?s=32&d=mm&r=g){.avatar
        .avatar-32 .photo .jetpack-lazy-image width="32" height="32"
        srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}
        ![](https://secure.gravatar.com/avatar/36263b91b6838b1e1be458f709fb7e30?s=32&d=mm&r=g){.avatar
        .avatar-32 .photo width="32" height="32"
        srcset="https://secure.gravatar.com/avatar/36263b91b6838b1e1be458f709fb7e30?s=64&d=mm&r=g 2x"}
        **Jan** [says:]{.says}
        :::

        ::: {.comment-metadata}
        [April 20, 2021 at 1:10
        pm](https://itsfoss.com/convert-markdown-files/#comments/351206)
        :::

        ::: {.comment-content}
        Thank you Bill, this helps a lot. I couldn't figure it out
        myself because it looked very misterious to me the more I
        thought about it. But now it turns out to be very simple!
        :::

        ::: {.reply}
        [Reply](https://itsfoss.com/convert-markdown-files/?replytocom=351206#respond){.comment-reply-link}
        :::
        :::
    :::
:::

::: {.tcm-lazy-comments}
:::
:::
:::
:::
:::

Primary Sidebar {#primary-sidebar .genesis-sidebar-title .screen-reader-text}
---------------

::: {#custom_html-3 .section .widget_text .widget .widget_custom_html}
::: {.widget_text .widget-wrap}
::: {.textwidget .custom-html-widget}
::: {#mlb2-2516912 .ml-form-embedContainer .ml-subscribe-form .ml-subscribe-form-2516912}
::: {.ml-form-align-center}
::: {.ml-form-embedWrapper .embedForm}
::: {.ml-form-embedBody .ml-form-embedBodyDefault .row-form}
::: {.ml-form-embedContent style=""}
#### Weekly Linux Newsletter

Join 75,000 other Linux users and get the latest Linux news and tips in
your inbox for FREE.
:::

::: {.ml-form-formContent}
::: {.ml-form-fieldRow}
::: {.ml-field-group .ml-field-name}
:::
:::

::: {.ml-form-fieldRow .ml-last-item}
::: {.ml-field-group .ml-field-email .ml-validate-email .ml-validate-required}
:::
:::
:::

::: {.ml-form-recaptcha .ml-validate-required style="float:left"}
::: {.g-recaptcha data-sitekey="6Lf1KHQUAAAAAFNKEX1hdSWCS3mRMv4FlFaNslaD"}
:::
:::

::: {.ml-form-embedSubmit}
Yes, let me in!

::: {.ml-form-embedSubmitLoad}
<div>

</div>

<div>

</div>

<div>

</div>

<div>

</div>
:::
:::
:::

::: {.ml-form-successBody .row-success style="display:none"}
::: {.ml-form-successContent}
#### Almost there!

Please check your inbox for confirmation email. If it\'s not there, do
check your spam folder.
:::
:::
:::
:::
:::

![.](https://track.mailerlite.com/webforms/o/2516912/t1h9m7?v1597657573){.jetpack-lazy-image
width="1" height="1"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}

![.](https://track.mailerlite.com/webforms/o/2516912/t1h9m7?v1597657573){width="1"
height="1"}
:::
:::
:::

::: {#siq_search_widget-6 .section .widget .widget_siq_search_widget}
::: {.widget-wrap}
### Don't find what you are looking for? {#dont-find-what-you-are-looking-for .widgettitle .widget-title}

::: {#siq-expandwdgt-cont .siq-expandwdgt-cont}
[]{.siq-expandwdgt-icon}
:::
:::
:::

::: {#media_image-16 .section .widget .widget_media_image}
::: {.widget-wrap}
### Still have questions? Clear your doubt {#still-have-questions-clear-your-doubt .widgettitle .widget-title}

[![Ask
Here](https://i2.wp.com/itsfoss.com/wp-content/uploads/2020/02/ask-here.jpg?fit=350%2C100&ssl=1 "Still have questions? Clear your doubt"){.image
.wp-image-73823 .attachment-full .size-full .jetpack-lazy-image
width="350" height="100"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}](https://itsfoss.community/)
:::
:::

::: {#optin-monster-api-2 .section .widget .optin-monster-api}
::: {.widget-wrap}
::: {#om-xtv5oq3odfthcxltxptg-holder}
:::
:::
:::

::: {#custom_html-2 .section .widget_text .widget .widget_custom_html}
::: {.widget_text .widget-wrap}
::: {.textwidget .custom-html-widget}
::: {#itsfoss_300x250_300x600_Sidebar2 align="center"}
:::
:::
:::
:::
:::
:::

::: {#genesis-footer-widgets .footer-widgets}
Footer {#footer .genesis-sidebar-title .screen-reader-text}
------

::: {.wrap}
::: {.widget-area .footer-widgets-1 .footer-widget-area}
::: {#linkcat-2014 .section .widget .widget_links}
::: {.widget-wrap}
### About Pages {#about-pages .widgettitle .widget-title}

-   [About It\'s FOSS](https://itsfoss.com/about/ "Know more about us")
-   [Meet the
    team](https://itsfoss.com/its-foss-team/ "Team behind It’s FOSS")
-   [We Donate to FOSS
    Projects](https://itsfoss.com/donations-foss/ "Check out donations made by us to Open Source projects")
:::
:::

::: {#linkcat-1482 .section .widget .widget_links}
::: {.widget-wrap}
### Contact Pages {#contact-pages .widgettitle .widget-title}

-   [Contact Us](https://itsfoss.com/contact-us/)
-   [Get Featured on It\'s
    FOSS](https://itsfoss.com/get-featured-on-its-foss/ "Want your product to be featured on It’s FOSS?")
-   [Request a
    tutorial](https://itsfoss.com/request-tutorial/ "Can’t find what you are looking for? Tell us.")
:::
:::

::: {#media_image-15 .section .widget .widget_media_image}
::: {.widget-wrap}
[![Cc By
Sa](https://i1.wp.com/itsfoss.com/wp-content/uploads/2020/01/cc-by-sa-e1598703212542.png?fit=300%2C105&ssl=1){.image
.wp-image-72526 .attachment-medium .size-medium .jetpack-lazy-image
width="300" height="105"
srcset="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"}](https://itsfoss.com/copyright/)
:::
:::
:::

::: {.widget-area .footer-widgets-2 .footer-widget-area}
::: {#linkcat-2015 .section .widget .widget_links}
::: {.widget-wrap}
### Stay in Touch with It\'s FOSS {#stay-in-touch-with-its-foss .widgettitle .widget-title}

-   [Follow us on
    Facebook](https://www.facebook.com/itsfoss/ "The best Linux related page on the entire Facebook")
-   [Follow us on
    Instagram](https://www.instagram.com/itsfoss/ "Follow us for Linux related images")
-   [Follow us on
    LBRY](https://lbry.tv/$/invite/@itsfoss:0 "Open source YouTube alternative")
-   [Follow us on
    Mastodon](https://mastodon.social/@itsfoss "Follow It’s FOSS on Mastodon Platform")
-   [Follow us on
    Pinterest](https://www.pinterest.fr/its_foss/ "Follow us on Pinterest")
-   [Follow us on
    Twitter](https://twitter.com/itsfoss2 "Follow us on Twitter")
-   [Follow us via RSS Feed](https://itsfoss.com/feed/)
-   [Subscribe to
    Newsletter](https://itsfoss.com/subscribe-to-newsletter/ "Subscribe to daily or weekly newsletter")
-   [Subscribe to YouTube
    Channel](https://www.youtube.com/c/itsfoss?sub_confirmation=1 "Subscribe to our rapidly growing YouTube channel")
:::
:::
:::

::: {.widget-area .footer-widgets-3 .footer-widget-area}
::: {#linkcat-2012 .section .widget .widget_links}
::: {.widget-wrap}
### Communities {#communities .widgettitle .widget-title}

-   [Exclusive Telegram
    Channel](https://t.me/joinchat/AAAAAEPRGUJrEE1itjpH6A "Join our private Telegram Channel with over 500 members to get the updates instantly")
-   [It\'s FOSS
    Forum](https://itsfoss.community/ "Official forum for It’s FOSS readers")
-   [Join LinkedIn
    Community](https://www.linkedin.com/groups/8597839 "A community for FOSS Professionals")
-   [Linux Users Group on
    Facebook](https://www.facebook.com/groups/LinuxUsersGroupOfficial/ "Join our exclusive Linux Users Group with over 90,000 Linux enthusiasts")
-   [Linux Users Group on
    Reddit](https://www.reddit.com/r/LinuxUsersGroup/ "Join our Subreddit and interact with a passionate Linux community")
:::
:::

::: {#linkcat-2013 .section .widget .widget_links}
::: {.widget-wrap}
### Policies {#policies .widgettitle .widget-title}

-   [Affiliate
    Policy](https://itsfoss.com/affiliate-policy/ "Affiliate Policy")
-   [Privacy Policy](https://itsfoss.com/privacy-policy/)
:::
:::
:::
:::
:::

::: {.wrap}
It\'s FOSS is Part of chmod777 Media Tech (OPC) Pvt Ltd· Built on
[Genesis
Framework](https://www.shareasale.com/r.cfm?b=346198&u=747593&m=28169&urllink=&afftrack=)
and Powered by
[UpCloud](https://www.upcloud.com/register/?promo=itsfoss)
:::
:::

::: {#wp-auth-check-wrap .hidden}
::: {#wp-auth-check-bg}
:::

::: {#wp-auth-check}
[Close dialog]{.screen-reader-text}

::: {#wp-auth-check-form .loading data-src="https://itsfoss.com/wp-login.php?interim-login=1&wp_lang=en_US"}
:::

::: {.wp-auth-fallback}
**Session expired**

[Please log in again.](https://itsfoss.com/wp-login.php) The login page
will open in a new tab. After logging in you can close it and return to
this page.
:::
:::
:::

::: {style="display: none;"}
\>
:::

::: {#om-by19m9tmzfns6oco-holder}
:::

::: {#om-pztb1uabhcye9ksm-holder}
:::

::: {.jp-carousel-wrap .jp-carousel-transitions itemscope="" itemtype="https://schema.org/ImageGallery" style="display: none;"}
::: {.jp-carousel-overlay}
:::

::: {.jp-carousel}
:::

::: {.jp-carousel-fadeaway}
:::

::: {.jp-carousel-info}
::: {.jp-carousel-photo-info}
 {#section .jp-carousel-caption itemprop="caption description"}
:::

::: {.jp-carousel-info-columns}
::: {.jp-carousel-left-column-wrapper}
::: {.jp-carousel-titleanddesc}
:::

::: {.jp-carousel-photo-info}
 {#section-1 .jp-carousel-caption itemprop="caption description"}
:::

::: {#jp-carousel-comment-form-container}
Write a Comment\...

::: {#jp-carousel-comment-form-submit-and-info-wrapper}
::: {#jp-carousel-comment-form-commenting-as}
Email (Required)

Name (Required)

Website
:::

[ ]{#jp-carousel-comment-form-spinner}

::: {#jp-carousel-comment-post-results}
:::
:::
:::

::: {.jp-carousel-comments}
:::

::: {#jp-carousel-comments-loading}
Loading Comments\...
:::
:::

::: {.jp-carousel-image-meta}
::: {.jp-carousel-buttons}
[Comment](#){.jp-carousel-commentlink}
:::

[]{.jp-carousel-image-download}

::: {.jp-carousel-image-map style="display: none;"}
:::
:::
:::
:::

::: {.jp-carousel-next-button style="display: none;"}
:::

::: {.jp-carousel-previous-button style="display: none;"}
:::

::: {.jp-carousel-close-hint}
×
:::
:::

::: {#ss-copy-popup .ss-popup-overlay}
::: {.ss-popup}
::: {.ss-popup-heading}
Copy link
:::

::: {.ss-popup-content}
::: {.ss-copy-action}
[Copy[Copied]{.ss-share-network-tooltip}](#){.ss-button}
:::
:::
:::
:::
