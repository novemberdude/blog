# Office Titok docs
+ https://developers.tiktok.com/: hiện tại chỉ cung cấp các sdk cho phép nhúng tiktok vào website riêng, hoặc cho phép upload video trực tiếp lên titok. Chưa cung cấp data API để lấy dữ liệu public như Twitter API, Facebook Graph API.

`Typically a company will offer an API for users to access raw data from the platform similar to Youtube or Twitter`
+ các cách để get data từ TikTok hiện tại:
  1. TikTokApi python package: an unofficial api wrapper for TikTok.com in python
  *Một số repo dựng tiktok api trên github*: /davidteather/TikTok-Api (python), /szdc/tiktok-api (typescript)
--> dùng unofficial api --> tiktok will be get upset and block you from getting data.
--> should carefully review the titok Terms of Service: https://www.tiktok.com/legal/terms-of-use?lang=en --> Tiktok said: "You may not use automated scripts to collect information from or otherwise interact with the Services"

??? khi crawl có cần fake ip không? https://www.youtube.com/watch?v=Ozj6ypE9aR0

+ selenium vs scrapy: https://hackernoon.com/scrapy-or-selenium-c3efa9df2c06
+ Selenium is a free automated testing suite for web applications across different browsers and platforms. Although it was created for automated testing on web app, it is really easy to apply to scrape websites!
+ tiktoks.netlify.app - a website crawldata from tiktok
+ crawl like có phải update k

# Problem
1. crawl data by username: can get data through a real browser but not in get method: https://forum.freecodecamp.org/t/need-advice-regarding-tiktok-api/380030
2. {"statusCode":10102,"statusMsg":"not login"} --> returned when send request to get user info without login.



# Thiết kế source code idg_baochi

## package idg_baochi.crawl_fb

### sel_react_comment_page.py


# Comment code:
 + dùng context manager cho connect database
 + format logging
