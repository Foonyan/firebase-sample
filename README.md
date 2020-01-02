# firebase-sample

Vueの環境を構築し、Firebaseにデプロイするまでの一連の流れをまとめたREADME
注意 node.jsを導入し、npmコマンドが使用できることが前提 

## Vue
### 環境構築   
vue-cliを導入する.     
vue-cliを用いてvueプロジェクトの作成やbuildを行う.  
```
npm i vue-cli -g
```

### プロジェクトの作成  
```
vue init webpack ＜プロジェクト名＞
```

初期の設定はデフォルトで良いと思われる。  
```
? Project name <プロジェクト名>
? Project description A Vue.js project
? Author *** <e-mail@e-mail.com>
? Vue build (Use arrow keys)
```

レコメンドされている方で。　　
```
? Vue build (Use arrow keys)
❯ Runtime + Compiler: recommended for most users 
  Runtime-only: about 6KB lighter min+gzip, but templates (or any Vue-
specific HTML) are ONLY allowed in .vue files - render functions are r
equired elsewhere 
```

router機能はこの先必要になるはず。  
```
? Install vue-router? (Y/n) Y
```

ESLintはソースコード検証ツールで、必ず必要なものではない。  
```
? Use ESLint to lint your code? (Y/n) n
```

Testモジュールは、とりあえず今は必要ない。  
```
? Set up unit tests (Y/n) n

? Setup e2e tests with Nightwatch? (Y/n) n
```

安定のnpmで。 
以上でプロジェクト作成は終了。 
```
? Should we run `npm install` for you after the project has been creat
ed? (recommended) (Use arrow keys)
❯ Yes, use NPM 
  Yes, use Yarn 
  No, I will handle that myself 
```

### 動作チェック・デバックのやりかた
作成されたプロジェクトの動作チェック。  
ローカルで開発する際のデバックとしてもこれからお世話になるはず。  
```
npm run dev
```
うまく動作すれば、以下のURLで作成したページにアクセスできる。  
```
http://localhost:8081
```
プロジェクトのbuildは以下のコマンドで行う。  
```
npm run build
```
distフォルダにbuild結果が格納される。  



## Firebase
###  環境構築 
事前準備 firebaseにloginし、プロジェクト追加を選択。
適当なプロジェクトを作成しておく。  
```
https://console.firebase.google.com/?hl=ja
```

firebase CLIを用いるには自分のローカル環境に、
firebase-toolsを導入する必要がある。  
実行できない場合は、自分のnode.jsなどを確認。  
```
npm install -g firebase-tools
```
ターミナルから、googleアカウントと紐付けを行う。    
```
firebase login  
```


### プロジェクトセットアップ〜Vueプロジェクトの公開(デプロイ)まで    
先程作成したVueプロジェクトのフォルダへ移動し、
firebaseと連結させる。   
```
firebase init
```

今回はコンテンツを公開するため、hosting
```
Which Firebase CLI features do you want to set up for this folder? Press Spac
e to select features, then Enter to confirm your choices. (Press <space> to sel
ect, <a> to toggle all, <i> to invert selection)

? Which Firebase CLI features do you want to set up for this folder? Press Spac
e to select features, then Enter to confirm your choices. (Press <space> to sel
ect, <a> to toggle all, <i> to invert selection)
 ◯ Database: Deploy Firebase Realtime Database Rules
 ◯ Firestore: Deploy rules and create indexes for Firestore
 ◯ Functions: Configure and deploy Cloud Functions
❯◯ Hosting: Configure and deploy Firebase Hosting sites
 ◯ Storage: Deploy Cloud Storage security rules
 ◯ Emulators: Set up local emulators for Firebase features
```

```
First, let's associate this project directory with a Firebase project.
You can create multiple project aliases by running firebase use --add, 
but for now we'll just set up a default project.  
Please select an option: (Use arrow keys)  

❯ Use an existing project 
  Create a new project 
  Add Firebase to an existing Google Cloud Platform project 
  Don't set up a default project 
```
```
? Select a default Firebase project for this directory: foonyansample (FoonyanSa
mple)

作成したプロジェクトを選択する。
```

```
What do you want to use as your public directory? dist

firebaseにデプロイするコンテンツが格納されているフォルダの選択。  
デフォルトはpublicフォルダになっているが、
Vueはbuild結果がdistフォルダに格納されるため、
デプロイするフォルダはdistに設定する事。  
```

```
Configure as a single-page app (rewrite all urls to /index.html)? (y/N) 

とりあえず、y
```


デプロイ
```
firebase deploy
```
成功の場合、URLが表示される。  
```
Hosting URL: https://*****.firebaseapp.com
```

## 一連の流れ  
vueをbuild→デプロイが一連の流れになる。  
```
npm run build
firebase deploy
```



### 参考サイト
firebaseは他に何ができるのか？
https://firebase.google.com/?hl=ja

