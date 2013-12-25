npm install node-weixin

/**
* 如果需要使用高级接口需要申请公众号，订阅号只能使用基础接口
*/
var weixin = require('node-weixin').init({
    url: '/',
    token: '',
    appid: '',
    secret: ''
});

weixin.errMsg(function (err) {
    console.log(err);
});

/**
 * 监听广本消息
 */
weixin.textMsg(function (msg) {
    weixin.postMsg({
        FromUserName: msg.ToUserName,
        ToUserName: msg.FromUserName,
        CreateTime: new Date().getTime(),
        MsgType: 'text',
        Content: 'haha'
    });
    //发送客服文本消息
    var data = {
        'touser': 'oMjrktwd14JaPBIC75QViXPLXjZ4',
        'msgtype': 'text',
        'text': {
            'content': '莫慌张，这是一条客服消息'
        }
    };
    weixin.postKefuMsg(data, function (r) {
        console.log(r);
    });
    console.log(msg);
});

/**
 * 监听图片消息
 */
weixin.imageMsg(function (msg) {
    weixin.postMsg({
        FromUserName: msg.ToUserName,
        ToUserName: msg.FromUserName,
        CreateTime: new Date().getTime(),
        MsgType: 'image',
        MediaId: '9GT8eGj2oiC_1hS_uzBWriuag_J_pEjdpzGz2ORXThxJ5gCzBXAbtgJ3g5x9wjkt'
    });
    //发送客服图片消息
    var data = {
        "touser": "oMjrktwd14JaPBIC75QViXPLXjZ4",
        "msgtype": "image",
        "image": {
            "media_id": "9GT8eGj2oiC_1hS_uzBWriuag_J_pEjdpzGz2ORXThxJ5gCzBXAbtgJ3g5x9wjkt"
        }
    };
    weixin.postKefuMsg(data, function (r) {
        console.log(r);
    });
    console.log(msg);
});

/**
 * 监听语音消息
 */
weixin.voiceMsg(function (msg) {
    weixin.postMsg({
        FromUserName: msg.ToUserName,
        ToUserName: msg.FromUserName,
        CreateTime: new Date().getTime(),
        MsgType: 'voice',
        MediaId: 'KmgpKgBjCNVSPr_QaR1oIKX36vc9zfmxxZh3zPnL4bX14WL0DenWzOUR4UuezeTS'
    });
    //发送客服语音消息
    var data = {
        "touser": "oMjrktwd14JaPBIC75QViXPLXjZ4",
        "msgtype": "voice",
        "voice": {
            "media_id": "KmgpKgBjCNVSPr_QaR1oIKX36vc9zfmxxZh3zPnL4bX14WL0DenWzOUR4UuezeTS"
        }
    };
    weixin.postKefuMsg(data, function (r) {
        console.log(r);
    });
    console.log(msg);
});

/**
 * 监听视频消息
 */
weixin.videoMsg(function (msg) {
    weixin.postMsg({
        FromUserName: msg.ToUserName,
        ToUserName: msg.FromUserName,
        CreateTime: new Date().getTime(),
        MsgType: 'video',
        MediaId: 'EurjyzU7O3QXY-V8YJF8RWOy9RqDq5Px0egafl1wUa_1_EvKWW3Jxlupxti-MRiW',
        ThumbMediaId: 'U-UH_SlFq3t16NRp4nu4Q_Yy_2p-l72L5X0S0qaySTNZNACBj1yIjLNBfFyIQlsE'
    });
    //发送客服视频消息
    var data = {
        "touser": "oMjrktwd14JaPBIC75QViXPLXjZ4",
        "msgtype": "video",
        "video": {
            "media_id": "EurjyzU7O3QXY-V8YJF8RWOy9RqDq5Px0egafl1wUa_1_EvKWW3Jxlupxti-MRiW",
            "title": "aa",
            "description": "bb"
        }
    };
    weixin.postKefuMsg(data, function (r) {
        console.log(r);
    });
    console.log(msg);
});

/**
 * 监听上报地理位置消息
 */
weixin.locationMsg(function (msg) {
    weixin.postMsg({
        FromUserName: msg.ToUserName,
        ToUserName: msg.FromUserName,
        CreateTime: new Date().getTime(),
        MsgType: 'music',
        Title: '果果的原创音乐',
        Description: '果果的原创音乐介绍',
        MusicUrl: 'http://qiniu.tuhuangzhe.com/audio/%E7%9B%B8%E6%80%9D%E5%90%9F2.wav?avthumb/mp3/ab/192k',
        HQMusicUrl: 'http://qiniu.tuhuangzhe.com/audio/%E7%9B%B8%E6%80%9D%E5%90%9F2.wav?avthumb/mp3/ab/250k',
        ThumbMediaId: 'U-UH_SlFq3t16NRp4nu4Q_Yy_2p-l72L5X0S0qaySTNZNACBj1yIjLNBfFyIQlsE'
    });
    //发送客服音乐消息
    var data = {
        "touser": "oMjrktwd14JaPBIC75QViXPLXjZ4",
        "msgtype": "music",
        "music": {
            "title": "果果的原创音乐",
            "description": "果果的原创音乐介绍",
            "musicurl": "http://qiniu.tuhuangzhe.com/audio/%E7%9B%B8%E6%80%9D%E5%90%9F2.wav?avthumb/mp3/ab/192k",
            "hqmusicurl": "http://qiniu.tuhuangzhe.com/audio/%E7%9B%B8%E6%80%9D%E5%90%9F2.wav?avthumb/mp3/ab/250k",
            "thumb_media_id": "9GT8eGj2oiC_1hS_uzBWriuag_J_pEjdpzGz2ORXThxJ5gCzBXAbtgJ3g5x9wjkt"
        }
    };
    weixin.postKefuMsg(data, function (r) {
        console.log(r);
    });
    console.log(msg);
});

/**
 * 监听链接消息
 */
weixin.linkMsg(function (msg) {
    weixin.postMsg({
        FromUserName: msg.ToUserName,
        ToUserName: msg.FromUserName,
        CreateTime: new Date().getTime(),
        MsgType: 'news',
        Articles: [
            {
                Title: 'aa',
                Description: 'bb',
                PicUrl: 'http://feeloc08.u.qiniudn.com/1385473580021/1385473580021.jpg?imageView/2/w/320',
                Url: 'http://blog.feeloc.cn'
            },
            {
                Title: 'aa',
                Description: 'bb',
                PicUrl: 'http://feeloc08.u.qiniudn.com/1385473580021/1385473580021.jpg?imageView/2/w/320',
                Url: 'http://blog.feeloc.cn'
            }
        ]
    });
    //发送客服图文消息
    var data = {
        "touser": "oMjrktwd14JaPBIC75QViXPLXjZ4",
        "msgtype": "news",
        "news": {
            "articles": [
                {
                    "title": "客服消息",
                    "description": "客服消息aa",
                    "url": "http://blog.feeloc.cn",
                    "picurl": "http://feeloc08.u.qiniudn.com/1385473580021/1385473580021.jpg?imageView/2/w/320"
                },
                {
                    "title": "客服消息",
                    "description": "客服消息bb",
                    "url": "http://blog.feeloc.cn",
                    "picurl": "http://feeloc08.u.qiniudn.com/1385473580021/1385473580021.jpg?imageView/2/w/320"
                }
            ]
        }
    };
    weixin.postKefuMsg(data, function (r) {
        console.log(r);
    });
    console.log(msg);
});

/**
 * 点击关注
 */
weixin.subEventMsg(function (msg) {
    console.log(msg);
});

/**
 * 取消关注
 */
weixin.unsubEventMsg(function (msg) {
    console.log(msg);
});

/**
 * 扫自定义二维码
 */
weixin.scanEventMsg(function (msg) {
    console.log(msg);
});

/**
 * 进入会话
 */
weixin.enterEventMsg(function (msg) {
    console.log(msg);
});

/**
 * 上报地理位置
 */
weixin.locationEventMsg(function (msg) {
    console.log(msg);
});

/**
 * 点击自定义菜单事件
 */
weixin.clickEventMsg(function (msg) {
    //发送客服文本消息
    var data = {
        'touser': 'oMjrktwd14JaPBIC75QViXPLXjZ4',
        'msgtype': 'text',
        'text': {
            'content': '你丫干嘛点我'
        }
    };
    weixin.postKefuMsg(data, function (r) {
        console.log(r);
    });
    console.log(msg);
});

/**
 * 设置自定义菜单
 */
weixin.setCusMenu({
    "button": [
        {
            "type": "click",
            "name": "今日歌曲",
            "key": "V1001_TODAY_MUSIC"
        },
        {
            "name": "菜单",
            "sub_button": [
                {
                    "type": "view",
                    "name": "搜索",
                    "url": "http://www.soso.com/"
                },
                {
                    "type": "view",
                    "name": "视频",
                    "url": "http://v.qq.com/"
                },
                {
                    "type": "click",
                    "name": "赞一下我们",
                    "key": "V1001_GOOD"
                }
            ]
        }
    ]
}, function (r) {
    console.log(r);
});

/**
 * 获取自定义菜单
 */
weixin.getCusMenu(function (r) {
    console.log(r);
});

/**
 * 删除自定义菜单
 */
weixin.delCusMenu(function (r) {
    console.log(r);
});

/**
 * 获得用户列表
 */
weixin.getUserList(function (r) {
    console.log(r);
});

exports.token = function (req, res) {
    if (weixin.signature(req)) {
        res.send(200, req.query.echostr);
    } else {
        res.send(200, 'fail');
    }
};

exports.msg = function (req, res) {
    weixin.getMsg(req, res);
};