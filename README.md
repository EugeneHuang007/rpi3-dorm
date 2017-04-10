# rpi3-dorm
raspberryPi3b+温湿度传感+继电器开关控制+flask web展示


#### QQ邮箱设置，使用
![qqemailsetting](/Users/wangzhiwei/myGitHub/rpi3-dorm/flaskWeb/static/image/qqemailsetting.png)

### 使用和天气API接口
#### 注册和天气开发者账号获取API key

![hew](/Users/wangzhiwei/myGitHub/rpi3-dorm/flaskWeb/static/image/hew.png)
![hewkey](/Users/wangzhiwei/myGitHub/rpi3-dorm/flaskWeb/static/image/hewkey.png)

#### 和天气API接口使用说明
![heweatherAPI](/Users/wangzhiwei/myGitHub/rpi3-dorm/flaskWeb/static/image/heweatherAPI.png)

####  数据返回示例

```bash
{
    "HeWeather5": [
        {
            "alarms": [
                {
                    "level": "蓝色",
                    "stat": "预警中",
                    "title": "山东省青岛市气象台发布大风蓝色预警",
                    "txt": "青岛市气象台2016年08月29日15时24分继续发布大风蓝色预警信号：预计今天下午到明天，我市北风风力海上6到7级阵风9级，陆地4到5阵风7级，请注意防范。",
                    "type": "大风"
                }
            ],
            "aqi": {
                "city": {
                    "aqi": "60",
                    "co": "0",
                    "no2": "14",
                    "o3": "95",
                    "pm10": "67",
                    "pm25": "15",
                    "qlty": "良",  //共六个级别，分别：优，良，轻度污染，中度污染，重度污染，严重污染
                    "so2": "10"
                }
            },
            "basic": {
                "city": "青岛",
                "cnty": "中国",
                "id": "CN101120201",
                "lat": "36.088000",
                "lon": "120.343000",
                "prov": "山东"  //城市所属省份（仅限国内城市）
                "update": {
                    "loc": "2016-08-30 11:52",
                    "utc": "2016-08-30 03:52"
                }
            },
            "daily_forecast": [
                {
                    "astro": {
                        "mr": "03:09",
                        "ms": "17:06",
                        "sr": "05:28",
                        "ss": "18:29"
                    },
                    "cond": {
                        "code_d": "100",
                        "code_n": "100",
                        "txt_d": "晴",
                        "txt_n": "晴"
                    },
                    "date": "2016-08-30",
                    "hum": "45",
                    "pcpn": "0.0",
                    "pop": "8",
                    "pres": "1005",
                    "tmp": {
                        "max": "29",
                        "min": "22"
                    },
                    "vis": "10",
                    "wind": {
                        "deg": "339",
                        "dir": "北风",
                        "sc": "4-5",
                        "spd": "24"
                    }
                }
            ],
            "hourly_forecast": [
                {
                    "cond": {
                        "code": "100",
                        "txt": "晴"
                    },
                    "date": "2016-08-30 12:00",
                    "hum": "47",
                    "pop": "0",
                    "pres": "1006",
                    "tmp": "29",
                    "wind": {
                        "deg": "335",
                        "dir": "西北风",
                        "sc": "4-5",
                        "spd": "36"
                    }
                }
            ],
            "now": {
                "cond": {
                    "code": "100",
                    "txt": "晴"
                },
                "fl": "28",
                "hum": "41",
                "pcpn": "0",
                "pres": "1005",
                "tmp": "26",
                "vis": "10",
                "wind": {
                    "deg": "330",
                    "dir": "西北风",
                    "sc": "6-7",
                    "spd": "34"
                }
            },
            "status": "ok",
            "suggestion": {
                "comf": {
                    "brf": "较舒适",
                    "txt": "白天天气晴好，您在这种天气条件下，会感觉早晚凉爽、舒适，午后偏热。"
                },
                "cw": {
                    "brf": "较不宜",
                    "txt": "较不宜洗车，未来一天无雨，风力较大，如果执意擦洗汽车，要做好蒙上污垢的心理准备。"
                },
                "drsg": {
                    "brf": "热",
                    "txt": "天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。"
                },
                "flu": {
                    "brf": "较易发",
                    "txt": "虽然温度适宜但风力较大，仍较易发生感冒，体质较弱的朋友请注意适当防护。"
                },
                "sport": {
                    "brf": "较适宜",
                    "txt": "天气较好，但风力较大，推荐您进行室内运动，若在户外运动请注意防风。"
                },
                "trav": {
                    "brf": "适宜",
                    "txt": "天气较好，风稍大，但温度适宜，是个好天气哦。适宜旅游，您可以尽情地享受大自然的无限风光。"
                },
                "uv": {
                    "brf": "强",
                    "txt": "紫外线辐射强，建议涂擦SPF20左右、PA++的防晒护肤品。避免在10点至14点暴露于日光下。"
                }
            }
        }
    ]
}
```
