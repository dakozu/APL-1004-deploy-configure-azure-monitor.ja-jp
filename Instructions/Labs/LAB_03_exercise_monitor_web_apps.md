---
lab:
  title: 演習 - Web アプリを監視する
  module: Guided Project - Deploy and configure Azure Monitor
---

## スキル タスク

- Application Insights を有効にする
- NET Core スナップショット デバッガーのログを無効にします。
- Log Analytics ワークスペースに書き込まれる Web アプリの HTTP ログを構成する
- タスク 4: Log Analytics ワークスペースに書き込まれる SQL Insights データを構成する
- Web Apps のファイルと構成の Change Tracking を有効にする

## 演習の手順

### Application Insights を有効にする

1. Azure portal の検索バーで、「**rg-alpha**」と入力し、結果の一覧から **[rg-alpha]** を選択します。
1. リソース グループ内の項目の一覧から、**SQL Database を使用する Web アプリの App Services** を選択します。
1. **[設定]** で **[Application Insights]** を選択します。
1. **[Application Insights]** ページで、**[Application Insights を有効にする]** を選択します。
1. **[Application Insights]** ページで、**[新しいリソースの作成]** が選択されていること、Log Analytics ワークスペースが **[ LogAnalytics1]** に設定されていることを確認し、**[適用]** を選択します。
1. **[監視設定の適用]** ダイアログで、**[はい]** を選択します。

### NET Core スナップショット デバッガーのログを無効にします。

1. Azure portal の検索バーで、「**rg-alpha**」と入力し、結果の一覧から **[rg-alpha]** を選択します。
1. リソース グループ内の項目の一覧から、**SQL Database を使用する Web アプリの App Services** を選択します。
1. **[設定]** で **[Application Insights]** を選択します。
1. **[アプリケーションのインストルメント化]** で 、**[.NET Core]** を選択し、[スナップショット デバッガー] 設定を **[オフ]** に設定します。 **適用** を選択します。
1. **[監視設定の適用]** ダイアログ ボックスで、**[はい]** を選択します。

    | プロパティ | 値    |
    |:---------|:---------|
    | 診断設定の名前  | httplogs   |
    | カテゴリ    | HTTP ログ  |
    | 宛先の詳細   | Log Analytics ワークスペースに送信する  |
    | サブスクリプション  | 該当するサブスクリプション  |
    | Log Analytics ワークスペース   | LogAnalytics1   |

### Log Analytics ワークスペースに書き込まれる Web アプリの HTTP ログを構成する

1. Azure portal の検索バーで、「**rg-alpha**」と入力し、結果の一覧から **[rg-alpha]** を選択します。
1. リソース グループ内の項目の一覧から、**SQL Database を使用する Web アプリの App Services** を選択します。
1. **[監視]** の **[診断設定]** を選択します。
1. **[診断設定]** ページで、**[診断設定の追加]** を選択します。
1. **[診断設定]** ページで、次を選択し、**[保存]** を選択します。

    | プロパティ | 値    |
    |:---------|:---------|
    | 診断設定の名前  | httplogs   |
    | カテゴリ    | HTTP ログ  |
    | 宛先の詳細   | Log Analytics ワークスペースに送信する  |
    | サブスクリプション  | 該当するサブスクリプション  |
    | Log Analytics ワークスペース   | LogAnalytics1   |

### タスク 4: Log Analytics ワークスペースに書き込まれる SQL Insights データを構成する

1. Azure portal の検索バーで、「**rg-alpha**」と入力し、結果の一覧から **[rg-alpha]** を選択します。
1. リソース グループ内の項目の一覧から、サンプル SQL Database を選択します。
1. **[監視]** の **[診断設定]** を選択します。
1. **[診断設定]** ページで、**[診断設定の追加]** を選択します。
1. **[診断設定] ページ**で、次の情報を入力し、**[保存]** を選択します。

    | プロパティ | 値    |
    |:---------|:---------|
    | 診断設定の名前  | InsightLogAnalytics   |
    | カテゴリ    | SQL Insights  |
    | 宛先の詳細   | Log Analytics ワークスペースに送信する  |
    | サブスクリプション  | 該当するサブスクリプション  |
    | Log Analytics ワークスペース   | LogAnalytics1   |

### Web Apps のファイルと構成の Change Tracking を有効にする

1. Azure portal の検索バーで、「**rg-alpha**」と入力し、結果の一覧から **[rg-alpha]** を選択します。
1. リソース グループ内の項目の一覧から、AzureLinuxAppWXYZ-webapp を選択します。
1. **[問題の診断と解決]** を選択します。
1. [検索] ダイアログ ボックスに、「**アプリケーションの変更**」と入力します。
1. **[変更分析]** ページで、**[構成]** を選択します。
1. **[ファイルと構成変更の追跡を有効にする]** ページで、[状態] スライダーを **[オン]** に変更し、**[保存]** を選択します。
