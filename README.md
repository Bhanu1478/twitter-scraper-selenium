<h1> Twitter scraper selenium </h1>
<p> Python's package to scrap Twitter's front-end easily with selenium.  </p>


[![PyPI license](https://img.shields.io/pypi/l/ansicolortags.svg)](https://opensource.org/licenses/MIT) [![Python >=3.6.9](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/downloads/release/python-360/)
[![Maintenance](https://img.shields.io/badge/Maintained-Yes-green.svg)](https://github.com/shaikhsajid1111/facebook_page_scraper/graphs/commit-activity)

<!--TABLE of contents-->
<h2> Table of Contents </h2>
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#Prerequisites">Prerequisites</a></li>
        <li><a href="#Installation">Installation</a>
        <ul>
        <li><a href="#sourceInstallation">Installing from source</a></li>
        <li><a href="#pypiInstallation">Installing with PyPI</a></li>
        </ul>
        </li>
      </ul>
    </li>
    <li><a href="#Usage">Usage</a>
    <ul>
    <li><a href="#profile">Scraping profile's tweets</a>
    <ul>
    <li><a href="#profileJson">In JSON format</a></li>
    <li><a href="#profileCSV">In CSV format</a></li>
    <li><a href="#profileArgument">Function Arguments</a></li>
    <li><a href="#profileOutput">Keys of the output data</a></li>
    </ul>
    <li><a href="#keyword">Scraping tweets using keywords</a>
    <ul>
    <li><a href="#keywordJson">In JSON format</a></li>
    <li><a href="#keywordCSV">In CSV format</a></li>
    <li><a href="#keywordArgument">Function Arguments</a></li>
    <li><a href="#keywordOutput">Keys of the output data</a></li>
    </ul>
    </li>
    <li><a href="#proxy">Using scraper with proxy</a>
    <ul>
    <li><a href="#unauthenticatedProxy">Unauthenticated Proxy</a></li>
    <li><a href="#authenticatedProxy">Authenticated Proxy</a></li>
    </ul>
    </li>
    </li>
    </ul>
    </li>
    <li><a href="#privacy">Privacy</a></li>
    <li><a href="#license">License</a></li>
  </ol>
</details>

<!--TABLE of contents //-->
<br>
<hr>
<h2 id="Prerequisites">Prerequisites </h2>
<li> Internet Connection </li>
<li> Python 3.6+ </li>
<li> Chrome or Firefox browser installed on your machine </li>
<hr>
<h2 id="Installation"> Installation </h2>
<h3 id="sourceInstallation">Installing from the source</h3>
<p>Download the source code or clone it with:<p>

```
git clone https://github.com/shaikhsajid1111/twitter-scraper-selenium
```

<p>Open terminal inside the downloaded folder:</p>

<br>

```
 python3 setup.py install
```

<h3 id="pypiInstallation">
Installing with <a href="https://pypi.org">PyPI</a>
</h3>

```
pip3 install twitter-scraper-selenium
```

<hr>
<h2 id="Usage">
Usage</h2>

<h3 id="profile">To scrap profile's tweets:</h3>
<p id="profileJson">In JSON format:</p>

```python
from twitter_scraper_selenium import scrap_profile

microsoft = scrap_profile(twitter_username="microsoft",output_format="json",browser="firefox",posts_count=10)
print(microsoft)
```
Output:
```javascript
{
  "1430938749840629773": {
    "tweet_id": "1430938749840629773",
    "username": "Microsoft",
    "name": "Microsoft",
    "profile_picture": "https://twitter.com/Microsoft/photo",
    "replies": 29,
    "retweets": 58,
    "likes": 453,
    "is_retweet": false,
    "retweet_link": "",
    "posted_time": "2021-08-26T17:02:38+00:00",
    "content": "Easy to use and efficient for all \u2013 Windows 11 is committed to an accessible future.\n\nHere's how it empowers everyone to create, connect, and achieve more: https://msft.it/6009X6tbW ",
    "hashtags": [],
    "mentions": [],
    "images": [],
    "videos": [],
    "tweet_url": "https://twitter.com/Microsoft/status/1430938749840629773",
    "link": "https://blogs.windows.com/windowsexperience/2021/07/01/whats-coming-in-windows-11-accessibility/?ocid=FY22_soc_omc_br_tw_Windows_AC"
  },...
}
```
<hr>
<p id="profileCSV">In CSV format:</p>

```python
from twitter_scraper_selenium import scrap_profile


scrap_profile(twitter_username="microsoft",output_format="csv",browser="firefox",tweets_count=10,filename="microsoft",directory="/home/user/Downloads")


```

Output:
<br>
<table class="table table-bordered table-hover table-condensed" style="line-height: 14px;overflow:hidden;white-space: nowrap">
<thead><tr><th title="Field #1">tweet_id</th>
<th title="Field #2">username</th>
<th title="Field #3">name</th>
<th title="Field #4">profile_picture</th>
<th title="Field #5">replies</th>
<th title="Field #6">retweets</th>
<th title="Field #7">likes</th>
<th title="Field #8">is_retweet</th>
<th title="Field #9">retweet_link</th>
<th title="Field #10">posted_time</th>
<th title="Field #11">content</th>
<th title="Field #12">hashtags</th>
<th title="Field #13">mentions</th>
<th title="Field #14">images</th>
<th title="Field #15">videos</th>
<th title="Field #16">post_url</th>
<th title="Field #17">link</th>
</tr></thead>
<tbody><tr>
<td>1430938749840629773</td>
<td>Microsoft</td>
<td>Microsoft</td>
<td>https://twitter.com/Microsoft/photo</td>
<td align="right">64</td>
<td align="right">75</td>
<td align="right">521</td>
<td>False</td>
<td> </td>
<td>2021-08-26T17:02:38+00:00</td>
<td>Easy to use and efficient for all – Windows 11 is committed to an accessible future.<br/><br/>Here&#39;s how it empowers everyone to create, connect, and achieve more: https://msft.it/6009X6tbW </td>
<td>[]</td>
<td>[]</td>
<td>[]</td>
<td>[]</td>
<td>https://twitter.com/Microsoft/status/1430938749840629773</td>
<td>https://blogs.windows.com/windowsexperience/2021/07/01/whats-coming-in-windows-11-accessibility/?ocid=FY22_soc_omc_br_tw_Windows_AC</td>
</tr>

</tbody>
</table>
<p>...</p>

<br><hr>
<div id="profileArgument">
<p><code>scrap_profile()</code> arguments:</p>

<table>
    <thead>
        <tr>
            <td>Argument</td>
            <td>Argument Type</td>
            <td>Description</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>twitter_username</td>
            <td>String</td>
            <td>Twitter username of the account</td>
        </tr>
        <tr>
            <td>browser</td>
            <td>String</td>
            <td>Which browser to use for scraping?, Only 2 are supported Chrome and Firefox. Default is set to Firefox</td>
        </tr>
        <tr>
            <td>proxy</td>
            <td>String</td>
            <td>Optional parameter, if user wants to use proxy for scraping. If the proxy is authenticated proxy then the proxy format is username:password@host:port.</td>
        </tr>
        <tr>
            <td>tweets_count</td>
            <td>Integer</td>
            <td>Number of posts to scrap. Default is 10.</td>
        </tr>
        <tr>
            <td>output_format</td>
            <td>String</td>
            <td>The output format, whether JSON or CSV. Default is JSON.</td>
        </tr>
        <tr>
            <td>filename</td>
            <td>String</td>
            <td>If output parameter is set to CSV, then it is necessary for filename parameter to passed. If not passed then the filename will be same as username passed.</td>
        </tr>
        <tr>
            <td>directory</td>
            <td>String</td>
            <td>If output_format parameter is set to CSV, then it is valid for directory parameter to be passed. If not passed then CSV file will be saved in current working directory.</td>
        </tr>
    </tbody>
</table>

</div>
<hr>
<br>
<div id="profileOutput">
<p>Keys of the output</p>

<table>
    <thead>
        <tr>
            <td>Key</td>
            <td>Type</td>
            <td>Description</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>tweet_id</td>
            <td>String</td>
            <td>Post Identifier(integer casted inside string)</td>
        </tr>
        <tr>
            <td>username</td>
            <td>String</td>
            <td>Username of the profile</td>
        </tr>
        <tr>
            <td>name</td>
            <td>String</td>
            <td>Name of the profile</td>
        </tr>
        <tr>
            <td>profile_picture</td>
            <td>String</td>
            <td>Profile Picture link</td>
        </tr>
        <tr>
            <td>replies</td>
            <td>Integer</td>
            <td>Number of replies of tweet</td>
        </tr>
        <tr>
            <td>retweets</td>
            <td>Integer</td>
            <td>Number of retweets of tweet</td>
        </tr>
        <tr>
            <td>likes</td>
            <td>Integer</td>
            <td>Number of likes of tweet</td>
        </tr>
        <tr>
            <td>is_retweet</td>
            <td>boolean</td>
            <td>Is the tweet a retweet?</td>
        </tr>
        <tr>
            <td>retweet_link</td>
            <td>String</td>
            <td>If it is retweet, then the retweet link else it'll be empty string</td>
        </tr>
        <tr>
            <td>posted_time</td>
            <td>String</td>
            <td>Time when tweet was posted in ISO 8601 format</td>
        </tr>
        <tr>
            <td>content</td>
            <td>String</td>
            <td>content of tweet as text</td>
        </tr>
        <tr>
            <td>hashtags</td>
            <td>Array</td>
            <td>Hashtags presents in tweet, if they're present in tweet</td>
        </tr>
        <tr>
            <td>mentions</td>
            <td>Array</td>
            <td>Mentions presents in tweet, if they're present in tweet</td>
        </tr>
        <tr>
            <td>images</td>
            <td>Array</td>
            <td>Images links, if they're present in tweet</td>
        </tr>
        <tr>
            <td>videos</td>
            <td>Array</td>
            <td>Videos links, if they're present in tweet</td>
        </tr>
        <tr>
            <td>tweet_url</td>
            <td>String</td>
            <td>URL of the tweet</td>
        </tr>
        <tr>
            <td>link</td>
            <td>String</td>
            <td>If any link is present inside tweet for some external website. </td>
        </tr>
    </tbody>
</table>
</div>
<br>
<hr>
<h3 id="keyword">To scrap tweets using keywords:</h3>

<div>
<p id="keywordJson">In JSON format:</p>

```python
from twitter_scraper_selenium import scrap_keyword
#scrap 10 posts by searching keyword "india" from date 30th August till date 31st August
india = scrap_keyword(keyword="india", browser="firefox",
                      tweets_count=10,output_format="json" ,until="2021-08-31", since="2021-08-30")
print(india)

```
Output:
```javascript
{
  "1432493306152243200": {
    "tweet_id": "1432493306152243200",
    "username": "TOICitiesNews",
    "name": "TOI Cities",
    "profile_picture": "https://twitter.com/TOICitiesNews/photo",
    "replies": 0,
    "retweets": 0,
    "likes": 0,
    "is_retweet": false,
    "posted_time": "2021-08-30T23:59:53+00:00",
    "content": "Paralympians rake in medals, India Inc showers them with rewards",
    "hashtags": [],
    "mentions": [],
    "images": [],
    "videos": [],
    "tweet_url": "https://twitter.com/TOICitiesNews/status/1432493306152243200",
    "link": "https://t.co/odmappLovL?amp=1"
  },...
}
```
</div>
<br>
<hr>
<div id="keywordCSV">
<p>In CSV format:</p>

```python
from twitter_scraper_selenium import scrap_keyword

scrap_keyword(keyword="india", browser="firefox",
                      tweets_count=10, until="2021-08-31", since="2021-08-30",output_format="csv",filename="india")
```
<br>
Output:
<table class="table table-bordered table-hover table-condensed" style="line-height: 14px;overflow:hidden;white-space: nowrap">
<thead><tr><th title="Field #1">tweet_id</th>
<th title="Field #2">username</th>
<th title="Field #3">name</th>
<th title="Field #4">profile_picture</th>
<th title="Field #5">replies</th>
<th title="Field #6">retweets</th>
<th title="Field #7">likes</th>
<th title="Field #8">is_retweet</th>
<th title="Field #9">posted_time</th>
<th title="Field #10">content</th>
<th title="Field #11">hashtags</th>
<th title="Field #12">mentions</th>
<th title="Field #13">images</th>
<th title="Field #14">videos</th>
<th title="Field #15">tweet_url</th>
<th title="Field #16">link</th>
</tr></thead>
<tbody>

<tr>
<td>1432493306152243200</td>
<td>TOICitiesNews</td>
<td>TOI Cities</td>
<td>https://twitter.com/TOICitiesNews/photo</td>
<td>0</td>
<td align="right">0</td>
<td align="right">0</td>
<td>False</td>
<td>2021-08-30T23:59:53+00:00</td>
<td>Paralympians rake in medals, India Inc showers them with rewards</td>
<td>[]</td>
<td>[]</td>
<td>[]</td>
<td>[]</td>
<td>https://twitter.com/TOICitiesNews/status/1432493306152243200</td>
<td>https://t.co/odmappLovL?amp=1</td>
</tr>

</tbody></table>
<p> ... </p>
</div>
<hr>
<br>
<div id="keywordArgument">
<p><code>scrap_keyword()</code> arguments:</p>

<table>
    <thead>
        <tr>
            <td>Argument</td>
            <td>Argument Type</td>
            <td>Description</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>keyword</td>
            <td>String</td>
            <td>Keyword to search on twitter. </td>
        </tr>
        <tr>
            <td>browser</td>
            <td>String</td>
            <td>Which browser to use for scraping?, Only 2 are supported Chrome and Firefox,default is set to Firefox.</td>
        </tr>
        <tr>
            <td>until</td>
            <td>String</td>
            <td>Optional parameter, Until date for scraping, a end date from where search ends. Format for date is YYYY-MM-DD.</td>
        </tr>
        <tr>
            <td>since </td>
            <td>String</td>
            <td>Optional parameter, Since date for scraping, a past date from where to search from. Format for date is YYYY-MM-DD.</td>
        </tr>
        <tr>
            <td>proxy</td>
            <td>Integer</td>
            <td>Optional parameter, if user wants to use proxy for scraping. If the proxy is authenticated proxy then the proxy format is username:password@host:port</td>
        </tr>
        <tr>
            <td>tweets_count</td>
            <td>Integer</td>
            <td>Number of posts to scrap. Default is 10.</td>
        </tr>
        <tr>
            <td>output_format</td>
            <td>String</td>
            <td>The output format, whether JSON or CSV. Default is JSON.</td>
        </tr>
        <tr>
            <td>filename</td>
            <td>String</td>
            <td>If output parameter is set to CSV, then it is necessary for filename parameter to passed. If not passed then the filename will be same as keyword passed.</td>
        </tr>
        <tr>
            <td>directory</td>
            <td>String</td>
            <td>If output parameter is set to CSV, then it is valid for directory parameter to be passed. If not passed then CSV file will be saved in current working directory.</td>
        </tr>
    </tbody>
</table>
</div>
<hr>
<div id="keywordOutput">
<p>Keys of the output</p>
<table>
    <thead>
        <tr>
            <td>Key</td>
            <td>Type</td>
            <td>Description</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>tweet_id</td>
            <td>String</td>
            <td>Post Identifier(integer casted inside string)</td>
        </tr>
        <tr>
            <td>username</td>
            <td>String</td>
            <td>Username of the profile</td>
        </tr>
        <tr>
            <td>name</td>
            <td>String</td>
            <td>Name of the profile</td>
        </tr>
        <tr>
            <td>profile_picture</td>
            <td>String</td>
            <td>Profile Picture link</td>
        </tr>
        <tr>
            <td>replies</td>
            <td>Integer</td>
            <td>Number of replies of tweet</td>
        </tr>
        <tr>
            <td>retweets</td>
            <td>Integer</td>
            <td>Number of retweets of tweet</td>
        </tr>
        <tr>
            <td>likes</td>
            <td>Integer</td>
            <td>Number of likes of tweet</td>
        </tr>
        <tr>
            <td>is_retweet</td>
            <td>boolean</td>
            <td>Is the tweet a retweet?</td>
        </tr>
        <tr>
            <td>posted_time</td>
            <td>String</td>
            <td>Time when tweet was posted in ISO 8601 format</td>
        </tr>
        <tr>
            <td>content</td>
            <td>String</td>
            <td>content of tweet as text</td>
        </tr>
        <tr>
            <td>hashtags</td>
            <td>Array</td>
            <td>Hashtags presents in tweet, if they're present in tweet</td>
        </tr>
        <tr>
            <td>mentions</td>
            <td>Array</td>
            <td>Mentions presents in tweet, if they're present in tweet</td>
        </tr>
        <tr>
            <td>images</td>
            <td>Array</td>
            <td>Images links, if they're present in tweet</td>
        </tr>
        <tr>
            <td>videos</td>
            <td>Array</td>
            <td>Videos links, if they're present in tweet</td>
        </tr>
        <tr>
            <td>tweet_url</td>
            <td>String</td>
            <td>URL of the tweet</td>
        </tr>
        <tr>
            <td>link</td>
            <td>String</td>
            <td>If any link is present inside tweet for some external website. </td>
        </tr>
    </tbody>
</table>
</div>
<br>
<hr>

<h3 id="proxy"> Using scraper with proxy </h3>

<div id="unauthenticatedProxy">
<p>Just pass <code>proxy</code> argument to function.</p>

```python
from twitter_scraper_selenium import scrap_keyword

scrap_keyword(keyword="#india", browser="firefox",tweets_count=10,output="csv",filename="india",
proxy="66.115.38.247:5678") #In IP:PORT format

```
</div>

<br>
<div id="authenticatedProxy">
<p> Proxy that requires authentication: </p>

```python

from twitter_scraper_selenium import scrap_profile

microsoft_data = scrap_profile(twitter_username="microsoft", browser="chrome", tweets_count=10, output="json",
                      proxy="sajid:pass123@66.115.38.247:5678")  #  username:password@IP:PORT
print(microsoft_data)


```

</div>
<br>
<hr>
<div id="privacy">
<h2>Privacy</h2>

<p>
This scraper only scrapes public data available to unauthenticated user and does not holds the capability to scrap anything private.
</p>
</div>
<br>
<hr>
<div id="license">
<h2>LICENSE</h2>

MIT
</div>