> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/weixin_51584115/article/details/126686989?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522171810818216800185883125%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=171810818216800185883125&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-126686989-null-null.142^v100^pc_search_result_base4&utm_term=csdn%E6%96%87%E7%AB%A0%E4%B8%8B%E8%BD%BD&spm=1018.2226.3001.4187)

**嫌前面这段啰嗦可以直接拖到最后看下载方法**  
听网课的时候看到 CSDN 上的笔记，觉得记得很好，很详细，想把它保存下来，于是去搜了一下如何将 CSDN 博客文章导出为 PDF，找到了这篇文章：[如何将 CSDN 文章内容转成 PDF](https://blog.csdn.net/u010055819/article/details/93205398?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522166226004316782244893572%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=166226004316782244893572&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~baidu_landing_v2~default-1-93205398-null-null.142%5Ev46%5Epc_ran_alice&utm_term=CSDN%E5%8F%98PDF&spm=1018.2226.3001.4187)  
尝试之后下载成功，但有一个问题，就是有一部分内容会被 “关注” 条挡住  
![](https://img-blog.csdnimg.cn/373bf2f017d949868a165b12d36e8f43.png)  
**解决方法：**  
在代码里加一条  
$(“.left-toolbox”).remove();  
left-toolbox 就是 “关注” 这个标签的类名，这句的意思就是把这个标签移除  
![](https://img-blog.csdnimg.cn/62c994303c28449e859c4dceb753cebd.png)

#### 最终方法

1.  打开 CSDN 文章内容
    
2.  按键盘上的 f12 键（或者右键—审查元素）进入浏览器调试模式，点击控制台（Console）进入控制台  
    ![](https://img-blog.csdnimg.cn/f0273e75fbb8453da40df10dfb549f4e.png)
    
3.  在控制台输入以下代码，回车
    

![](https://img-blog.csdnimg.cn/887a6f4e25f24039802fabcd42c06774.png)

```
(function(){
$("#side").remove();
$("#comment_title, #comment_list, #comment_bar, #comment_form, .announce, #ad_cen, #ad_bot").remove();
$(".nav_top_2011, #header, #navigator").remove();
$(".p4course_target, .comment-box, .recommend-box, #csdn-toolbar, #tool-box").remove();
$("aside").remove();
$(".tool-box").remove();
$(".csdn-side-toolbar").remove();
$(".more-toolbox").remove();
$(".template-box").remove();
$(".left-toolbox").remove();
$(".bottom-pub-footer").remove();
$(".pre-numbering").remove();
$("main").css('display','content'); 
$("main").css('float','left'); 
$("#mainBox").css('width','100%');        
$(".main_father.clearfix.d-flex.justify-content-center").css("width","100%");

window.print();
 
$("tool-box").remove();
})();

```

4.  在弹出的打印页面中将**布局**设置成横向，纵向会显示不全。  
    这里我设置的**每个工作表的页数**是两页，可以按自己的要求设置  
    设置完成后点击**打印**，将 pdf 文件保存到文件夹  
    ![](https://img-blog.csdnimg.cn/6f02ff4364dd49f683c7cf2fc2193825.png)
    
5.  旋转文档（用的是 WPS）  
    ![](https://img-blog.csdnimg.cn/bb86aacff9ac4fae8d312d6c5469be43.png)