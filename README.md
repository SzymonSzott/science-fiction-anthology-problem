# Solving the Science Fiction Anthology Problem
In his blog post, [The Mathematics of Buying Science Fiction Anthologies](https://auxiliarymemory.com/2018/08/18/the-mathematics-of-buying-science-fiction-anthologies/), James Wallace Harris proposed the  science fiction anthology problem:

> We’ve just published [The Classics of Science Fiction Short Stories](https://classicsofsciencefiction.com/classics-of-science-fiction-short-stories/) that identified 275 short stories, novelettes, and novellas that are  the most remembered in the genre. We gathered stories from 290  retrospective and annual best-of-the-year anthologies, several polls and lists, finalists from three awards (Hugo, Nebula, Sturgeon), three  recommended reading lists and put them into a database. We produced what we call The Classics of Science Fiction Short Stories list consisting  of the stories that were on at least 5 of those sources. [...]
>
> Here’s the mathematical challenge that appeals to me. What’s the minimum number of anthologies to buy to get the most of the 275 stories on the list?

In the meantime, v2 of the list has been released with 101 stories of 8 or more citations.

In mathematics, this is known as the [set cover problem](https://en.wikipedia.org/wiki/Set_cover_problem) and the goal of this mini-project is to use Python to:

- parse the [Short Stories v2](https://csfquery.com/SearchResult?mincite=8&category=story&sortby=7&list=1) list,
- create a story-to-anthology mapping using data from the [Internet Speculative Fiction Database](http://www.isfdb.org/),
- find the minimum number of books covering the short stories list.

# Results from Heuristics

The best solution that I could find using heuristics is 22 books (ordered by the number of classic SF short stories):

- Sense of Wonder
- The Wesleyan Anthology of Science Fiction
- Science Fiction: Stories and Contexts
- The Big Book of Science Fiction: The Ultimate Collection
- The Science Fiction Hall of Fame, Volume IV
- The Very Best of Fantasy & Science Fiction: 60th Anniversary Anthology
- The Science Fiction Century
- The Best of the Nebulas
- Armageddons
- Survival Printout
- Modern Classic Short Novels of Science Fiction
- The Legend Book of Science Fiction
- The Arbor House Treasury of Modern Science Fiction
- The Locus Awards: Thirty Years of the Best in Science Fiction and Fantasy
- Hugo and Nebula Award Winners from Asimov's Science Fiction
- The Hugo Winners, Volume Three
- The Best Science Fiction and Fantasy of the Year Volume Six
- The Best Science Fiction and Fantasy of the Year Volume Five
- The Year's Best Science Fiction: Fourth Annual Collection
- The Unreal and the Real: The Selected Short Stories of Ursula K. Le Guin
- The New Space Opera 2
- The New Hugo Winners, Volume III

This is a non-unique solution as any of the latter books, contributing a single story, can be replaced.

# The True Solution

Heuristics are fun to play around with, but if you want to find the true solution you should use an integer programming solver as explained by [S](https://shreevatsa.wordpress.com/) in one of the comments to the blog post [The SF Anthology Problem – Solved](https://classicsofsciencefiction.com/2020/08/09/the-sf-anthology-problem-solved/). [S](https://shreevatsa.wordpress.com/) provides an explanation of the solution [in this notebook](https://colab.research.google.com/drive/1wbktvb8XWISitThnpRA5_MLZh0JaKcK6#scrollTo=Vcaey1tMBiS7) reporting that the true solution, found using [Google OR-Tools](https://developers.google.com/optimization/mip/integer_opt) involves 21 books:

```


34 Sense of Wonder
22 Science Fiction: Stories and Contexts
22 The Big Book of Science Fiction: The Ultimate Collection
16 The Road to Science Fiction: Volume 3: From Heinlein to Here        OR        The Road to Science Fiction #3: From Heinlein to Here
12 The Locus Awards: Thirty Years of the Best in Fantasy and Science Fiction        OR        The Locus Awards: Thirty Years of the Best in Science Fiction and Fantasy
9 Great Science Fiction of the 20th Century
5 The Science Fiction Century
5 Nebula Award-Winning Novellas
4 Nebula Award Stories 5        OR        Nebula Award Stories Five
4 Future on Ice
4 The Hugo Winners, Volume Three
4 Modern Classics of Science Fiction        OR        The Legend Book of Science Fiction
3 Worlds Imagined        OR        The Arbor House Treasury of Great Science Fiction Short Novels
3 Nebula Winners Thirteen
3 Beyond the End of Time
1 The Best from Fantasy & Science Fiction: A 40th Anniversary Anthology        OR        The Year's Best Fantasy: First Annual Collection        OR        A Century of Fantasy 1980-1989: The Greatest Stories of the Decade        OR        The American Fantasy Tradition        OR        Demons and Dreams: The Best Fantasy and Horror 1        OR        The New Hugo Winners Volume II        OR        The New Hugo Winners, Volume II        OR        The Year's Best Fantasy Stories: 14
1 The 1987 Annual World's Best SF        OR        The Year's Best Science Fiction: Fourth Annual Collection        OR        Nebula Awards 22: SFWA's Choices for the Best Science Fiction & Fantasy 1986        OR        The Mammoth Book of Best New Science Fiction
1 The Best Science Fiction and Fantasy of the Year Volume Four        OR        Strangest of All: Anthology of Astrobiological Science Fiction        OR        Twenty-First Century Science Fiction        OR        The Final Frontier        OR        The New Space Opera 2        OR        The Year's Best Science Fiction & Fantasy: 2010        OR        The Year's Best Science Fiction: Twenty-Seventh Annual Collection        OR        Year's Best SF 15        OR        The Mammoth Book of Best New Science Fiction: 23rd Annual Collection
1 The Mammoth Book of Best New SF 25        OR        Nebula Awards Showcase 2013        OR        The Year's Best Science Fiction & Fantasy 2012        OR        The Year's Best Science Fiction: Twenty-Ninth Annual Collection        OR        The Best Science Fiction and Fantasy of the Year Volume Six
1 The Best Science Fiction and Fantasy of the Year Volume Two        OR        Nebula Awards Showcase: 2009: The Year's Best SF and Fantasy        OR        Nebula Awards Showcase 2009: The Year's Best SF and Fantasy        OR        The Year's Best Fantasy & Horror 2008: Twenty-First Annual Collection        OR        The Year's Best Science Fiction: Twenty-Fifth Annual Collection        OR        The Mammoth Book of Best New Science Fiction 21st Annual Collection
1 The Very Best of the Best: 35 Years of The Year's Best Science Fiction        OR        The Year's Best Dark Fantasy and Horror: 2011        OR        The Year's Best Science Fiction: Twenty-Eighth Annual Collection        OR        The Year's Best Science Fiction & Fantasy 2011        OR        The Year's Top Ten Tales of Science Fiction 3        OR        The Mammoth Book of Best New SF 24        OR        The Humanity of Monsters        OR        Clarkesworld: Year Four        OR        The Best Science Fiction and Fantasy of the Year Volume Five
```

# Author

[Szymon Szott](https://szymonszott.github.io/)
