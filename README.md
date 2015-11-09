Wuxiaworld Scraper
==================

Supported stories
-----------------
* [Against the Gods](http://www.wuxiaworld.com/atg-index/)
* [Coiling Dragon](http://www.wuxiaworld.com/cdindex-html/)
* [Stellar Transformations](http://www.wuxiaworld.com/st-index/)

A quick Python scraper for wuxiaworld.com using Requests & BeautifulSoup.
Unlike the EPUBs floating around, the ones that come out of here have correct
chapter breaks and hyperlinked table of contents.

**NOTE**: The translator(s) at wuxiaworld.com wish to keep the community
centralized, so please do not post the resulting epubs to the public. They
don't mind if we make our own epubs, which is why I have written this scraper.
So feel free to make and use your own, but please respect their wishes
on this matter.

Even better, go participate in the community and let the translator know how
much you appreciate his work!

Only tested on Linux for now.
Creates separate HTML and optionally EPUBs for each "Book."

Here is what argparse tells me the usage is:

```
    usage: wuxiaworld_scraper.py [-h] [--delay DELAY] [--books BOOKS
                               [BOOKS ...]] [--no-epub]  url
```

DELAY is the pause between chapter downloads so we don't make a ton of requests
very fast, which could get us banned. By default, the script waits one second
between chapter downloads. It could be way faster if the books downloaded in
parallel, but don't do that. I haven't gotten banned yet with all my testing...

Here are some ways to run it:

Download all of Coiling Dragon and create EPUBS:

```
./wuxiaworld_scraper.py http://www.wuxiaworld.com/cdindex-html
```

Download book 3 of Coiling Dragon, but don't make an EPUB:

```
./wuxiaworld_scraper.py --no-epub http://www.wuxiaworld.com/cdindex-html --books 3
```

Download books 5-7 of Stellar Transformations and make EPUBs:

```
./wuxiaworld_scraper.py http://www.wuxiaworld.com/st-index --books 5 6 7
```


Known Bugs
----------
* Stellar Transformations does something weird with the chapter 1 titles, so
it's not quite right in the output.  My workaround is to manually fix the HTML
and then run pandoc.

Future Work
-----------
* Test on other OSes
* Make a webapp (like GoogleAppEngine) version
* Clean up code
* Write tests & integrate with Travis & Coveralls
* Support other stories on wuxiaworld.
* Support other sites?

