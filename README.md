## 請將以下連結加入書籤
[Facebook 取消已讀](javascript:function runScript(){window.XMLHttpRequest.prototype._myopen=window.XMLHttpRequest.prototype.open;window.XMLHttpRequest.prototype.open=function(){if(arguments.length>=2&&(arguments[0].toLowerCase()=="post")&&typeof arguments[1]==="string"){if(arguments[1].indexOf("change_read_status",0)!=-1){console.log("cancel!!!");console.log(arguments);return;}else if(arguments[1].indexOf("typ",0)!=-1){console.log("cancel!!!");console.log(arguments);return;}else if(arguments[1].indexOf("send_message",0)!=-1){console.log("Send!");xmlhttp=new XMLHttpRequest();xmlhttp._myopen("POST","/ajax/messaging/typ.php",true);xmlhttp.send();}}console.log(arguments);this._myopen.apply(this,arguments);};window.onbeforeunload=function (e){var showMsg="我發現你要離開這一頁了!!\n等等如果要繼續隱藏已讀，請重新執行，才可以繼續發揮效用！";return showMsg;};alert("對方已經不知道你已經已讀或是正在打字囉\r\n\r\nBy GYZLAB");}if(typeof window.XMLHttpRequest.prototype._myopen==="function")alert("對方仍然不知道你已經已讀或是正在打字囉\r\n\r\nBy GYZLAB");else runScript();)

## 功能：
當這個指令碼開始運行後，對方不會發現你已讀 也不會發現你正在輸入！
## Note:  
Work on Chrome, Firefox & IE
Enjoy it!!

## 指令碼:
```markdown
  function runScript()
  {
    //_myopen用來置換原本的open，所以如果要使用原本的xmlhttp.open 要使用._myopen
    window.XMLHttpRequest.prototype._myopen = window.XMLHttpRequest.prototype.open;
    window.XMLHttpRequest.prototype.open = function(){      
        if (arguments.length >= 2&& (arguments[0].toLowerCase() == "post")&& typeof arguments[1] === "string")            
        {
          //取消change_read_status 不會告知系統我已讀
          if(arguments[1].indexOf("change_read_status", 0) != -1)
          {
            console.log("cancel!!!");
            console.log(arguments);
            return;
          }
          //取消typ 不會告知系統我在輸入
          else if(arguments[1].indexOf("typ", 0) != -1)  
          {
              console.log("cancel!!!");
              console.log(arguments);
              return;
          }
          //FB的機制是 send_message之前 一定要有typ
          else if(arguments[1].indexOf("send_message", 0) != -1)  
          {
            console.log("Send!");
            //送出一個ajax typ.php
            xmlhttp = new XMLHttpRequest();
            //注意！是呼叫.myopen 如果呼叫open會被擋掉
            xmlhttp._myopen("POST", "/ajax/messaging/typ.php", true);
            xmlhttp.send();
          }
      }
      console.log(arguments);
      this._myopen.apply(this, arguments);
      };
    window.onbeforeunload = function (e) {
    var showMsg = "我發現你要離開這一頁了!!\n等等如果要繼續隱藏已讀，請重新執行，才可以繼續發揮效用！";
    return showMsg;
    };
    alert("對方已經不知道你已經已讀或是正在打字囉");
  }//function runScript
  //main
  if(typeof window.XMLHttpRequest.prototype._myopen==="function")
    alert("對方仍然不知道你已經已讀或是正在打字囉");  
  else
    runScript();
```


