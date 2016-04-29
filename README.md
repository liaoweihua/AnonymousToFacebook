# AnonymousToFacebook
Use Node.js and Facebook Graph API to build this "annonymous to facebook" system.<br/>
<a href="https://nodejs.org/" target="_blank">Node.js</a><br/>
<a href="https://developers.facebook.com/tools/explorer/" target="_blank">Facebook Graph API</a>

# Install
1. create mysql database must same as DB in kaobei.js.

2. create mysql datatable to record post must same as FanPageEnglishName in kaobei.js:

        id              BIGINT  UNSIGNED        AUTO_INCREMENT  PRIMARY KEY
        dataId          TEXT    NOT NULL
        ip              TEXT    NOT NULL
        postId          TEXT    NOT NULL
        postTime        TEXT    NOT NULL
        
3. create mysql datatable to record report must same as ReportDT in kaobei.js:

        id              BIGINT  UNSIGNED        AUTO_INCREMENT  PRIMARY KEY
        dataId          TEXT    NOT NULL
        ip              TEXT    NOT NULL
        fbUserId        TEXT    NOT NULL
        reportTime      TEXT    NOT NULL

4. Edit these three files

        kaobei.js
        about-this-site.js
        functions.js 內的 shorturl
    
5. Install canvas

        https://github.com/Automattic/node-canvas

6. Enter this project

7. npm install

8. forever start bin/www

#  Facebook Graph API
Post only message to facebook.

        Method: POST
        URL: /{fanpageid}/feed
        Body: {
            message: 訊息,
            link: 預覽網址
        }

Post photo to facebook.

        Method: POST
        URL: /{fanpageid}/photos
        Body: {
            message: 訊息,
            url: 圖片網址
        }

# bitly short url
Use bitly API to get short url from long url.

        Method: GET
        URL: http://api.bit.ly/v3/shorten?longUrl={1}&login={2}&apikey={3}&format=json";
        //1: 長網址
        //2: bitly使用者名稱
        //3: bitly API Key
        Response: {
            data: {
                url: 短網址
                ...
            }
            ...
        }

# Example
<a href="https://www.facebook.com/toolmanpage/" target="_blank">靠北工具人</a><br/>
<a href="http://toolman.kaobei.ga/" target="_blank">發文系統</a>
