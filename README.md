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