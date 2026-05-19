# 演習 5: 発行と共有

### 推定所要時間: 40 分

## 概要

この演習では、**Leave Management Agent** を Microsoft Teams に発行して展間する方法を学びます。Teams 内でエージェントをテストし、犬察集と休暇申請プロセスが期待どおり機能することを確認します。

## 目標

次のタスクを完了できるようになります。

- タスク 1: Microsoft Teams への展間と発行

- タスク 2: Microsoft Teams での発行済みエージェントのテスト

## タスク 1: Microsoft Teams への展間と発行

このタスクでは、Copilot Studio のチャンネル設定を使用して **Leave Management Agent** を Microsoft Teams に発行します。

1. **[Leave Management Agent]** ページで、**[チャンネル] (1)** タブを選択し、**[Teams および Microsoft 365 Copilot] (2)** チャンネルに移動します。

   ![](../media/leav-man-e4-g-2.png)

1. **[Teams および Microsoft 365 Copilot]** ページで、**[エージェントを Microsoft 365 Copilot で使用可能にする]** を有効化して全体の展間区域を増やすか、ページ 下部の **[チャンネルの追加] (1)** ボタンをクリックして続けます。

   ![](../media/leav-man-e4-g-3.png)

1. **[発行の準備ができましたか?]** ダイアログで、**[発行] (1)** をクリックしてエージェントを Teams 向けに公開します。

   ![](../media/leav-man-e4-g-4.png)

1. 選択した Teams チャンネル内でエージェントを表示するリンクを確認します。

   ![](../media/leav-man-e4-g-5.png)

1. **[Microsoft Teams を開く]** ポップアップが表示された場合は、**[キャンセル] (1)** をクリックしてデスクトップ アプリを開かずに進めます。

   ![](../media/leav-man-e4-g-6.png)

1. **[代わりに Web アプリを使用]** リンクをクリックして、ブラウザー ベースの Teams で続けます。

   ![](../media/leav-man-e4-g-7.png)

1. Teams アプリ ストアでエージェントのページを確認し、**[追加] (1)** をクリックして **Leave Management Agent** を追加します。

   ![](../media/leav-man-e4-g-12.png)

1. Teams 内で **[Leave Management Agent] (1)** を開きます。

   ![](../media/leav-man-e4-g-13.png)

1. チャット ボックスに **Hello (1)** と入力し、**[送信] (2)** ボタンをクリックしてエージェントと会話を開始します。

   ![](../media/cor-mn-e4-g-19.png)

## タスク 2: Microsoft Teams での発行済みエージェントのテスト

このタスクでは、Microsoft Teams 内で **Leave Management Agent** に休暇申請を展間し、展間済みのエージェントをテストします。

1. **[Leave Management Agent]** チャットで、チャット ボックスに **休暇を申請したい (1)** と入力し、**[送信] (2)** ボタンをクリックして休暇申請フローを開始します。

   ![](../media/cor-mn-e4-g-12.png)

1. エージェントから休暇の種類を選択するよう求められたら、希望の休暇の種類を選択します。

   ![](../media/cor-mn-e4-g-13.png)

1. エージェントから開始日を入力するよう求められたら、**yyyy-mm-dd** 形式で入力します (例: **2025-09-20 (1)**).

   ![](../media/cor-mn-e4-g-14.png)

1. エージェントから終了日を入力するよう求められたら、**yyyy-mm-dd** 形式で入力します (例: **2025-09-27 (1)**).

   ![](../media/cor-mn-e4-g-15.png)

1. エージェントから申請の理由を入力するよう求められたら、理由を入力します (例: **Need a break to play video games (1)**).

   ![](../media/cor-mn-e4-g-16.png)

1. **Microsoft Power Automate** からの Leave Approval メールで、**[拒否] (1)** をクリックし、拒否の理由を入力し (例: *仲間が休暇を取るので遊びに行くのは許可できません* (2))、**[送信] (3)** をクリックします。

   ![](../media/cor-mn-e4-g-20.png)

1. Teams の **[アクティビティ]** セクションを確認して、**Leave Management Agent** から Leave Approval 通知が届いていることを確認します。

   ![](../media/cor-mn-e4-g-21.png)

## まとめ

この演習では、**Leave Management Agent** を Microsoft Teams に発行し、Teams 内でエージェントをテストしました。休暇申請フローが期待どおり機能すること、および承認プロセスの辺りでエージェントが正しく応答することを確認しました。

### ラボを正常に完了しました！
