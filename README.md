#### 项目简介
此项目为茅酒汇主项目，项目主要由原生和RN、触屏混合开发。
#### 开发环境及配置
- 开发工具 Android Studio3.1.2以上
- jdk 1.7以上


####  安装
- Flavors字段说明：
production生产环境
stagging测试环境
rn环境(连接服务资源，第一次加载完成远程资源后白屏，需要重启一次APP）
- Jenkins打包说明
[android-maojiuhui(生产包)](  http://10.0.0.223:8080/view/android/job/android-maojiuhui/)
[android-maojiuhui-staging(测试包)](   http://10.0.0.223:8080/view/android/job/android-maojiuhui-staging/)
[android-maojiuhui-release(渠道包)]( http://10.0.0.223:8080/view/android/job/android-maojiuhui-release/)




- 二维码地址下载地址
 [生产apk(与测试包微信支付环境共用)](https://fir.im/gbk3)
 [测试apk](https://fir.im/8daz)

#### 开发调试
- java联调：APP点击 我的存酒->接口设置httpUrl、httpsUrl
- 触屏联调：APP点击 我的存酒->接口设置webUrl->手机wifi设置代理
- [路由地址纪录](http://tools.jinhui365.cn/interface/list?domain_id=19&viewName=%E8%8C%85%E9%85%92%E6%B1%87%E7%A7%BB%E5%8A%A8%E7%AB%AF%E8%B7%AF%E7%94%B1%E6%8E%A5%E5%8F%A3%E5%88%97%E8%A1%A8)
- [接口地址]( http://tools.jinhui365.cn/interface/list?domain_id=20&viewName=%E8%8C%85%E9%85%92%E6%B1%87%E6%8E%A5%E5%8F%A3%E5%88%97%E8%A1%A8)

#### 发布
- 升级版本号
gradle.properties文件修改，VERSION_NAME VERSION_CODE
- [渠道包存放地址](http://10.0.0.223:8080/view/android/job/android-maojiuhui-release/)

#### 目录结构
    ├── app 主项目
        ├──src
            ├── main 项目公共文件
                ├── maojiuhui 茅酒汇代码依赖main
                    ├── adapter  数据对应的adapter
                    ├── common 公共类
                        ├── component 组件
                        ├── data 时间选择器
                        ├── route 路由相关
                    ├── im 聊天相关代码
                    ├── manager 管理类，用户信息管理等
                    ├── model层
                        ├── data json实体
                        ├── event EventBus事件
                        ├── service 网络请求接口url
                    ├── mvp中的presenter层
                    ├── rn rn相关类
                    ├── util 工具类
                    ├── mvp中的view层
    ├── MPCharLib 折线图依赖库
    ├── RN折线图需要依赖的库，该库依赖MPCharLib


#### 相关链接
- [功能职责](http://wiki.jinhui365.cn/pages/viewpage.action?pageId=7046740)
- [支付SDK](http://gitlab.jinhui365.cn/android/android-zqpay-zl)
- [RN基类库](http://gitlab.jinhui365.cn/mobile/rn-app-basic)
- [渠道打包](https://github.com/mcxiaoke/packer-ng-plugin)
- [网易云信IM](http://wiki.jinhui365.cn/pages/viewpage.action?pageId=15451668)
- [360加固在jenkins持续集成](http://wiki.jinhui365.cn/pages/viewpage.action?pageId=4785517)
- [im sdk](http://gitlab.jinhui365.cn/android/im-library)

#### 注意事项  

1、渠道包
app/src/maojiuhui/assets/ut.json 记录注册ut参数，当渠道增加后需要注意变更该文件