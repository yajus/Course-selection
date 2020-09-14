#### 外网选课
readme页面：https://jwxt-443.webvpn.jnu.edu.cn/Secure/PaiKeXuanKe/wfrm_Xk_ReadMeCn.aspx  
选课页面：https://jwxt-443.webvpn.jnu.edu.cn/Secure/PaiKeXuanKe/wfrm_XK_XuanKe.aspx  
**网址已废弃**  

新系统：jwxk.jnu.edu.cn  
#### 简单的js页面拉取，点击抢课代码
(讲道理这代码是会出bug的)  
```
function sleep(delay)
{
var start = new Date().getTime();
while (new Date().getTime() < start + delay);
}

//点击开始选课
document.getElementById('courseBtn').click();
sleep(1000)

//进入公选课
document.getElementById('aPublicCourse').click();
sleep(3000)

//课程搜索事件
var t=document.getElementById("publicSearch");
t.value="202116189"
select = document.getElementById('public_sfct')
console.log(select.options.length)
for (var i = 0; i < select.options.length; i++){
      if (select.options[i].value == '0'){
         select.options[i].selected = true;
         break;

      }
 }
ev = document.createEvent("HTMLEvents");
ev.initEvent("change", false, true);
select.dispatchEvent(ev);


//选课事件
function choiceprocess()
{
setTimeout("document.getElementsByClassName('cv-choice')[0].click();",3000);

setTimeout("document.getElementsByClassName('cv-sure cvBtnFlag')[0].click();",6000);

setTimeout("document.getElementsByClassName('cv-sure cvBtnFlag')[0].click();",9000);

setTimeout(choiceprocess,12000)
}

setTimeout(choiceprocess,1000);
```

#### 中大研究生选课
code from guolin zheng  
```
#!/bin/bash
while :
do
result=$(curl chrome F12 点击选课copy curl请求头填入)
    echo $result
    success=$(echo ${result} | grep "选课成功")
    echo $success
    if [ "$success" =  "" ] 
    then
        echo fail
    else
        echo success
        sleep 5
        break
    fi
    sleep 1
    echo sleeping
done

```
