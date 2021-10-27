# 団体の企画データについて

```json
{
    "id": "",//団体のID、URLに使用、ファイル名と同一にする
    "name": "",//表示する団体名
    "description": "",//団体紹介文
    //団体のSNS等のリンク
    // 複数のTwitterアカウントを掲載する団体がいたため配列形式
    "sns": [
        {
            //サービス名
            // Twitter、Instagram、YouTube、Facebookのいずれかを指定すると、対応するclassが指定され色がつくようにする
            "service": "ウェブサイト",
            "url": ""
        },
        {
            "service": "Twitter",
            "url": ""
        },
        {
            "service": "Instagram",
            "url": ""
        },
        {
            "service": "YouTube",
            "url": ""
        }
    ],
    // 以下、出店形態ごとの情報
    // 出展の有無と'stage'、"exhibition","interaction","store"というプロパティの存在有無は常に対応されている状態にする。
    // （出展しない場合は空のプロパティを残さず、削除する。）
    // ステージライブ配信
    "stage": {
        "title": "",
        "description": "",
        "url": "",
        // プレミア公開する時刻（31日のみのため日付不要）
        // hh:mmのフォーマットで指定
        "premiereTime": ""
    },
    // 教室ライブ配信・展示
    "exhibition": {
        "title": "",
        "description": "",
        // URLが複数ある場合があるため配列指定
        "contents": [
            {
                // 使用サービス
                "service": "",
                "url": "",
                // 日時の指定がある場合のみm月d日(曜日)の形で指定する。2日間に渡る場合は「m月d日(曜日)・m月d日(曜日)」と表記
                // 
                // ない場合でもdate,timeプロパティを削除しない（空白で残す）
                "date":"",
                // 時刻はhh:mm形式
                "time": ""
            }
        ]
    },
    "interaction": {
        "title": "",
        "description": "",
        "contents": [
            {
                "title": "",
                "url": "",
                "time": "",
                // 参加者向けの案内
                "announce": ""
            }
        ]
    },
    "store": {
        "title": "",
        "description": "",
        "store": ""
    }
}

```