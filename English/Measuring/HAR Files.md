HAR Files
=====================

HAR (HTTP Archive) files are used to keep a record of your request stack from start to finish. It's the data that you'll typically see when you're debugging a website with developer tools. The main difference is it's saved as a JSON representation.

You main reason for needing a HAR file would be to analyse the data externally from the request. For example if your client lives in China (notorius for it's politically incentivised blocking) and he/she experiences something that you're unable to experience in a different country. Your client can send you their HAR file allowing you access to the full request stack asthough you're making the request yourself. That is particularly useful when debugging performance issues internationally.

While a private VPN will cover most of this type of international testing there will always be instances where you just cannot get the data you need or just simply cannot replicate the issue and this is where a HAR file can step in.

Chrome users can find this HAR export quickly by right clicking network resources panel and clicking 'Save as HAR with Content'.

### Exporting HAR

![Exporting HAR data](http://s28.postimg.org/fptxwzq3h/Screenshot_2014_10_03_16_30_13.png)

### Viewing HAR

You can view HAR files online with HAR viewers.

[chromeHAR](http://ericduran.github.io/chromeHAR/) - By Eric Duran

[harviewer](https://github.com/janodvarko/harviewer) - By Jan Odvarko
