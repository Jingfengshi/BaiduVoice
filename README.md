<h1 align="center"> baidu-voice </h1>

<p align="center">:rainbow: 基于百度语音接口 PHP 获取语音内容的信息组件</p>

[![Build Status](https://travis-ci.org/jingfengshi/baidu-voice.svg?branch=master)](https://travis-ci.org/jingfengshi/baidu-voice)
![StyleCI build status](https://github.styleci.io/repos/164062667/shield) 
## 安装

```shell
$ composer require jingfengshi/baidu-voice -vvv
```

## 使用
```shell
    use jingfengshi\BaiduVoice\AiSpeech;
    $appId='xxx';
    $appKey='xxx';
    $appSecret='xxx';
    $ai_speech=new AiSpeech($appId,$appKey,$appSecret);
    $res=$ai_speech->getContentFromVoice(file_get_contents(public_path().'/test.pcm'),'pcm',8000);
    dd($res)
```

## 在Laravel中使用
在laravel中使用也是同样的安装方式，配置写在 `config/service.php`中
```shell
    .
    .
    .
     'weather' => [
        'appId' => env('BAIDU_VOICE_API_ID'),
        'appKey' => env('BAIDU_VOICE_API_KEY'),
        'appSecret' => env('BAIDU_VOICE_API_SECRET'),
    ],

```
然后在 `.env`中配置`BAIDU_VOICE_API_ID`
```shell
BAIDU_VOICE_API_ID=xxxx
```
可以使用两种方式来获取  `jingfengshi\BaiduVoice\AiSpeech` 实例:

## 方法参数注入

```shell
  .
    .
    .
    public function edit(AiSpeech $aiSpeech) 
    {
        $response = $weather->getContentFromVoice(file_get_contents(public_path().'/test.pcm'),'pcm',8000);
    }
    .
    .
    .

```

## 服务名访问

```shell
 .
    .
    .
    public function edit() 
    {
        $response = app('AiSpeech')->getContentFromVoice(file_get_contents(public_path().'/test.pcm'),'pcm',8000);;
    }
    .
    .
    .

```

## Contributing

You can contribute in one of three ways:

1. File bug reports using the [issue tracker](https://github.com/jingfengshi/baidu-voice/issues).
2. Answer questions or fix bugs on the [issue tracker](https://github.com/jingfengshi/baidu-voice/issues).
3. Contribute new features or update the wiki.

_The code contribution process is not very formal. You just need to make sure that you follow the PSR-0, PSR-1, and PSR-2 coding guidelines. Any new code contributions must be accompanied by unit tests where applicable._

## License

MIT