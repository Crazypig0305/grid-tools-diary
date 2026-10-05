---
title: "Microsoft Authenticator 備份改了：iPhone 改用 iCloud、Android 2027 年改 Google 備份，換手機前先做這三件事"
date: 2026-10-05
lastmod: 2026-10-05
description: "Microsoft Authenticator 的 iPhone 版已改用 iCloud 備份、App 裡找不到備份開關；Android 版 2027 年 1 月起改用 Google 備份。iPhone 和 Android 之間的備份不能互相還原。本文整理換手機前要先做的三件事、跨平台換機怎麼重新綁定，以及改 Google 備份後會不會吃 15 GB 空間。"
categories: ["privacy"]
tags: ["Microsoft Authenticator", "2FA", "雙因素驗證", "換手機", "資安"]
draft: false
---

> 📅 原文發布：2026 年 10 月｜最後更新：2026 年 10 月
> 本文內容已於 2026 年 10 月 5 日逐項對照 [微軟說明頁〈在 Microsoft Authenticator 中備份您的帳戶〉](https://support.microsoft.com/zh-tw/authenticator/back-up-your-accounts-in-microsoft-authenticator)、[〈還原帳戶認證〉](https://support.microsoft.com/en-us/authenticator/restore-account-credentials-from-microsoft-authenticator)、[Microsoft Learn 換機文件](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-transfer-authenticator-new-phone)與 App Store 台灣區頁面校對。
> 備份規則隨 App 版本調整，換機前建議再到微軟說明頁確認一次。

直接說結論：**Microsoft Authenticator 的備份已經跟著手機系統走了。** iPhone 版改用 iCloud 備份，App 裡原本的「雲端備份」開關被拿掉，要到 iPhone 的 iCloud 設定裡開；Android 版目前仍用 Microsoft 個人帳號備份，但微軟說明頁寫明 2027 年 1 月起改從 Google One 備份啟用。兩邊的備份不能互通：iPhone 備份的帳號還原不到 Android 手機上，反過來也一樣。

所以換手機前要分兩種情況處理。同平台換機（iPhone 換 iPhone、Android 換 Android），先確認舊手機的備份真的開著、公司帳號準備重新登入、舊手機留到全部驗證過再清；跨平台換機，備份幫不上忙，每個帳號都要在新手機重新綁定。下面依序拆解。

---

## Microsoft Authenticator 備份改了什麼

| 項目 | iPhone（iOS）| Android（現在）| Android（2027 年 1 月起）|
|---|---|---|---|
| 備份存在哪 | iCloud（需開 iCloud 雲碟、iCloud 鑰匙圈、iCloud 備份）| Microsoft 個人帳號 | Google One 備份 |
| 在哪裡開 | iPhone「設定」→ iCloud →「儲存至 iCloud」裡的 Authenticator | App 內 設定 →「雲端備份」 | 從 Google One 備份啟用「Microsoft Authenticator」|
| 需不需要 Microsoft 個人帳號 | 不需要 | 需要 | 不需要 |
| 能還原到另一個平台嗎 | 不能 | 不能 | 不能 |

iPhone 這次改動的時間點，微軟是用對企業 IT 管理員發的訊息中心公告（編號 MC1111780）說明的：2025 年 9 月開始推送、預計 10 月初推完，原本 App 內那個需要 Microsoft 個人帳號的備份功能會移除，新做法需要 iOS 16.0 以上（[BleepingComputer 報導](https://www.bleepingcomputer.com/news/microsoft/microsoft-authenticator-on-ios-moves-backups-fully-to-icloud/)）。App Store 台灣區目前的版本是 6.8.56（2026 年 9 月 29 日更新），頁面標示需要 iOS 17.0 以上。

Android 的變動寫在[微軟說明頁](https://support.microsoft.com/zh-tw/authenticator/back-up-your-accounts-in-microsoft-authenticator)的注意事項裡，原文是：「從 2027 年 1 月開始，您將不再使用您的 Microsoft 個人帳戶來啟用備份。您必須從 Google One 備份啟用『Microsoft Authenticator』。」在那之前，Android 用戶照舊在 App 設定裡開「雲端備份」、選一個 Microsoft 個人帳號存放。

## iPhone 找不到「備份」選項？開關搬到 iCloud 設定裡了

不少人搜「microsoft authenticator 備份 沒有 備份 選項」，原因就是上面那條：iPhone 版的備份不再由 App 自己管，App 設定頁裡已經沒有那個開關。照[微軟說明頁](https://support.microsoft.com/zh-tw/authenticator/back-up-your-accounts-in-microsoft-authenticator)的步驟，要在 iPhone 上做四件事：

1. 開啟 iCloud 雲碟
2. 開啟 iCloud 鑰匙圈
3. 開啟 iCloud 備份
4. 打開「設定」→ 點你的姓名 → iCloud →「儲存至 iCloud」旁的「顯示全部」，找到 Authenticator 並打開開關（路徑寫法依 [Apple 台灣支援頁](https://support.apple.com/zh-tw/118225)）

四項缺一項，備份就可能沒做成。另外要注意 iCloud 空間：[Apple 官方](https://support.apple.com/zh-tw/108047)寫明免費方案是 5GB，iCloud 備份遇到空間不足時會跳出提示。微軟沒有公布 Authenticator 的備份佔多少空間，也沒寫 iCloud 滿了時 Authenticator 的備份會不會跟著失敗，所以換機前順手看一下 iCloud 還有沒有剩餘空間比較保險。

## 不是每種帳號都能完整還原

備份「成功」不代表還原後全部能直接用。微軟說明頁把帳號分成三類，還原後的狀態不一樣：

| 帳號類型 | 備份了什麼 | 還原後要做什麼 |
|---|---|---|
| Microsoft 個人帳號（只用 30 秒更新的一次性密碼）| 一次性密碼 | 還原後就能用 |
| Microsoft 個人帳號（有開無密碼登入）| 只有帳號名稱 | 要重新登入 |
| 公司或學校帳號 | 只有帳號名稱 | 要重新登入 |
| 第三方帳號（例如 Amazon、Facebook、Gmail）| 一次性密碼 | 還原後就能用 |

最容易出事的是公司帳號。[Microsoft Learn 換機文件](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-transfer-authenticator-new-phone)寫明，公司或學校帳號還原的只有名稱，新手機上可能看到紅字「Sign in to add your account」，要點進去重新登入才算設定完成；如果公司強制用 passkey（通行金鑰），要先在新手機設好新的 passkey，才能移除舊裝置。

## 換手機前先做這三件事

<!-- IG-synthesis: 微軟把換機資訊拆在三個地方（Support 備份頁、Support 還原頁、Microsoft Learn 換機文件），各自只講一段；本節把三頁的條件合併成「換機前三件事」，並把 iOS 端的版本門檻（6.8.33）、開過一次 App、舊手機保留到驗證完這幾個散在不同頁的細節放進同一張清單 -->

### 第一件：確認舊手機的備份真的開著

iPhone 用戶照上一節四個步驟檢查一次，另外微軟還原疑難排解寫了兩個常被忽略的條件：舊手機的 Authenticator 要升到 6.8.33 版或更新，而且換手機前至少要打開 App 一次。新 iPhone 上如果看不到備份，微軟給的解法是把 Authenticator 解除安裝再重新安裝，備份應該就會出現。

Android 用戶則到 App 的 設定 → 備份，確認「雲端備份」是開著的，並記住當初選的是哪一個 Microsoft 個人帳號。新手機還原時要登入同一個帳號，[還原說明頁](https://support.microsoft.com/en-us/authenticator/restore-account-credentials-from-microsoft-authenticator)寫得很直接：如果你登入不了備份用的帳號，微軟客服也幫不上忙。

### 第二件：公司帳號另外準備重新登入

公司或學校帳號還原後只有名稱，一定要重新登入。如果公司要求多重驗證，而你登記的唯一驗證方式就是舊手機上的 Authenticator，舊手機一清掉，新手機就可能登不進去。

保險做法是換機前先到公司帳號的[安全性資訊頁](https://mysignins.microsoft.com/security-info)看看，除了 Authenticator 之外還有沒有其他登記的驗證方式（例如電話）。沒有的話，先問公司 IT 部門換機流程；微軟的文件也寫明，管理者若不開放自行設定 passkey，要找管理者或服務台走他們核准的流程。

### 第三件：舊手機留到全部驗證過再清

[Microsoft Learn 換機文件](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-transfer-authenticator-new-phone)的重要提示只有一句：在確認新手機能登入你最常用的帳號與資源之前，先保留舊手機。實際做法是在新手機上逐一試登入：Microsoft 個人帳號、公司帳號、每一個有開兩步驟驗證的第三方服務，全部能用之後，才把舊手機回復原廠設定或拿去舊換新。

## iPhone 換 Android（或反過來）：備份帶不過去，只能逐一重新綁定

搜「microsoft authenticator 換手機 android」的人，多半是遇到這一關。微軟說明頁開頭的重要提示寫明：「您只能在相同的裝置類型上備份與還原：使用 iOS 裝置備份的帳戶無法在 Android 裝置上還原。」[還原說明頁](https://support.microsoft.com/en-us/authenticator/restore-account-credentials-from-microsoft-authenticator)給的替代辦法是把帳號重新加一次。

重新加的位置依帳號類型不同，都要在舊手機還能用的時候做：

| 帳號類型 | 到哪裡重新綁定 |
|---|---|
| Microsoft 個人帳號 | [account.microsoft.com/security](https://account.microsoft.com/security) →「Manage how I sign in」→「Add a new way to sign in or verify」→「Use an app」，再用新手機掃 QR 碼 |
| 公司或學校帳號 | [mysignins.microsoft.com/security-info](https://mysignins.microsoft.com/security-info) →「Add sign-in method」→ Microsoft Authenticator |
| 第三方帳號（Google、Facebook、Amazon 等）| 各服務自己的兩步驟驗證設定頁，新增或更換驗證器 App，掃新的 QR 碼 |

前兩列的步驟與選項名稱出自[微軟〈如何將帳戶新增到 Microsoft Authenticator〉](https://support.microsoft.com/en-us/authenticator/how-to-add-your-accounts-to-microsoft-authenticator)英文版，中文介面的按鈕名稱可能略有不同，以畫面為準。第三方帳號的設定頁位置每家不同，帳號多的話建議列一張清單，一個一個打勾，綁好一個就在新手機試一次驗證碼。

### 要不要乾脆把個人帳號搬到別的 App？

如果你是會在 iPhone 和 Android 之間換來換去的人，或公司強制裝 Microsoft Authenticator、你不想讓個人帳號跟公司帳號擠在同一個 App，可以趁這次重新綁定，把個人帳號的驗證碼放到能跨平台同步的 App。以 Google Authenticator 為例：

| 比較項目 | Microsoft Authenticator | Google Authenticator |
|---|---|---|
| 備份／同步方式 | iPhone 走 iCloud；Android 走 Microsoft 個人帳號（2027 年起改 Google One 備份）| 登入 Google 帳號後同步 |
| iPhone 與 Android 互轉 | 備份不能互通 | 新裝置登入同一個 Google 帳號就會自動同步 |
| 不想用雲端時 | — | 可選「不使用帳戶」，改用匯出 QR 碼手動轉移 |
| 公司 M365 推播核准、無密碼登入 | 有 | 沒有（只產生驗證碼）|

Google Authenticator 這一欄依 [Google 官方說明](https://support.google.com/accounts/answer/1066447?hl=zh-Hant)：同步需要 Android 版 6.0、iOS 版 4.0 以上，在新裝置登入同一個 Google 帳號，驗證碼會自動同步過去。代價是所有個人帳號的驗證碼都掛在 Google 帳號上，Google 帳號一被盜就全部暴露；它跟其他 App 在這類風險上的比較，在 [2FA Authenticator App 比較](/privacy/2fa-authenticator-app-compare/)那篇有完整的場景矩陣。

公司帳號則留在 Microsoft Authenticator，因為推播核准、無密碼登入這些功能要靠它；公司若有指定驗證 App，照公司規定。

## Android 2027 年改 Google 備份：會不會吃 15 GB、要不要付費

微軟說明頁只寫了「從 Google One 備份啟用」，沒有寫備份大小、沒有寫現有的 Microsoft 帳號備份會不會自動轉過去，也沒有寫 2027 年 1 月的具體切換方式。這幾點目前都未公布，到時要看 App 更新內容與微軟說明頁。

Google 這一側倒是寫得清楚。[Google 帳戶儲存空間說明](https://support.google.com/googleone/answer/9312312?hl=zh-Hant)把「透過 Android 備份設定管理的所有資料」列在計入儲存空間配額的項目裡，[Android 備份說明](https://support.google.com/android/answer/2819582?hl=zh-Hant)也寫明 Google 帳戶可免費備份到 15 GB，之後可透過 Google One 取得更多空間。

換句話說，改到 Google 備份後，Authenticator 的資料會跟 Gmail、Google 相簿、雲端硬碟共用同一個 15 GB。要不要付費，取決於你現在 15 GB 用了多少，而不是 Authenticator 本身；微軟沒公布它佔多少空間。Google 的說明也寫到，帳戶超過配額兩年以上沒處理，連 Android 裝置備份都可能被刪除。空間本來就快滿的人，可以先看 [Google One 值得訂嗎](/productivity/google-one-review/)那篇，評估清空間還是升級。

## 優點與缺點（這次備份改版）

**優點：**
- iPhone 用戶不必再為了備份註冊或登入 Microsoft 個人帳號，只用公司帳號的人也能備份帳號名稱與第三方驗證碼。
- 備份方式跟著手機系統走：依微軟還原說明，新 iPhone 開好同樣的 iCloud 項目、裝回 Authenticator，就能把備份還原回來，不用再多記一組 Microsoft 帳號。
- Android 2027 年改用 Google One 備份後，兩個平台的邏輯一致：都用手機系統本身的雲端帳號。

**缺點：**
- iPhone 版 App 內沒有備份開關，要到 iCloud 設定裡找，四個 iCloud 項目缺一個就可能沒備份到，舊習慣的人容易以為「沒有備份功能」。
- 跨平台換機完全不能還原，每個帳號都要重新綁定，帳號多的人很花時間。
- 公司或學校帳號不管哪個平台都只備份名稱，換機一定要重新登入，唯一驗證方式在舊手機上的人最容易卡住。
- Android 改 Google 備份後，資料吃的是 Google 帳戶 15 GB 共用空間；現有備份怎麼轉、什麼時候切換，微軟目前都沒寫。

## 結論

**同平台換機的人不用換 App，照三件事做完就好；常在 iPhone 和 Android 之間換的人，個人帳號值得搬到能跨平台同步的 App。** Microsoft Authenticator 這次改版對同平台換機其實是簡化：iPhone 走 iCloud、Android 2027 年起走 Google One，都跟系統備份綁在一起。麻煩只出在兩個地方：跨平台換機的備份帶不過去，以及公司帳號一律要重新登入。

換機前的順序記住這樣就夠：先確認舊手機備份開著、公司帳號有第二種驗證方式、新手機每個帳號都試登入過，最後才清舊手機。想進一步比較各款驗證器 App 在「雲端帳號被盜」「公司看不看得到」這些場景下的差異，可以看 [2FA Authenticator App 怎麼選](/privacy/2fa-authenticator-app-compare/)；如果你在考慮連密碼都不用的登入方式，[Passkey vs Password](/privacy/passkey-vs-password/)那篇整理了 passkey 和密碼管理器怎麼搭配。

→ [Microsoft Authenticator 備份官方說明](https://support.microsoft.com/zh-tw/authenticator/back-up-your-accounts-in-microsoft-authenticator)

---

📌 本文無聯盟行銷連結，評測立場獨立。
