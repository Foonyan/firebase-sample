# firebase-sample

###  Firebase CLIのインストール 
firebase CLIを用いるには、firebase-toolsを導入する必要がある。  
```
npm install -g firebase-tools
```

### プロジェクトセットアップ〜htmlの公開(デプロイ)まで    
コンテンツのデプロイは、firebase hostingを用いる  

1.firebaseにloginし、適当なプロジェクトを作成しておく。  


2.googleアカウントと紐付け  
```
firebase login  
```


3.プロジェクトの紐付け  
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
What do you want to use as your public directory? public

以降、publicフォルダの中のコンテンツが公開される。
```

```
Configure as a single-page app (rewrite all urls to /index.html)? (y/N) 

とりあえず、y
```


4.デプロイ
```
firebase deploy
```
成功の場合、URLが表示される。  
```
Hosting URL: https://*****.firebaseapp.com
```

5.みんなでいじるためには  
1.Project Overview -> ユーザと権限 で追加  
2.git でつつくコンテンツをclone     
3.firebase initで各自、アカウントとプロジェクトを紐付ける？   

### 参考サイト
firebaseは他に何ができるのか？
https://firebase.google.com/?hl=ja

