In vim, access the 1-toc.md file and do these steps.
To erase the 1st line, which shows the file name 1-toc.md:
dd

Then a quick macro to apply to all lines:
qa
yyP
esc
I "* (space) ["
esc
e (space) R (space) e a "](space)"
esc
D a "("
esc
JxA ")"
enter
esc
99@a
boom!
