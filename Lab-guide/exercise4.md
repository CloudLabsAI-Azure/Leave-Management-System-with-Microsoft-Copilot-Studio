# 演習 4: エンド ツー エンド テスト

### 推定所要時間: 40 分

## 概要

この演習では、さまざまなプロンプトとシナリオを実行してエージェントをエンド ツー エンドでテストします。テスト完了後は、休暇申請データが Dataverse テーブルに正しく更新されていることを確認します。

## 目標

次のタスクを完了できるようになります。

- タスク 1: 承認シナリオのテスト

- タスク 2: Dataverse のデータの検証

## タスク 1: 承認シナリオのテスト

このタスクでは、指定のプロンプトを使用してエージェントをエンド ツー エンドで実行し、応答の正確性を検証します。

1. エージェントの設定が完了したので、テストを行います。

1. 上部のメニュー バーで **[発行]** をクリックして、エージェントへの変更を保存して適用します。

   ![](../media/lev-mgmt-sb-ex4-g1.png)

1. **[このエージェントを発行する]** ダイアログ ボックスで、詳細を確認し、**[発行]** をクリックして発行プロセスを確認して完了します。

   ![](../media/lev-mgmt-sb-ex4-g2.png)

1. **[Leave Management Agent]** ページで、右上隅の **[テスト]** をクリックしてエージェントのテスト パネルを開きます。

   ![](../media/lev-mgmt-sb-ex4-g11.png)

1. **[エージェントのテスト]** パネルで、**Leave Management Agent** のテストを行います。

   ![](../media/lvimg57.png)

1. **[エージェントのテスト]** パネルで、チャット ボックスに **Hello (1)** (または類似のメッセージ) と入力し、**[送信] (2)** ボタンをクリックしてエージェントと話しかけます。

1. **[アクティビティ マップ]** ページで、**[挨拶]** トピックがトリガーされ、*Good afternoon*、*Good morning*、*Hello*、*Hey*、*Hi* などのフレーズが表示されることを確認します。

   ![](../media/leav-man-e4-g-33.png)

1. **[エージェントのテスト]** パネルで、**休暇を申請したい (1)** などのリクエストを入力し、**[送信] (2)** ボタンをクリックしてエージェントの休暇関連のクエリを処理する能力をテストします。

   ```
   I want to apply for Leave
   ```

   ![](../media/gs-fix2-leave2-may-g28.png)

1. **[エージェントのテスト]** パネルで、休暇の種類を選択するよう求められたら、**Casual**、**Emergency**、**Unpaid** などのオプションから選択します。

   ![](../media/lev-mgmt-sb-ex4-g6.png)

1. **[エージェントのテスト]** パネルで、必要な **yyyy-mm-dd** 形式で休暇開始日を入力し (例: **2026-04-06 (1)**)、**[送信] (2)** ボタンをクリックします。

   ```
   2026-05-13
   ```

1. **[エージェントのテスト]** パネルで、必要な **yyyy-mm-dd** 形式で休暇終了日を入力し (例: **2026-04-07 (1)**)、**[送信] (2)** ボタンをクリックします。

1. **[エージェントのテスト]** パネルで、休暇の理由を入力し (例: **家族の行事に出席する予定です (1)**)、**[送信] (2)** ボタンをクリックします。

   ```
   2026-05-14
   ```

   > **Note:** In this test scenario, we are validating a leave request for 2 days or less.

   ![](../media/gs-fix2-leave2-may-g21.png)

1. In the **Test your agent** panel, enter the reason for your leave using the below example value **(1)**, and then select the **Send (2)** button.

   ```
   I will be attending a family function
   ```

   ![](../media/gs-fix2-leave2-may-g22.png)

1. **[エージェントのテスト]** パネルで、承認された休暇日を示す確認メッセージがエージェントから返ってくることを確認します。

   ![](../media/leav-man-e4-g-31.png)

   > **注:** 接続するよう求めるプロンプトが表示される場合は、以下の手順を実行してください。

   > **[接続マネージャーを開く] (1)** をクリックして資格情報を確認します。

      ![](../media/gs-fix2-leave2-may-g23.png)
      
   > **[接続の管理]** ページで、**Leave Management Workflow** が **[接続なし] (1)** と表示される場合があります。**[接続] (2)** をクリックして接続を確立します。

      ![](../media/cor-mn-e5-g-43.png)

   > **[接続またはピック接続の作成]** ページで、使用可能な接続 **[標準承認] (1)** を選択し、**[送信] (2)** をクリックして接続セットアップを完了します。

      ![](../media/cor-mn-e5-g-44.png)

   > **[接続の管理]** ページで、**Leave Management Workflow** の状態が **[接続済み] (1)** と表示されていることを確認します。接続されたら、エージェントをテストしていた前のタブに戻って続けてください。

      ![](../media/cor-mn-e5-g-45.png)

   > 接続を確認した後、**[エージェントのテスト]** タブに戻ります。上部の **[更新] (1)** ボタンをクリックしてセッションを再読み込みし、リクエストを再試行してテストを続けてください。

   ![](../media/gs-fix2-leave2-may-g24.png)

1. **[エージェントのテスト]** パネルで、**[更新]** アイコンをクリックして会話を再開し、新しい入力でエージェントをテストします。

   ![](../media/gs-fix2-leave2-may-g25.png)

1. **[エージェントのテスト]** パネルで、チャット ボックスに **Hello (1)** (または類似のフレーズ) と入力し、**[送信] (2)** ボタンをクリックして挨拶意図をトリガーします。

   ```
   https://outlook.com
   ```

1. **[エージェントのテスト]** パネルで、チャット ボックスに **休暇を申請したい (1)** と入力し、**[送信] (2)** ボタンをクリックしてエージェントの休暇関連のクエリを処理する能力をテストします。

   - Username: <inject key="AzureAdUserEmail"></inject>
   - Temporary Access Key: <inject key="AzureAdUserPassword"></inject>

      ![](../media/gs-fix2-leave2-may-g33.png)

1. In the **Test** pane, select **New test session** to test leave requests for more than 2 days.

   ![](../media/gs-fix2-leave2-may-g26.png)

1. In the message box, enter **Hello (1)**, and then select the **Send (2)** icon.

   ![](../media/gs-fix2-leave2-may-g27.png)

1. In the **Test your agent** panel, enter the below request in the message box **(1)**, and then select the **Send (2)** button to test the agent.

   ```
   I want to apply for Leave
   ```

   ![](../media/gs-fix2-leave2-may-g28.png)

1. **[エージェントのテスト]** パネルで、休暇の種類を選択するよう求められたら、**Casual**、**Emergency**、**Unpaid** などのオプションから選択します。

   ![](../media/lev-mgmt-sb-ex4-g6.png)

1. **[エージェントのテスト]** パネルで、必要な **yyyy-mm-dd** 形式で休暇開始日を入力し (例: **2025-09-20 (1)**)、**[送信] (2)** ボタンをクリックします。

   ```
   2026-05-13
   ```

1. **[エージェントのテスト]** パネルで、**yyyy-mm-dd** 形式で休暇終了日を入力し、開始日から 2 日以上後の日付にするようにしてください (例: **2025-09-25 (1)**)。**[送信] (2)** ボタンをクリックして申請を送信します。

1. In the **Test your agent** panel, enter the leave end date in the required **yyyy-mm-dd** format using the below example value **(1)**, and then select the **Send (2)** button.

1. **[エージェントのテスト]** パネルで、休暇を申請する理由を入力し (例: *個人的な理由で短い休暇が必要です* (1))、**[送信] (2)** ボタンをクリックして続けます。

   > **Note:** In this test scenario, we are validating a leave request for more than 2 days.

1. ブラウザーを開いて [https://outlook.com](https://outlook.com) に移動して Outlook にアクセスします。

1. **[受信トレイ]** で、件名 **Microsoft Power Automate - Leave Approval** のメールを見つけてクリックし、休暇申請の詳細を確認します。

   ```
   I need to take leave for personal work
   ```

1. **[Leave Approval]** メールで **[承認]** をクリックして休暇申請を承認します。

1. Verify that the agent shows the **Processing** status while waiting for the email approval response.

1. **[コメント] (1)** ボックスに承認メモ (例: *Approved*) を入力し、**[送信] (2)** をクリックして休暇承認を確定します。

1. In the **Inbox (1)**, select the **Microsoft Power Automate - Leave Approval (2)** email to view the leave request details.

   ![](../media/gs-fix2-leave2-may-g31.png)

1. Select **Approve (1)**, enter *Approved* in the **Comments (2)** box, and then select **Submit (3)** to finalize the leave approval.

   ![](../media/gs-fix2-leave2-may-g32.png)

1. エージェントが休暇申請を確認し、休暇期間の詳細を表示する承認メッセージを返します。

   ![](../media/gs-fix2-leave2-may-g34.png)

## タスク 2: Dataverse のデータの検証

このタスクでは、Dataverse に移動してエージェントによって更新されたデータを検証します。

1. **Copilot Studio** ページで、左側のナビゲーション パネルから **[その他のオプション] (1)** メニューをクリックし、**[Power Platform]** セクションの **[Power Apps] (2)** を選択して移動するか、新しいブラウザー ウィンドウで [https://make.powerapps.com](https://make.powerapps.com) に移動します。

   ![](../media/cor-mn-e4-g-10.png)

1. **Power Apps** ポータルで、環境が **ODL_User (1)** に設定されていることを確認します。左側のナビゲーション メニューから **[テーブル] (2)** を選択し、リストから **[Leave Request] (3)** を選択します。

   ![](../media/cor-mn-e4-g-7.png)

1. **[Leave Request 列とデータ]** ページで、新しく追加されたレコードを確認します。次のフィールドを確認してください。
      - **[従業員のメールアドレス]** と **[従業員名]** は自動的にユーザーの詳細で入力されます。
      - **[休暇の種類]** は選択した休暇の種類を反映します。
      - **[開始日]** と **[終了日]** はテスト中に入力した値と一致します。
      - **[期間]** は計算された休暇日数を表示します。
      - **[ステータス]** は現在の承認状態を表示します。

         ![](../media/cor-mn-e4-g-11.png)  

         ![](../media/cor-mn-e4-g-9.png)

         > **注:** **[従業員のメールアドレス/ユーザー ID]** フィールドは、ログイン コンテキストからシステムによって自動的に取得されます。手動で入力する必要はありません。

## まとめ

この演習では、さまざまなプロンプトとシナリオを実行してエージェントをエンド ツー エンドでテストしました。テスト完了後は、休暇申請データが Dataverse テーブルに正しく更新されていることを確認しました。

### この演習を正常に完了しました。次の演習に進んでください >>

   ![](../media/a-gs-g5.png)
