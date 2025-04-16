# shcrapy

A tool to collect links from a website

## Intro

shcrapy is a tool that was created to collect mp3 (and any extension) links from a website and save them to a file, allowing for mass downloading.

## Instructions

shcrapy comes with 3 built in flags or arguments
- use the `-e|--extensions` flag to specify a comma separated list of extensions to scrape for
- use the `-i|--ignore` flag to specify a comma separated list of words to ignore. If the word is found in the URL, it will not scrape that URL. This is useful to ignore certain areas of a website, for example "radio"
- use the `-f|--force` flag to scrape every sigle URL. Normally shcrapy will avoid scraping links that include special characters, which are usually used to navigate a single page, or query on a single page. It also does not scrape links ending with an extension, but instead, simply saves them to the output file. But sometimes it can be desireable. Be warned, this will take quite long for most sites, especially if it is scraping large mp3 files.
- use the `-d|--depth` flag to specify a "depth" value. Normally shcrapy will search stricly inside the URL that is entered. If this is set to 2, for example, shcrapy will scrape the entered URL, as well as any URLs that are linked on any of the pages it scrapes. If set to 3, it will dig down 3 layers.
Once started, shcrapy will save specified links to a file in the directory where it is running named after the URL that is used. Once it is finished running, the contents of the file can be pasted into a downloader like JDownloader to download them all.

## Examples

`./shcrapy -e mp3 thenarrowpath.com` - collect mp3 links from a url

`./shcrapy -e mp3 -f thenarrowpath.com` - collect mp3 links from a url and forcibly scrape all urls, including ones with special characters (can take a long time)

`./shcrapy -e mp3,pdf thenarrowpath.com/audio/audio-books` - collect mp3 and pdf files from a sub-url

`./shcrapy -e mp3,zip,pdf -i radio thenarrowpath.com` - collect mp3, zip and pdf files while ignoring any link including the word 'radio'

`./shcrapy -e mp3 -d 2 thenarrowpath.com` - collect mp3 files from a url, and any urls linked on any page within the url (depth 2)

shcrapy will also work for sub-urls. It will only collect links below any sub-url specified.
