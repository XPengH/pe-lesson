> ##  ga相关

> * 单页面统计所有页面路径
>
>   ``` js
>   router.afterEach((to) => {
>       window.ga('set', 'page', `${to.path}`);
>       window.ga('set', 'title', `${to.path}`);
>       window.ga('send', 'pageview');
>   })
>   ```

> * 事件统计
>
>   ``` js
>   ga('send', 'event', 'top500_jobsv2.3', 'click', 'form_btn_提交');
>   ```
>
> * 添加ga-analysis
>
>   ``` js
>   <script>
>       (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
>       (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
>       m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
>       })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
>       ga('create', 'UA-XXXXX-Y', 'auto');
>       ga('send', 'pageview');
>   </script>
>   ```
>
> * dfg
>
> * 