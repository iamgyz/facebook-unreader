# facebook-unreader
A javascript patch which can let you read message without "seen" by your friend


# Usage  
Please copy the following code and paste to the url-bar  
```
javascript:function runScript(){window.XMLHttpRequest.prototype._myopen=window.XMLHttpRequest.prototype.open;window.XMLHttpRequest.prototype.open=function(){if(arguments.length>=2&&(arguments[0].toLowerCase()=="post")&&typeof arguments[1]==="string"){if(arguments[1].indexOf("change_read_status",0)!=-1){console.log("cancel!!!");console.log(arguments);return;}else if(arguments[1].indexOf("typ",0)!=-1){console.log("cancel!!!");console.log(arguments);return;}else if(arguments[1].indexOf("send_message",0)!=-1){console.log("Send!");xmlhttp=new XMLHttpRequest();xmlhttp._myopen("POST","/ajax/messaging/typ.php",true);xmlhttp.send();}}console.log(arguments);this._myopen.apply(this,arguments);};window.onbeforeunload=function (e){var showMsg="%E6%88%91%E7%99%BC%E7%8F%BE%E4%BD%A0%E8%A6%81%E9%9B%A2%E9%96%8B%E9%80%99%E4%B8%80%E9%A0%81%E4%BA%86!!\r\n\r\n%E7%AD%89%E7%AD%89%E5%A6%82%E6%9E%9C%E8%A6%81%E7%B9%BC%E7%BA%8C%E9%9A%B1%E8%97%8F%E5%B7%B2%E8%AE%80%EF%BC%8C%E8%A8%98%E5%BE%97%E5%86%8D%E6%8C%89%E4%B8%80%E4%B8%8B%E6%9C%AC%E6%9B%B8%E7%B0%BD%EF%BC%8C%E6%89%8D%E5%8F%AF%E4%BB%A5%E7%B9%BC%E7%BA%8C%E7%99%BC%E6%8F%AE%E6%95%88%E7%94%A8%EF%BC%81";return showMsg;};alert("%E5%B0%8D%E6%96%B9%E5%B7%B2%E7%B6%93%E4%B8%8D%E7%9F%A5%E9%81%93%E4%BD%A0%E5%B7%B2%E7%B6%93%E5%B7%B2%E8%AE%80%E6%88%96%E6%98%AF%E6%AD%A3%E5%9C%A8%E6%89%93%E5%AD%97%E5%9B%89\r\n\r\n%E5%88%87%E8%A8%98%EF%BC%9A%E9%80%99%E5%80%8B%E6%95%88%E6%9E%9C%E5%8F%AA%E5%AD%98%E5%9C%A8%E5%96%AE%E4%B8%80%E5%88%86%E9%A0%81%E4%B8%AD%EF%BC%8C%E8%80%8C%E4%B8%94%E4%B8%8D%E6%98%AF%E6%B0%B8%E4%B9%85%E7%9A%84%E5%91%A6\r\n\r\nBy GYZ");}if(typeof window.XMLHttpRequest.prototype._myopen==="function")alert("%E5%B0%8D%E6%96%B9%E4%BB%8D%E7%84%B6%E4%B8%8D%E7%9F%A5%E9%81%93%E4%BD%A0%E5%B7%B2%E7%B6%93%E5%B7%B2%E8%AE%80%E6%88%96%E6%98%AF%E6%AD%A3%E5%9C%A8%E6%89%93%E5%AD%97%E5%9B%89\r\n\r\n%E5%88%87%E8%A8%98%EF%BC%9A%E9%80%99%E5%80%8B%E6%95%88%E6%9E%9C%E5%8F%AA%E5%AD%98%E5%9C%A8%E5%96%AE%E4%B8%80%E5%88%86%E9%A0%81%E4%B8%AD%EF%BC%8C%E8%80%8C%E4%B8%94%E4%B8%8D%E6%98%AF%E6%B0%B8%E4%B9%85%E7%9A%84%E5%91%A6\r\n\r\nBy GYZ");else runScript();
```
### Chrome  
For Chrome user, fter you paste it to url-bar, please enter `javascript:` in the first   

