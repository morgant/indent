# dent
By Morgan Aldridge <morgant@makkintosshu.com>

[![dent on OpenHub](https://www.openhub.net/p/dent/widgets/project_thin_badge.gif)](https://www.openhub.net/p/dent) [![Build Status](https://travis-ci.com/morgant/dent.svg?branch=master)](https://travis-ci.com/morgant/dent) [![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=DBY3R8ARLDELE&currency_code=USD&source=url)

## OVERVIEW

`dent` is a small utility written in `bash` which indents the output of the command passed as a parameter.

## USAGE

Prepend `dent` to any command:

    dent echo "Hello world"

Output:

      Hello world

Because `dent` increments `DENT_LEVEL` prior to executing the command and decrements it upon completion, it inherently supports nested calls. So, if you have another command or function that itself calls `dent`, it's output will be further indented. For example:

    dent dent echo "Hello world"

Output:

        Hello world

## ENVIRONMENT VARIABLES

* `DENT_CHAR` - The character(s) used to indent (default: '  ' [two spaces])
* `DENT_LEVEL` - The current indent level (default: `0`)

