# 青岛卫生人才教育培训平台刷课脚本


## 脚本

学习网站：青岛卫生人才教育培训平台: https://wsjxjy.org/#/

脚本地址：[青岛卫生人才教育培训平台-刷课脚本][2]

## 教程

浏览器安装篡改猴插件后，打开[脚本安装地址][2]，进入后点击安装脚本，安装完成刷新你的学习网页就可以愉快使用了。

## 联系

注：如果需要代学，可以联系我微信yizhituziang或者QQ2422270452

![微信二维码](https://www.tuziang.com/wx.jpg)

## 更多

关键代码分享：
```
  setInterval(function () {
    if (location.href.indexOf("#/video?pid=") != -1) {
      // 当前视频已经完成，那么返回视频列表
      if (document.querySelector("p.el-alert__description") && document.querySelector("p.el-alert__description").innerText.indexOf("已完成") != -1) {
        // 返回详情
        document.querySelector("#app > div tr > td > button:nth-child(2) > span").click()
      }
    }
  }, 1 * 1000)

  var lastLocation = ''
  setInterval(function () {
    //console.log("判断进入sp ", location.href.indexOf("#/exam/notice?m")!=-1 && lastLocation.indexOf("#/exam/notice?m")==-1)
    if (location.href.indexOf("/#/proinfo?pid=") != -1 && lastLocation.indexOf("/#/proinfo?pid=") == -1) {
      setTimeout(function () {
        startVideo()
      }, 4 * 1000)
    }
    lastLocation = location.href
  }, 100)

  // 从视频列表中点击第一个未完成的视频
  function startVideo() {
    console.log("startVideo", startVideo)
    for (let i = 0; i < document.querySelectorAll("tbody > tr").length; i++) {
      let tr = document.querySelectorAll(" tbody > tr")[i]
      if (tr && tr.innerText.indexOf("100%") == -1) {
        document.querySelectorAll(" tbody > tr")[i].querySelector("button").click()
        return
      }
    }
  }
```


  [1]: https://microsoftedge.microsoft.com/addons/detail/%E7%AF%A1%E6%94%B9%E7%8C%B4/iikmkjmpaadaobahmlepeloendndfphd?refid=bingshortanswersdownload
  [2]: https://greasyfork.org/zh-CN/scripts/507144-%E9%9D%92%E5%B2%9B%E5%8D%AB%E7%94%9F%E4%BA%BA%E6%89%8D%E6%95%99%E8%82%B2%E5%9F%B9%E8%AE%AD%E5%B9%B3%E5%8F%B0%E5%88%B7%E8%AF%BE%E8%84%9A%E6%9C%AC
