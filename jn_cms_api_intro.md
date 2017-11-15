- 站点地址:  `http://52.80.116.0`
- 登录
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
- 获取内容
    - 相对地址: `/api/content/list.jspx`
    - 参数:
        ````
        /**
        * 内容列表API
        * ids tagIds、topicId、channelIds、siteIds 必须有一个参数有值，否则结果为空 
        * ids tagIds、topicId、channelIds、siteIds 的参数值之间以,号分隔,比如channelIds "73,74"
        * channelOption参数仅在使用 channelIds参数时有效，默认值为1
        * @param format 非必选 默认1 内容信息简化模式  0全部信息模式
        * @param ids  ids优先级最高
        * @param tagIds  tagID优先级第二
        * @param topicId 专题ID 优先级第三
        * @param channelIds 栏目ID 优先级第四
        * @param siteIds 站点ID 优先级第五
        * @param typeIds 类型ID数组  非必选
        * @param titleImg  是否有标题图 非必选
        * @param recommend  推荐 非必选 
        * @param orderBy  排序 非必选 默认4固顶降序
        * @param title   标题检索  非必选
        * @param channelOption  channelOption 1子栏目 2副栏目  0或者channelIds多个值
        * @param first   查询开始下标  非必选  默认0
        * @param count	  查询数量  非必选  默认10
        */
        ````
     - 注意: 查询数量默认为`10`
- 获取栏目列表
    - 相对地址: `/api/channel/list.jspx`
    - 参数:
        ```
        /**
        * 栏目列表API
        * @param parentId  父栏目ID
        * @param siteId    站点ID
        * @param hasContentOnly  是否有内容
        * @param first   查询开始下标
        * @param count	  查询数量
        */
        ```
    - 注意: 只能获取一层栏目, 子栏目需根据父栏目id获取