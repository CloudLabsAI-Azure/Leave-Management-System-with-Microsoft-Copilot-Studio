# 演習 5: 発行と共有

### 推定所要時間: 40 分

## 概要

この演習では、**Leave Management Agent** を Microsoft Teams に発行してその機能を検証する方法を学習します。まず Copilot Studio で Teams チャネルを有効にして発行プロセスを完了します。デプロイ後、Microsoft Teams でエージェントと対話し、休暇申請を送信して、エージェントが正しく応答し、承認ワークフローが機能することを確認します。

## 目標

次のタスクを完了できるようになります。

- タスク 1: Microsoft Teams へのエージェントのデプロイと発行
- タスク 2: Microsoft Teams でのデプロイ済みエージェントのテスト

## タスク 1: Microsoft Teams へのエージェントのデプロイと発行

このタスクでは、Copilot Studio で Teams チャネルを有効にして **Leave Management Agent** を Microsoft Teams に発行します。発行設定を構成し、エージェントを利用可能にして、Teams 環境内で正常にインストールされてアクセスできることを確認します。

1. エージェントの設定が完了したので、さまざまなプラットフォームで使用できるように発行します。

1. **[Leave Management Agent]** ページで、**[チャネル] (1)** タブを選択し、[Microsoft チャネル] の下にある **[Teams と Microsoft 365 Copilot] (2)** をクリックします。

   ![](../media/gs-fix2-leave2-may-g36.png)

1. **[エージェントを Microsoft 365 Copilot で利用可能にする] (1)** チェックボックスをオフにして、**[チャネルの追加] (2)** を選択します。

   ![](../NewMedia/e5t1s2.png)

1. チャネルが追加されたら、**[Microsoft Teams]** で **[Teams でエージェントを表示する]** を選択して Microsoft Teams でエージェントを開きます。

   ![](../NewMedia/e5t1s3.png)

1. **[Teams デスクトップ アプリとのより良い接続を維持]** ページで、**[代わりに Web アプリを使用する]** をクリックしてブラウザーで続行します。

   ![](../NewMedia/e5t1s4.png)

1. Microsoft Teams の **[Leave Management Agent]** ページで、**[追加]** をクリックしてエージェントをインストールします。**[追加]** オプションが表示されない場合は、Copilot Studio に戻り、もう一度 **[Teams でエージェントを表示する]** を使用してください。

   ![](../NewMedia/e5t1s5.png)

1. エージェントが正常に追加されたら、**[開く]** をクリックして Teams で **Leave Management Agent** を起動します。

   ![](../NewMedia/e5t1s6.png)

1. **Leave Management Agent** のチャット ウィンドウで、メッセージ ボックスに **Hello (1)** と入力し、**[送信] (2)** ボタンをクリックして会話を開始します。

   ![](../NewMedia/e5t1s7.png)

## タスク 2: Microsoft Teams でのデプロイ済みエージェントのテスト

このタスクでは、Microsoft Teams でデプロイ済みの **Leave Management Agent** を、休暇申請を送信して必要な詳細を提供し、承認結果を確認することでテストします。

1. **Leave Management Agent** のチャット ウィンドウで、メッセージ ボックスに **I want to apply for leave (1)** と入力し、**[送信] (2)** ボタンをクリックして会話を続けます。

   ![](../NewMedia/e5t1s8.png)

1. **Leave Management Agent** のチャット ウィンドウで、休暇の種類を選択するよう求められたら、オプションの 1 つを選択します。

   ![](../NewMedia/e5t1s9.png)

1. **Leave Management Agent** のチャットで、必要な **yyyy-mm-dd** 形式で休暇開始日を入力します (例: **2025-09-20 (1)**)。**[送信] (2)** ボタンをクリックして続行します。

   ![](../NewMedia/e5t1s10.png)

1. **Leave Management Agent** のチャットで、必要な **yyyy-mm-dd** 形式で休暇終了日を入力します (例: **2025-09-27 (1)**)。**[送信] (2)** ボタンをクリックして送信します。これにより、合計休暇期間が 2 日を超えることが保証されます。

   ![](../NewMedia/e5t1s11.png)

1. **Leave Management Agent** のチャットで、休暇の理由を入力します (例: **Need a break to play video games (1)**)。**[送信] (2)** ボタンをクリックして続行します。

   ![](../NewMedia/e5t1s12.png)

1. **Microsoft Power Automate (1)** からの **[休暇承認]** メールで、**[拒否] (2)** をクリックし、**[コメント] (3)** フィールドに拒否の理由を入力して、**[送信] (4)** をクリックして確認します。

   ![](../NewMedia/e5t1s19.png)

   > **注:** 接続を求めるプロンプトが表示された場合は、以下の手順を実行してください。

   > **[接続マネージャーを開く] (1)** をクリックして資格情報を確認します。

      ![](../NewMedia/e5t1s13.png)
      
   > **[接続の管理]** ページで、**Leave Management Workflow** が **[未接続] (1)** と表示される場合があります。**[接続] (2)** をクリックして接続を確立します。

      ![](../NewMedia/e5t1s14.png)

   > **[接続の作成または選択]** ページで、利用可能な接続 **[Standard approvals] (1)** を選択し、**[送信] (2)** をクリックして接続の設定を完了します。

      ![](../NewMedia/e5t1s15.png)

   > **[接続の管理]** ページで、**Leave Management Workflow** のステータスが **[接続済み] (1)** と表示されていることを確認します。接続後、エージェントをテストしていた前のタブに戻って続行します。

      ![](../NewMedia/e5t1s18.png)

1. **[エージェントのテスト]** タブに戻り、**[再試行]** を選択します。

   ![](../NewMedia/e5t1s17.png)

1. Microsoft Teams で **[アクティビティ] (1)** セクションに移動し、**[Leave Approval] (2)** 通知を確認して申請の最終ステータスを確認します。

   ![](../NewMedia/e5t1s16.png)

## まとめ

この演習では、**Leave Management Agent** を Microsoft Teams に正常に発行し、Teams 環境内でアクセスして使用できることを確認しました。休暇申請を送信し、必要な詳細を提供して、Power Automate を通じた自動承認プロセスを観察することでエージェントをテストしました。これにより、実際のユーザー シナリオでのエージェントのデプロイと機能的な動作の両方が検証されました。

### ラボを正常に完了しました！
