---
lab:
  title: 演習 - Log Analytics をデプロイする
  module: Guided Project - Deploy and configure Azure Monitor
---

## スキル タスク

- Log Analytics ワークスペースを作成する
- Log Analytics のデータ保持とアーカイブのポリシーを構成します。
- Log Analytics ワークスペースへのアクセスを有効にします。

## 演習の手順

### Log Analytics ワークスペースを作成する

1. Azure portal の検索バーに「**Log analytics**」と入力し、結果から **[Log Analytics ワークスペース]** を選択します。
1. **[Log Analytics ワークスペース]** ページで、**[作成]** を選択します。
1. Log Analytics ワークスペース ウイザードの **[基本]** ページで、次の情報を入力し、**[確認と作成]** を選択します。
   
    | プロパティ | 値    |
    |:---------|:---------|
    | サブスクリプション  | 該当するサブスクリプション   |
    | リソース グループ    | rg-alpha  |
    | 名前  | LogAnalytics1  |
    | リージョン    | 米国東部  |

4. 情報を確認し、**[作成]** を選択します。

### Log Analytics のデータ保持とアーカイブのポリシーを構成します。

1. Azure portal の検索バーに「**Log analytics**」と入力し、結果から **[Log Analytics ワークスペース]** を選択します。
1. **[Log Analytics ワークスペース]** ページで、**[LogAnalytics1]** を選択します。
1. LogAnalytics1 の **[Log Analytics ワークスペース]** ページで、**[使用量と推定コスト]** を選択します。
1. **[データ保有期間]** を選択し、スライダーを 60 日に設定します。 **OK** を選択します。
1. LogAnalytics1 の **[Log Analytics ワークスペース]** ページで、**[使用量と推定コスト]** を選択します。
1. **[日次上限]** を選択します。 **[オン]** を選択します。 日次上限を 10 GB に設定し、**[OK]** を選択します。

### Log Analytics ワークスペースへのアクセスを有効にします。

1. Azure portal の検索バーに「**Log analytics**」と入力し、結果から **[Log Analytics ワークスペース]** を選択します。
1. **[Log Analytics ワークスペース]** ページで、**[LogAnalytics1]** を選択します。
1. **[アクセス制御 (IAM)]** を選択します。
1. **[追加]**、次に **[ロールの割り当ての追加]** の順に選択します。
1. ロールの一覧で、**[Log Analytics 閲覧者]** を選択し、**[次へ]** を選択します。
1. **[メンバー]** ページで、**[メンバーの選択]** を選択し、[XXXXXXXX-AppLogExaminers] (※) セキュリティ グループを選択します。 **[選択] を選びます**。
   **※ 選択するグループ名のXXXXXXXXはラボ環境にアクセスするために使っているユーザーアカウントの LabUser- の後に続く8桁の数字に置き換えてください**
1. **[メンバー]** 領域で、**[確認と割り当て]** を選択します。
