# shcrapy
A tool to collect links from a website

## Intro
shcrapy is a tool that was created to collect mp3 (and any extension) links from a website and save them to a file, allowing for mass downloading.

## Instructions
shcrapy comes with 3 built in flags or arguements
- use the '-e' flag to specify a comma separated list of extensions to scrape for
- use the '-i' flag to specify a comma separated list of words to ignore. If the word is found in the URL, it will not scrape that URL. This is useful to ignore certain areas of a website, for example "radio"
- use the '-f' flag to scrape every sigle URL. Normally shcrapy will avoid links that include special characters, which are usually used to navigate a single page, or query on a single page. But sometimes it can be desireable.

## Examples
`shcrapy -e mp3 thenarrowpath.com` - collect mp3 links from a url

`shcrapy -e mp3,pdf thenarrowpath.com/audio/audio-books` - collect mp3 and pdf files from a sub-url

`shcrapy -e mp3,zip,pdf -i radio thenarrowpath.com` - collect mp3, zip amd pdf files while ignoring any link including the word 'radio'

shcrapy will also work for sub-urls. It will only collect links below any sub-url specified.
