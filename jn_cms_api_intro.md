- 登录
    - 站点地址:  `http://52.80.116.0`
    - 相对地址:  `/api/user/login.jspx`
    - 参数: 
        - username
            - 用户名
                1. 用户名: admin; 密码: password
                1. 用户名: test3; 密码: test3
            - 必选
        - aesPassword
            - 加密后的密码, 使用aes128进行加密
            - 必选
        - appId
            - 应用id, 固定
        - nonce_str
            - 随机字符串, java中可以实现, 参考test文件夹中样例长度
        - sign 
            - MD5算法实现, 参考test文件夹中的样例代码