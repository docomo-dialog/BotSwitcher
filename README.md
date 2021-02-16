# BotSwitcher
BotSwitcherは対話を行っているボットIDの登録と、取得ができます。  
複数ボットで対話を行う際のボットの切り替えにご活用ください。

BotSwitcherdではボットIDを保持する時間に有効期限を設けています。  
有効期限はボットプロパティのキーに "time"、値に秒数を指定することで設定できます。  
ボットプロパティで設定していない場合は60秒になります。  
<br/>
## 利用手順
1. ボットID「BotSwitcher」でボットを作成  
   ボット編集にて"公開"をglobalもしくはpublicに設定
2. BotSwitcherボットにBotSwitcher.aimlを追加しデプロイ
3. 他のボットからsraixタグでBotSwitcherボットを呼び出す  

<br/>

## 関数詳細
### ボットID登録
###### 関数 : #SET botId
```
<sraix botid="(プロジェクト名)_BotSwitcher">#SET TestBot</sraix>
```
ボットIDを登録します。  
"botId" には登録するボットIDを指定してください。  
有効期限は登録した時点からカウントが開始します。  
<br/>
### ボットID取得
###### 関数 : #GET
```
<sraix botid="(プロジェクト名)_BotSwitcher">#GET</sraix>
```
登録されているボットIDを取得します。  
ボットIDが登録されていない場合はNOTFOUND、有効期限が切れている場合はEXPIREDが返却されます。  
ボットIDが取得できた場合は有効期限のカウントがリセットされます。  
<br/>
### 初期化
###### 関数 : #CLEAR
```
<sraix botid="(プロジェクト名)_BotSwitcher">#CLEAR</sraix>
```
登録されているボットIDを破棄します。  
<br/>
### 有効期限の検証
###### 関数 : #check expire
```
<sraix botid="(プロジェクト名)_BotSwitcher">#check expire</sraix>
```
登録されているボットIDの有効期限を検証します。  
有効期限が切れていない場合はSTILL ALIVE、有効期限が切れている場合はEXPIRED、ボットIDが登録されていない場合はNOTFOUNDが返却されます。

test
