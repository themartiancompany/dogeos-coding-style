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
my views onto contributors as not even me always
abide to it, still it's quite possible if somebody
will ever send me code to review, I will very much
ask the sender to please format it in such
a way I can deem it *readable*.

Let me premise I've never been really strict with
this stuff; still, since DogeOS is an *operating
system-like set of software* supposed to work on
pretty much any kind of computing devices and that
from 2023 onwards, year in which I had suddenly
found myself without an home because of a series
of unfortunate events caused a group of very
irresponsible people who have played or still play
with other people's lives as if they were less
than humans, I've been forced to write it on terminals
whose size does not display well more than 60-80 columns
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

Also, my background is in Mathematics, not Computer
Science, so I've always found most computer code
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
mandatory for one to be proficient in programming
to have available and use *syntax highlighters*,
without which programming is more resembling to
a torture rather than to a relatively playful activity
like playing with construction toys.

Because of the above you can correctly imagine,
in particular at the beginning of my programming
journey, I've always been particularly fond of
languages in which one can mix in the same
document both formatted text and code, such as
*Jupyter notebooks* (`.ipynb`); more generally
I've always found the approach of the *Python*
programming language, in which lexemes' relative
positioning uniquely determines their semantic
role in the code, superior to those of other
languages in which these types of choices
are left to the programmer.

Since though an operating system is written
in dozens of languages rather a single one,
I've been forced to deal with the various
different rules imposed by each of them.

So, surprisingly maybe, these days I would
say my favourite programming language is actually
one in which no strict positioning
rule is enforced, the usage or not of special
characters such as curly braces determines what
to some people may be considered side effects,
in which there are basically no types other than
strings, which does not include lots of useful
constructs which simplify data access and analysis,
which everybody kinda knows but nobody
really likes to write in, which is almost
unreadable without a syntax highlighter,
which is horribly slow, which follows the least
common sense meanings for commands' names and
common action patterns, of which I've not read
the full manual of and so of which I do probably
not even know all of the syntax rules and on
which I actually impose one of strictest set of
rules one may think about:

*GNU Bash*.

I would say probably that is because really at
any given time, the language I do use the most
inevitably becomes the one I do like the most,
same as when during university I ended up
liking the most the field I did spend more time
on.
So, being that Bash is really a language for the
shell and its interpreter is virtually preinstalled
literally on any device on the market,
it couldn't but become my language of election
(even though actually it is not even the default
shell program running in my terminals).

I mean, for now, who knows about the future.

So, anyway, the coding style rules.

These rules are mainly intended for Bash
code but really they can be applied in almost
all programming languages and I suggest doing
so in order to minimize the differences
between them and among other things, facilitate
automatic conversion between them, where appliable.
Many of them have been derived and extended
from the first Bash program I've had to deal with,
[Archiso](
  https://github.com/themartiancompany/archiso).
I'm available to discuss and change them
at any time if convinced others may be better.

Before enumerating them, just let me tell just
one more thing.

Fuck you Linus Torvalds and *git ur push
smashed by a bunch of greedy masters*.

#### Basic coding style rules

- Lines must not be longer than 60,
  max 80 columns.

- Blocks shouldn't be longer than 100 lines;

- Indentation is two spaces long.

- In functions calls and declarations,
  not more than *one* parameter per line must
  be used.

- Programs and subcommand options and arguments
  must be grouped into arrays.

- Variables names must be the shortest and
  still the most descriptive as possible.

- All variables except global ones and all
  functions are *private*.

- Functions' local variables must be declared
  at the beginning of the block; after input
  variables, internal variables are defined
  before service variables.

- Global variables declarations must be defined
  in a function.

- Arrays can be used to shorted strings length.

- Pipelines and redirections must be indented.

##### Example

Honestly I think this example really should use the
[Crash Bash](
  https://github.com/themartiancompany/crash-bash)
library because it's the minimum required to
write a short Bash programs which is decent
to use but for the sake of simplicity I'm not gonna.

Also keep in mind, if you're reading this from
Github, that its Bash syntax highlighter is not
that great, so I strongly suggest reading this
code on a good programming text editor such as
Vim.

```bash
#!/usr/bin/env bash

_global_variables() {
  quiet=""
  target_movie=""
  segment_start=""
  segment_length=""
  app_opts=()
  msg=()
}

_requirements() {
  local \
    _mediaclip \
    _nplayer \
    _msg=()
  _mediaclip="$(
    command \
      -v \
      "medialength" || \
    true)"
  if [[ "${_mediaclip}" == "" ]]; then
    _msg=(
      "Install the program"
      "'mediaclip' from the"
      "'media-tools' package."
    )
    echo \
      "${_msg[*]}" \
      1>&2
    exit \
      1 
  fi
  _nplayer="$(
    command \
      -v \
      "nplayer" || \
    true)"
  if [[ "${_nplayer}" == "" ]]; then
    _msg=(
      "Install the 'nplayer'"
      "package."
    )
    echo \
      "${_msg[*]}" \
      1>&2
    exit \
      1 
  fi
}

_play_movie_segment() {
  local \
    _target_movie="${1}" \
    _segment_start="${2}" \
    _segment_length="${3}" \
    _mediaclip_args=() \
    _mediaclip_opts=() \
    _nplayer_opts=() \
    _mktemp_opts=() \
    _movie_segment \
    _msg=()
  _mktemp_opts+=(
    --dry-run
    --suffix=".mp4"
  )
  _msg=(
    "Playing movie '${_target_movie}'"
    "from second '${_segment_start}'"
    "for '${_segment_length}' seconds."
  )
  echo \
    "${_msg[*]}"
  _movie_segment="$(
    mktemp \
      "${_mktemp_opts[@]}")"
  _mediaclips_args+=(
    "${_target_movie}"
    "${_segment_start}"
    "${_segment_length}"
    "${_movie_segment}"
  )
  if [[ "${quiet}" == "n" ]]; then
    _mediaclip_opts+=(
      -v
    )
    _nplayer_opts+=(
      -v
    )
  fi 
  mediaclip \
    "${_mediaclip_opts[@]}" \
    "${_mediaclip_args[@]}"
  nplayer \
    "${_nplayer_opts[@]}" \
    "${_movie_segment}"
  rm \
    -rf \
    "${_movie_segment}"
}

_set_overrides() {
  if [[ ! -v quiet" ]]; then
    quiet="y"
  fi
  if [[ ! -v "segment_start" ]]; then
    segment_start="0"
  fi
  if [[ ! -v "segment_length" ]]; then
    segment_length="10"
  fi
}

_show_config() {
  local \
    _msg=()
  _msg=(
    "  Target movie: ${target_movie}"
    " Segment start: ${segment_start}"
    "Segment length: ${segment_length}"
  )
  if [[ "${quiet}" == "n" ]]; then
    printf \
      "%s\n" \
      "${_msg[@]}"
  fi
}

_usage() {
  local \
    _exit_code="${1}"
    _usage_text=()
  _usage_text=(
    "Play a movie segment"
    ""
    "Usage:"
    ""
    "  play-movie-segment"
    "    [options]
    "    <target-movie>
    ""
    "  options:"
    "     -s <start>      Segment start."
    "                     Default: ${segment_start}"
    "     -l <length>     Segment length."
    "                     Default: ${segment_length}"
    "     -h              This message."
    "     -v              Enable verbose output."
  )
  printf \
    "%s\n" \
    "${_usage_text[@]}"
  exit \
    "${_exit_code}"
}

_global_variables
_requirements

while \
  getopts \
    's:l:vh?' \
    arg; do
  case \
    "${arg}" in
    s)
      segment_start="${OPTARG}" ;;
    l)
      segment_length="${OPTARG}" ;;
    v)
      quiet="n" ;;
    h|?)
      _set_overrides
      _usage \
        0 ;;
    *)
      msg=(
        "Invalid argument '${arg}'."
      )
      echo \
        "${msg[*]}" \
        1>&2
      _usage \
        1 ;;
  esac
done
shift \
  $(( OPTIND - 1 ))
if (( ${#} < 1 )); then
  msg=(
    "A movie file should"
    "should be given in input."
  )
  echo \
    "${msg[*]}" \
    1>&2
  _usage \
    1 ;;
fi

_set_overrides

target_movie="${1}"

app_opts=(
  "${target_movie}"
  "${segment_start}"
  "${segment_length}"
)

_play_movie_segment \
  "${app_opts[@]}"
```

## License

This Document is released by Pellegrino Prevete
under the terms of the GNU Affero General Public
License version 3.
