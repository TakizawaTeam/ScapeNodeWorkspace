## Re:CREATORS
```
想像力から生み出された可能性は本来独立する。
可能性から想像力が生まれる事で、二次創作の連鎖反応が生まれる。
今の事象を君がまだ疑うのなら、次に疑うのは・・・
```

## ScapeNodeWorkspace
#### 起動方法
1. npm run init #初期化
2. npm run start #起動
3. [control] + [c] #停止

#### 使い方①：Web画面で操作
> 起動した状態で以下にアクセスする<br/>
> http://localhost:5001/workspace/index.html<br/>
> 画面上でノード管理を行うか、画面下のwebターミナルで直接操作を行う<br/>
> webターミナルのCONNECTボタンを押し操作する。※トップレベルのawaitは省略可<br/>

```
checkin("Database");
change("user");
child();
```

#### 使い方②：ChromeのDeveloperToolsのConsoleタブから
```
(async ()=>{
  const server = new WebSocket(`ws://localhost:5001/repl`);
  await server.ask(`checkin("Database");`);
  const nodes = await server.ask(`child();`);
  console.log(nodes);
})();
```
