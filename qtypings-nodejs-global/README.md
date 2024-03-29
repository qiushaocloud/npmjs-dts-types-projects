NodeJS 环境定义一些全局接口、类型等

### 项目源码
* 自建 gitlab 地址: https://gitlab.qiushaocloud.top/qiushaocloud/npmjs-dts-types-projects
* github 地址: https://github.com/qiushaocloud/npmjs-dts-types-projects

### npm 包
* 安装 npm 包: `npm install --save-dev @types/qtypings-nodejs-global`

###  TS 定义
#### nodejs.d.ts
```typescript
declare namespace NodeJS {
    interface Global {
        [propName: string]: any;
    }
}
```

#### object.d.ts
```typescript
type QJson = Record<string, any>;

type QJsonT<T> = Record<string, T>;

type QJsonNumber = Record<number, any>

type QJsonNumberT<T> = Record<number, T>;
```

#### fn.d.ts
```typescript
/** 任意回调参数的回调函数 */
interface QFnAnyArgs{
    (... args:any[]):void;
}

/** 无回调参数的回调函数 */
interface QFnEmptyArgs{
    ():void;
}

/** 任意回调参数的回调函数, 返回类型T */
interface QFnAnyArgsReturnT<T>{
    (... args:any[]): T;
}

/** 是否成功回调函数 */
interface QFnIsSuccess{
    (isSuccess: boolean):void;
}

/** 是否成功回调函数, 第2个参数开始任意回调参数*/
interface QFnIsSuccessAnyArgs{
    (isSuccess: boolean, ...args: any[]):void;
}

/** 错误则无result，有result则无错误 */
interface QFnErrorOrResult{
    (err: Error | string | undefined, result?: any, ...args: any[]): void;
}

/** 错误描述回调 */
interface QFnErrorDesc{
    (errDesc: string): void;
}
```


#### 开源不易，如果对您有帮助，请您动一动您的小手，给作者点 Star，也请您多多关注分享者「[邱少羽梦](https://www.qiushaocloud.top)」

* 分享者邮箱: [qiushaocloud@126.com](mailto:qiushaocloud@126.com)
* [分享者博客](https://www.qiushaocloud.top)
* [分享者自己搭建的 gitlab](https://gitlab.qiushaocloud.top/qiushaocloud) 
* [分享者 gitee](https://gitee.com/qiushaocloud/dashboard/projects) 
* [分享者 github](https://github.com/qiushaocloud?tab=repositories) 
