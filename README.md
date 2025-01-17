# Get Latest Version

## Linux
api(dot)getfiddler(dot)com/linux/latest-linux

## Windows
api(dot)getfiddler(dot)com/win/latest

## NOTICE

If you are using windows, just try https://github.com/dnSpyEx/dnSpy
## get ilasm (ildasm)

1. dotnet new console -n test
2. cd test
3. dotnet add package Microsoft.NETCore.ILAsm (ILDAsm)
4. dotnet publish -c Release --self-contained --runtime linux-x64
5. export PATH=$(pwd)/bin/Release/netcoreapp3.1/linux-x64/publish:$PATH
6. ilasm (ildasm)

# for v4.6.1

## Patch

1. 下载Electron https://github.com/electron/electron/releases , 解压到`Electron`文件夹
2. 复制 `Fiddler Everywhere/resources` -> `Electron/resources`
3. 复制 `v4.6.1/Fiddler.WebUi/Fiddler.WebUi.dll` -> `Electron/resources/app/out/WebServer`
4. 复制 `v4.6.1/FiddlerBackendSDK/FiddlerBackendSDK.dll` -> `Electron/resources/app/out/WebServer`
5. 复制 `v4.6.1/server/file` -> `Electron/resources/app/out/file`

## 修改 main.js

1. 打开 `resources/app/out/main.js`
2. `v4.6.1/server/index.js` 的内容添加到 `resources/app/out/main.js` 开头

## 修改 main.xxx.js

1. 打开 `resources/app/out/WebServer/ClientApp/dist/main.xxx.js`
2. 替换所有 `https://api.getfiddler.com` 为 `http://127.0.0.1:5678/api.getfiddler.com`
3. 搜索并删除 `.then(c=>t.verifyResponse(c?.headers,c?.body))`

## Some Detail

[Let me see new](./v4.6.2/readme.md)

[Let me see old](./DETAIL.MD)

## 免责声明
	
本仓库仅供技术学习交流使用，如有下载相关文件，请在学习后24小时内删除相关内容。

请勿将本项目内容用于非法用途，使用者在使用时即视为对行为可能产生的任何不良后果负责。
	
由于传播、利用此工具所提供的信息而造成的任何直接或者间接的后果及损失，均由使用者本人负责，作者不为此承担任何责任。
