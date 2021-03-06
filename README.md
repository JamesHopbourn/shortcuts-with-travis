## Shortcuts with Travis-CI

## 配置教程
1. 申请 GitHub token
2. 下载这个 Shortcuts: [GitHub Repository Update](https://www.icloud.com/shortcuts/f8fa8b7b0b4e41098bfe0c071c1ed6f1)
3. 更改 Shortcuts 里面的仓库地址、token、committer 信息
4. fork 这个项目然后开始发挥你的想象力，爱玩什么玩什么

## 玩法
1. Shortcuts 推送网页链接，Travis-CI 归档网页后推送到 develop 分支（保存容易被和谐的文章）
2. ...暂时没想到

## curl 命令
```
curl -u "JamesHopbourn:token" -X PUT 'https://api.github.com/repos/JamesHopbourn/shortcuts-with-travis/contents/shortcuts.txt' -d '{"message": "my commit message3",  "committer": {"name": "james", "email": "jameshopbourn@gmail.com" }, "content": "bXkgdXBkYXRlZCBmaWxlIGNvbnRlbnRz", "sha": "fb617c9e42866ca24d0ff8e0c2725048f6f9530c"}'
```

更新内容使用 base64 编码后替换到 content  
sha 通过 API 获取  
```
curl https://api.github.com/repos/JamesHopbourn/shortcuts-with-travis/contents/shortcuts.txt|jq .sha|sed 's/"//g'|pbcopy
```
