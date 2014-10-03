HAR Files
=====================

HAR (HTTP Archive) files are used to keep a record of your request stack from start to finish. It's the data that you'll typically see when you're debugging a website with developer tools. The main difference is it's saved as a JSON representation.

You main reason for needing a HAR file would be to analyse the data externally from the request. For example if your client lives in China (notorius for it's politically incentivised blocking) and he experiences something that you're unable to experience in a different country. You can gain access to the full request stack with this HAR file and debug as if you made the request from the clients origin location. Particularly useful when debugging performance in multiple countries.

While a private VPN will cover most of this type of testing there will always be instances where you just cannot get the data you need or just simply cannot replicate the issue.

Chrome users can find this HAR export quickly by right clicking network resources panel and clicking 'Save as HAR with Content'.

### Exporting HAR

![Exporting HAR data](http://s28.postimg.org/fptxwzq3h/Screenshot_2014_10_03_16_30_13.png)

### Viewing HAR

You can view HAR files online with HAR viewers.

[chromeHAR](http://ericduran.github.io/chromeHAR/) - By Eric Duran

[harviewer](https://github.com/janodvarko/harviewer) - By Jan Odvarko
