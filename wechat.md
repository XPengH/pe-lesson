> ## 微信网页
>
> * url history
>
>   vue replace 替换路由无法触发微信浏览器url更新，导致无法正常识别二维码(解决方法：locationstorage设置标志位reload页面)
>
> * 微信头像&&html2canvas 截图跨域微信头像不显示的问题
>
>   ``` nginx
>   location /wechat_image/ {
>           add_header 'Access-Control-Allow-Origin' "$http_origin" always;
>           add_header 'Access-Control-Allow-Credentials' 'true' always; 
>           add_header 'Access-Control-Allow-Methods' 'GET, OPTIONS' always; 
>           add_header 'Access-Control-Allow-Headers' 'Accept,Authorization,Cache-Control,Content-Type,DNT,If-Modified-  Since,Keep-Alive,Origin,User-Agent,X-Requested-With' always; 
>           proxy_pass http://thirdwx.qlogo.cn/mmopen/vi_32/; 
>    }
>   ```
>
>   
>
>   ``` js
>   wechaturl.replace(/(http|https):\/\/thirdwx\.qlogo\.cn\/mmopen\/vi_32\//, '/wechat_image/');
>   ```
>
> * ios微信滚动
>
>   ``` css
>   webkit-overflow-scrolling: touch;
>   ```
>
> * 微信分享logo问题
>
>   1. logo大小控制
>   2. 注意打包后的url是否正确
>
> * iphonex等长屏幕手机遮罩层有表单输入时，主内容被挤上去，无法回弹
>
>   ``` js
>   document.body.scrollTop = 0;
>   ```
>
>   
>
> * 分享链接带参需要uniqued转换，否则分享无图标
>
> * 
>
>   

> ##  微信小程序
>
> 