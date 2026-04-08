[comment]: <> (SPDX-License-Identifier: AGPL-3.0)

[comment]: <> (-----------------------------------------)
[comment]: <> (Copyright © 2024, 2025, 2026)
[comment]: <> (            Pellegrino Prevete)
[comment]: <> (All rights reserved)
[comment]: <> (-----------------------------------------)

[comment]: <> (This program is free software: you can)
[comment]: <> (redistribute it and/or modify it under)
[comment]: <> (the terms of the GNU Affero General)
[comment]: <> (Public License as published by the)
[comment]: <> (Free Software Foundation, either version)
[comment]: <> (3 of the License.)

[comment]: <> (This program is distributed in the hope)
[comment]: <> (that it will be useful, but WITHOUT ANY)
[comment]: <> (WARRANTY; without even the implied)
[comment]: <> (warranty of MERCHANTABILITY or FITNESS)
[comment]: <> (FOR A PARTICULAR PURPOSE. See the GNU)
[comment]: <> (AFFERO General Public License for more)
[comment]: <> (details.)

[comment]: <> (You should have received a copy of the)
[comment]: <> (GNU Affero General Public License along)
[comment]: <> (with this program. If not, see)
[comment]: <> (<https://www.gnu.org/licenses/>.)

# DogeOS Coding Style Guide

This document describes the preferred coding style for
[DogeOS](
  https://github.com/themartiancompany/dogeos).

As Torvalds
[remarks](
  https://docs.kernel.org/process/coding-style.html),
coding style is very personal so I also won't force
my views onto contributors, still it's quite possible
if somebody will ever send me code to review, I will
very much ask the sender to please format it in such
a way I can deem it *readable*.

Let me premise I've never been really strict with
this stuff; still, since DogeOS is an *operating
system-like set of software* supposed to work on
pretty much any kind of computing devices and that
from 2023 onwards, year on which I had suddenly
found myself without an home because of a series
of unfortunate events caused a group of very
irresponsible people who have played or still play
with other people's lives as if they were less
than humans, I've been forced to write it on terminals
whose size does not display well more than 60-80 columns,
and even less rows, so that respecting this short
yet quite rigid set of rules has become for me pretty
much mandatory.

<div
   align="center">
  <img
     src="https://raw.githubusercontent.com/themartiancompany/dogeos-coding-style/cfbc2b6a31a80e651d66340de2237597f3b148fe/media/hip01.jpg"
     width="500"
     align="center"
  />
  <br />
  <sub>
    <i>
      An HIP-01 device.
    </i>
  </sub>
</div>

Also, my background is in Mathematics, not computer
science, so I've always found most computer code
to be relatively *unreadable*, given in Mathematics
one does usually use letters, not whole words to
refer to variables, let alone group of words joined
with space-like characters like the *underscores*
(`_like_this_way_for_example`).
In this regard please let me make public I do consider
the *camel case* convention (`likeThisWayForExample`)
extremely barbaric and barely fit for computers
rather than humans and do not let me even start
about how easy is for one to be reminded about another
camel something whenever that term is being used.

Because of the above, I've always considered
mandatory for one be proficient in programming
to have available and use *syntax highlighters*,
without which programming is more resembling to
torture rather than a relatively playful activity
like playing with construction toys.

Because of the above, you can correctly imagine,
in particular at the beginning of my programming
journey, I've always been particularly fond of
languages in which one can mix in the same
document both formatted text and code, such as
*Jupyter notebooks* (`.ipynb`); more generally
I've always found the approach of the *Python*
programming language, in which lexemes' relative
positioning uniquely determines their semantic
role in the code.




## License

This Document is released by Pellegrino Prevete
under the terms of the GNU Affero General Public
License version 3.
