#util/util.Cookie

Cookie utilities

##Methods

###set

Set a cookie item

**Chainable**: true

**Params**:  
*   name _String_

    Cookie name
*   value _*_

    Cookie value
*   domain _String_

    The domain cookie store in
*   path _String_

    The path cookie store in
*   expires _Date_

    The expire time of cookie


###get

Get value of a cookie item

**Returns**: _String|Null_ - 

**Params**:  
*   name _String_

    Cookie name


###del

Delete a cookie item

**Chainable**: true

**Params**:  
*   name _String_

    Cookie name
*   domain _String_

    The domain cookie store in
*   path _String_

    The path cookie store in


###find

Find certain string in cookie with regexp

**Returns**: _Array|Null_ - RegExp matches

**Params**:  
*   pattern _RegExp_

    

####Example

     // assume cookie is like below
     // ts_uid=5458535332; ptui_loginuin=mice530@qq.com; Hm_lvt_bb8beb2d26e5d753995874b8b827291d=1367826377,1369234241;
     Cookie.find(/ptui_loginuin=([\S]*);/); // returns ["ptui_loginuin=mice530@qq.com;", "mice530@qq.com"]

