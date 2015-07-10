# facebook-unreader
A javascript patch which can let you read message without "seen" by your friend


# Usage  
Please copy the following code and paste to the url-bar  
```
javascript:function runScript(){window.XMLHttpRequest.prototype._myopen=window.XMLHttpRequest.prototype.open;window.XMLHttpRequest.prototype.open=function(){if(arguments.length>=2&&(arguments[0].toLowerCase()=="post")&&typeof arguments[1]==="string"){if(arguments[1].indexOf("change_read_status",0)!=-1){console.log("cancel!!!");console.log(arguments);return;}else if(arguments[1].indexOf("typ",0)!=-1){console.log("cancel!!!");console.log(arguments);return;}else if(arguments[1].indexOf("send_message",0)!=-1){console.log("Send!");xmlhttp=new XMLHttpRequest();xmlhttp._myopen("POST","/ajax/messaging/typ.php",true);xmlhttp.send();}}console.log(arguments);this._myopen.apply(this,arguments);};window.onbeforeunload=function (e){var showMsg="我發現你要離開這一頁了!!\n等等如果要繼續隱藏已讀，請重新執行，才可以繼續發揮效用！";return showMsg;};alert("對方已經不知道你已經已讀或是正在打字囉\r\n\r\nBy GYZ");}if(typeof window.XMLHttpRequest.prototype._myopen==="function")alert("對方仍然不知道你已經已讀或是正在打字囉\r\n\r\nBy GYZ");else runScript();
```
### Chrome  
For Chrome user, fter you paste it to url-bar, please enter `javascript:` in the first   

