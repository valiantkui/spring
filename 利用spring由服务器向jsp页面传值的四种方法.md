## 1.使用request
    public  String  test(   
       HttpServletRequest   request){

            ....
          request.setAttribute("adminCode",adminCode);

      return  "index";//springmvc默认使用转发，将request转发到指定页面
      }

### 2.使用modelAndView
将数据先封装到ModelAndView对象里面，然后将该对象作为方法的返回值
## 3.使用modelMap
将该对象作为方法的参数，然后将数据绑定到该对象

     public  String  login6(AdminParam
            ap,ModelMap  mm){
    
          String adminCode=ap.getAdminCode();

        //相当于request.setAttribute().....
              
    mm.addAttribute("adminCode",adminCode);

     return  "index";
}

## 4.使用session




# 四种方法如何选择
优先选择生命周期短的。建议用request




