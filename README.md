# wxh5pay


// 监控微信浏览器
  
isWeiXin() { 
let ua = window.navigator.userAgent.toLowerCase(); 
if (ua.match(/MicroMessenger/i) != "micromessenger") { 
this.isWeiXi = false
  
// 重新存储新的token（在外部浏览器打开支付完成后是没有token这些数据的所以需要在浏览器一打开的时候就去存一次数据）
  
window.localStorage.setItem("channelId", this.theRequest.channelId); 
window.localStorage.setItem("userKey",JSON.stringify(this.theRequest.userKey)); 
window.localStorage.setItem("userToken",JSON.stringify(this.theRequest.userToken)); 
if(this.theRequest.memberTypeName){
  
// 调用支付宝支付
  
this.zfbPayBuy(this.theRequest) 
} else { 
this.zfbPayBuySocial(this.theRequest) 
}
  
} else { 
this.isWeiXi = true
  
} 
},


![image](https://img-blog.csdnimg.cn/24884355e4bc4e64b8f8ce22303abc4e.gif)







