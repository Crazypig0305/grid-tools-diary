---
title: "2FA Authenticator App 怎麼選？2026 五款主流工具比較"
description: "2FA 該用哪個 Authenticator App？Google / Microsoft / Authy / 1Password 內建 / Bitwarden 內建五款主流工具比較，含跨裝置同步、備份機制、開源狀態、企業 admin 觀察三場景風險矩陣，最後給三種使用情境的明確推薦組合。"
date: 2026-05-18
lastmod: 2026-09-13T00:19:00+08:00
canonicalURL: "https://gridtoolsdiary.com/privacy/2fa-authenticator-app-compare/"
categories: ["privacy"]
tags: ["2FA", "authenticator", "雙因素驗證", "passkey", "資安"]
draft: false
---

只用密碼登入的時代已經結束。從 Google、Apple、Microsoft 到大部分銀行與政府服務，現在預設都會推使用者開啟「兩步驟驗證（2FA）」——除了密碼之外，再加一道由 Authenticator App 產生的六位數動態驗證碼。

問題是：Authenticator App 不只一款。手機商店上隨便搜「authenticator」，列出十幾個介面長得幾乎一樣的選項。對非技術背景的使用者來說，要判斷「哪個比較安全」「換手機時會不會把所有驗證碼弄丟」「公司強制裝的那個跟我自己用的可以共存嗎」這類問題並不容易。

本文比較 2026 年五款最常被推薦的 Authenticator App——**Google Authenticator、Microsoft Authenticator、Authy、1Password 內建、Bitwarden 內建**——從跨裝置同步、備份機制、開源狀態、企業 admin 可見性四個維度評估，並針對三種典型使用情境給明確的推薦組合。

文章後段也會處理兩個近年常被問到的問題：**Passkey 出現後，2FA App 是不是要被淘汰了？備援碼（recovery code）到底應該怎麼保管？**

## 為什麼 2FA 不能只靠簡訊？

在比較 App 之前，先釐清一件事：**簡訊 2FA 是比較弱的一種雙因素驗證**。

依據國際 [Internet Engineering Task Force (IETF) RFC 6238 規範](https://datatracker.ietf.org/doc/html/rfc6238)，標準的時間型一次性密碼（Time-based One-Time Password, TOTP）應該由「使用者裝置上的應用程式」依共享密鑰與當前時間獨立產生，伺服器端不傳輸驗證碼本身。

簡訊 2FA 不符合這個原則：驗證碼是由伺服器產生後傳送到電信網路，過程中可能被 SIM swap 攻擊（攻擊者向電信業者申辦補卡）或 SS7 信令網路漏洞攔截。[Wikipedia 的 Multi-factor Authentication 條目](https://en.wikipedia.org/wiki/Multi-factor_authentication)整理了這段歷史：美國國家標準暨技術研究院（NIST）在 2016 年 7 月的指引草案曾提議淘汰簡訊驗證。2017 年 6 月定稿的 [SP 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html) 沒有淘汰它，而是在 §5.1.3.3 改列為「受限制（RESTRICTED）」但仍可使用（原文：Use of the PSTN for out-of-band verification is RESTRICTED），並要求驗證方用電話網路（簡訊或語音）傳碼前，先考量換機、換 SIM 卡、號碼轉移等風險訊號。現行的 [NIST SP 800-63B-4](https://pages.nist.gov/800-63-4/sp800-63b.html)（2025 年 8 月定稿，§3.1.3.3）延續這個「受限制」分類，換機、換 SIM、號碼轉移這些風險訊號的要求也仍在。

換句話說，**只要你有更好的選項，就不應該依賴簡訊 2FA**。而「更好的選項」就是 Authenticator App。

## 五款主流 Authenticator App 比較

下表整理五款主流 App 在 2026 年的功能差異。所有「不開源」的 App 都不代表不安全，但「開源」意味著資安研究員可以審核程式碼，是長期信任的加分項。

| App | 費用 | 跨裝置同步 | 備份機制 | 開源 | 企業 admin 可見 |
|---|---|---|---|---|---|
| **Google Authenticator** | 免費 | ✅（2023 年新增）| 透過 Google 帳號 | ❌ | ❌（個人帳號）|
| **Microsoft Authenticator** | 免費 | ✅ | 透過 Microsoft 帳號 | ❌ | ⚠️（企業 M365 環境可見）|
| **Authy** | 免費 | ✅（多裝置）| 雲端加密備份 | ❌ | ❌（個人 App，官網未提企業管理功能）|
| **1Password 內建** | 付費（USD 47.88/年起）| ✅（隨密碼庫）| 隨密碼庫雲端備份 | ❌ | ❌（個人方案）|
| **Bitwarden 內建** | Premium USD 19.80/年 | ✅（隨密碼庫）| 隨密碼庫雲端備份 | ✅ | ❌（個人方案）|

<!-- IG-angle: 把「企業 admin 看不看得到我的驗證碼」這個多數比較文沒列的維度拉進五款比較表，再用手機遺失／雲端帳號被盜／企業可見性三個風險場景做矩陣，把「哪個最好」換成「你最怕哪種情況」 -->

> 💲 費用欄更正（2026 年 9 月 12 日）：兩款密碼管理器內建方案今年都調過價，本文原本沿用的是舊價。現價已對照 [Bitwarden 官方定價頁](https://bitwarden.com/pricing/)（Premium $19.80/年，[2026 年 1 月 21 日調整](https://bitwarden.com/blog/bitwarden-launches-enhanced-premium-plan/)）與 [1Password 官方定價頁](https://1password.com/pricing/personal)（個人版 $47.88/年）更正；1Password 新價從 2026 年 3 月 27 日當天或之後的第一次續訂起套用，出處是 [MacRumors 2026 年 2 月 24 日報導](https://www.macrumors.com/2026/02/24/1password-march-price-increase/)引述的官方通知。

### Google Authenticator

Google 自家的 Authenticator 從 2010 年問世，原本最大的缺點是「不支援雲端同步」——一旦手機掉了或刷機，所有驗證碼必須一個一個重設。2023 年加入 Google 帳號同步後解決了這個問題，但資安研究者 Mysk 當時就指出同步的資料沒有端對端加密（[MacRumors 2023 年 4 月 27 日報導](https://www.macrumors.com/2023/04/27/google-authenticator-cloud-sync-no-e2e/)）。現在 [Google 官方說明](https://support.google.com/accounts/answer/1066447)的寫法是「Google encrypts Authenticator codes both in transit and at rest across our products.」（在傳輸中與儲存時加密），頁面上沒有提到端對端加密。

介面在五款中最陽春，沒有資料夾分類，帳號一多就不好整理。

### Microsoft Authenticator

最大優勢是整合 Microsoft 365 SSO（單一登入）：在企業環境若公司用 M365，這個 App 同時負責公司帳號登入確認與 MFA 通知推播，整合度最高。

注意點是：**公司帳號登記進 Microsoft Authenticator 後，公司的 IT 管理者在後台看得到這個驗證方式**——[Microsoft Entra 文件](https://learn.microsoft.com/en-us/entra/identity/authentication/howto-mfa-userdevicesettings)寫明管理者可以在使用者的驗證方式頁管理這些方法，依 [Microsoft Graph 文件](https://learn.microsoft.com/en-us/graph/api/resources/microsoftauthenticatorauthenticationmethod?view=graph-rest-1.0)，登記資料包含 App 所在裝置的名稱（原文：The name of the device on which this app is registered）與 App 版本。微軟文件講的是公司帳號這一側；本文沒有查到它對「同一個 App 裡另外加的個人帳號（例：個人 Gmail、個人 Apple ID）」可見範圍的明確說明，所以保守做法是公司帳號與個人帳號分用兩個 App。

[Microsoft 官方 help](https://learn.microsoft.com/en-us/azure/active-directory/authentication/concept-authentication-methods) 也有完整的方法清單。

### Authy

Twilio 旗下產品（[Authy 官方](https://authy.com/)），同一個 Authy 帳號可以在多支手機、平板上同時使用。雲端備份用你自己設的備份密碼、在手機上先加密再上傳；[Twilio 官方說明](https://www.twilio.com/en-us/blog/how-the-authy-two-factor-backups-work)寫明「The encryption/decryption key is never transmitted.」，Authy 自己也看不到你的帳號內容。換新手機或加掛新裝置時，要先用原本註冊的手機號碼收一次驗證碼（簡訊或語音），同步下來之後還得輸入備份密碼才解得開（原文：you will have to provide your backup password to decrypt your keys）。

缺點是**桌面版（Windows、macOS、Linux）已在 2024 年 3 月 19 日停止服務**——原訂 2024 年 8 月，Twilio 在 2024 年 2 月 19 日的[官方公告](https://www.twilio.com/en-us/changelog/end-of-life--eol--of-twilio-authy-desktop-apps)提前，現在只剩手機版。對於需要桌機產生驗證碼的工作流（例如 IT 管理員），這是明顯的退步。

### 1Password 內建 2FA

如果已經用 1Password 管理密碼，內建的 TOTP 功能是最自然的選擇：每個帳號的密碼與驗證碼存在同一條目，登入時 1Password 會自動填入兩者，操作步驟比「打開另一個 App 抄六位數」少很多。

但這也是 1Password 內建 2FA 最大的爭議點——**密碼與第二因素存在同一個保險庫，本質上違反了「雙因素應該獨立」的設計原則**。如果 1Password 主密碼洩漏，攻擊者可同時取得密碼與 2FA，等於只有單因素保護。

1Password 官方部落格在 [2023 年 6 月 22 日的文章](https://1password.com/blog/1password-2fa-passwords-codes-together)裡回應過這個爭議：驗證碼和密碼如果都來自同一支裝置，本來就算不上真正的第二因素，放在 1Password 或放在同一支手機上的驗證碼 App，保護程度一樣（原文：you have the same level of protection whether you store your TOTP in 1Password or an authenticator app (on the same device)）；而能拿到你 1Password 登入資料的攻擊者，至少得同時握有你的 Email、Secret Key 與帳號密碼，這種人不太會被另一個驗證碼 App 擋住。文章的結論是：對多數人來說，把 TOTP 放在 1Password 在可接受的風險範圍內。本文的建議比它保守一點：高敏感帳號（主要 Email、銀行、加密貨幣交易所）的 2FA，仍建議放在另一個跟密碼庫分開的 App（理由見下方場景二）。

延伸閱讀：[1Password 2026 漲價分析]({{< ref "/privacy/1password-price-hike-2026" >}})。

### Bitwarden 內建 2FA

Bitwarden Premium（USD 19.80/年）內建 TOTP 功能，邏輯與 1Password 相同，但有兩個關鍵差異：**價格約是 1Password 個人方案的四成，且程式碼完全開源**（[Bitwarden GitHub](https://github.com/bitwarden) 可審閱）。

「密碼與 2FA 同庫」的爭議在 Bitwarden 同樣存在。但對預算敏感、且偏好開源軟體的使用者，Bitwarden 內建 2FA 是性價比最高的選項。

延伸閱讀：[Bitwarden 完整評測]({{< ref "/privacy/bitwarden-review" >}})｜[Bitwarden vs 1Password 完整比較]({{< ref "/privacy/bitwarden-vs-1password" >}})。

## 三場景風險矩陣

選 Authenticator App 不是看「哪個最好」，而是看「在你最在意的風險場景下，哪個影響最小」。

### 場景一：手機遺失或刷機

| App | 救援難度 |
|---|---|
| Google Authenticator | 容易（Google 帳號還在即可恢復）|
| Microsoft Authenticator | 容易（M 帳號還在即可恢復）|
| Authy | 容易（多裝置已登入即可）|
| 1Password 內建 | 容易（隨密碼庫恢復）|
| Bitwarden 內建 | 容易（隨密碼庫恢復）|

五款都有雲端同步後，**這個場景已不再是選擇關鍵**。真正麻煩的是「同步雲端被攻破」的下一個場景。

### 場景二：雲端帳號被盜

| App | 攻擊面 |
|---|---|
| Google Authenticator | Google 帳號被盜 = 全 2FA 暴露 |
| Microsoft Authenticator | M 帳號被盜 = 全 2FA 暴露 |
| Authy | Authy 帳號被接管（例如手機號碼被 SIM swap、被加掛新裝置）**再加上**備份密碼被猜中或外洩 = 全 2FA 暴露；只接管帳號、沒有備份密碼的話解不開（2022 年 8 月確實發生過帳號被接管的事件：[Twilio 官方說明](https://www.twilio.com/en-us/blog/august-2022-social-engineering-attack)有 93 個 Authy 帳號被加掛了未授權裝置）|
| 1Password 內建 | 主密碼+Secret Key 被盜 = 密碼與 2FA 同時暴露 |
| Bitwarden 內建 | 主密碼被盜 = 密碼與 2FA 同時暴露 |

Authy 這一列多了一道門：新裝置同步下來的是加密過的備份，還要輸入備份密碼才解得開。所以用 Authy 的話，備份密碼一定要設成跟其他地方都不重複的長密碼——這道門是它比 Google Authenticator 多出來的保護，備份密碼跟別處共用，這道門就等於沒有。

這個場景下，**沒有任何一款有雲端同步的 App 是免疫的**。能避開這個場景的，是不靠廠商雲端同步的 App——例如 Android 的 [Aegis](https://github.com/beemdevelopment/Aegis)（開源，保險庫加密存在手機上，備份存到你自己選的位置；前提是別把備份檔放進會被同一次盜號波及的雲端）。常被一起推薦的 iOS App Raivo OTP 則不是純本地：它的[官方 README](https://github.com/raivo-otp/ios-application) 列的第一條功能就是自動備份／同步到 iCloud。純本地的代價是手機掉了、又沒有自己的備份，就真的要逐一重設。

### 場景三：企業 admin 可見性

| App | 企業環境曝光 |
|---|---|
| Google Authenticator | 個人 Google 帳號，企業看不到 |
| Microsoft Authenticator | 公司帳號登記後，admin 看得到這個驗證方式、所在裝置名稱與 App 版本 |
| Authy | 個人用 App，官網沒有提到企業管理功能 |
| 1Password 內建 | 個人方案沒有管理者；Business 方案有報表權限的人看得到你 Employee vault 的項目數量、項目本身不直接開放給其他成員，但有帳號救援權限的人救援你的帳號後可以進入整個 vault（[官方說明](https://support.1password.com/employee-vault/)）|
| Bitwarden 內建 | 個人方案沒有管理者；組織的 owner／admin 依設計看不到成員的個人保險庫，但 Enterprise 方案若開了帳號救援政策、你也已登記，管理者重設你的主密碼後會取得你整個保險庫的存取權（[官方說明](https://bitwarden.com/help/onboarding-and-succession/)）|

若你高度在意「公司 IT 部門看不到我的個人帳號 2FA」，建議**個人帳號的驗證碼放在 Aegis，或放在你自己註冊、自己付費的 Bitwarden 個人方案帳號裡——不要放進加入公司 Bitwarden 組織的那個帳號（上表寫過，公司若開了帳號救援，管理者重設你的主密碼後就能進入整個保險庫）；公司強制要裝的 Microsoft Authenticator 只放公司帳號**。

## Passkey 出來了，2FA 還要用嗎？

近兩年 Apple、Google、Microsoft 三家強推 Passkey（FIDO2 通行金鑰），讓不少人懷疑「Authenticator App 是不是要被淘汰了」。

答案是：**還要用，但角色會慢慢縮小。**

Passkey 的本質是「無密碼登入」——用裝置上的生物辨識（Face ID、指紋）取代密碼，且內建第二因素（裝置本身），所以同時取代密碼與 2FA。技術上比 TOTP 更安全（無 phishing 風險、無共享密鑰外洩可能）。

但 2026 年的現實是：**支援 Passkey 的服務雖然越來越多，離「到處都能用」還很遠**。不少傳統銀行、政府網站、中小型 SaaS 與企業內部系統仍只支援密碼 + TOTP 的組合。所以未來 5-10 年的合理策略是：

- 支援 Passkey 的服務 → 改用 Passkey（Google、Apple、Microsoft、Amazon、PayPal、GitHub 等已支援）
- 不支援 Passkey 的服務 → 繼續用密碼 + Authenticator App
- 兩者並行，不需要二選一

Passkey 本身的備份策略也仍在演進中：iCloud Keychain、Google Password Manager、1Password、Bitwarden 都已支援跨裝置同步 Passkey，但「裝置全失」的恢復流程目前各家差異很大，建議高敏感帳號仍保留 TOTP 作為備援機制。

## 備援碼（Recovery Code）怎麼保管？

幾乎所有支援 2FA 的服務都會在開啟時提供「備援碼」——通常是 8-10 組六位數或英數混合的字串，用來在「Authenticator App 完全無法使用」時恢復登入。

備援碼的價值極高（一次性可繞過 2FA），所以絕對不能放在以下位置：

- 截圖或拍照存在手機相簿（相簿若有開雲端同步，備援碼就跟著上雲，雲端帳號一出事就一起外洩）
- 用 Email 寄給自己（Email 帳號本身可能就是被保護的目標）
- 直接寫在密碼管理器同一條目下（單點失效）

合理的備援碼保管方式有三種：

1. **印出紙本，放在實體保險箱或抽屜深處**——對非數位攻擊免疫，但要記得火災、水災、搬家後是否還能找到
2. **存在獨立的離線密碼管理器**（KeePassXC 純本地版），與主要密碼管理器分開
3. **存在另一個信任的人手上**（伴侶、家人），但要評估社交工程風險

不論用哪種方式，**每年至少審視一次備援碼是否仍可讀、仍能對應到當前的帳號清單**。

## 三種情境的明確推薦

最後給三種典型使用者的明確組合：

**情境 A：已用 Bitwarden 管理密碼、預算敏感、偏好開源**
- Authenticator：**Bitwarden 內建 2FA**（已付 Premium 即可用）
- 高敏感帳號（主 Email、銀行）：驗證碼另存一份在跟密碼庫分開的 App 做雙保險——Android 可用純本地的 **Aegis**；iPhone 則挑符合這兩個條件之一的 App：能在 App 設定裡把 iCloud／雲端同步整個關掉，或能匯出加了密碼的備份檔讓你自己保管。確認方法是裝好後先進 App 的設定頁，找「同步」「備份」「iCloud」這幾個選項，看能不能關、能不能匯出成加密檔；兩樣都做不到的，驗證碼就跟密碼庫一樣掛在雲端帳號上，當不了雙保險。常被推薦的 Raivo OTP 主打功能就是同步到 iCloud（見場景二），挑的時候同樣照這兩個條件檢查
- 備援碼：紙本 + 保險箱

**情境 B：已用 1Password、跨裝置體驗優先**
- Authenticator：**1Password 內建 2FA**（與密碼一起填入最順）
- 高敏感帳號：另存於 **Authy**（手機、平板多裝置同步；備份密碼設成跟其他地方都不重複的長密碼，這是它比 Google Authenticator 多的那道門，見場景二；注意桌面版已在 2024 年 3 月停止，電腦上沒有 Authy 可用）
- 備援碼：印出收在抽屜 + 另外手動輸入一份到 KeePassXC 純本地資料庫（不要用拍照的方式存，照片會先進手機相簿）

**情境 C：純免費、單一手機使用、技術門檻最低**
- Authenticator：**Google Authenticator**（最簡單，雲端同步已支援）
- 公司 M365 → **Microsoft Authenticator**（與個人帳號分開放）
- 備援碼：印出收進實體文件夾

## 結論

選 Authenticator App 沒有「最佳解」，只有「在你的場景下風險可接受的解」。

五款主流 App 在「跨裝置同步」與「裝置遺失救援」上差異已不大；真正的差異在於**雲端被攻破的攻擊面**（純本地 vs 雲端同步）與**企業 admin 可見性**。

對非技術背景使用者來說，最重要的不是糾結哪一款最好，而是**確實開啟 2FA、確實備份備援碼、確實理解 2FA 不是萬靈丹**——配合密碼管理器、Passkey、實體安全金鑰（如 YubiKey）多層防護，才是現代資安的合理姿態。

延伸閱讀：[Bitwarden vs 1Password 完整比較]({{< ref "/privacy/bitwarden-vs-1password" >}})｜[1Password 2026 漲價分析]({{< ref "/privacy/1password-price-hike-2026" >}})｜[Bitwarden 完整評測]({{< ref "/privacy/bitwarden-review" >}})。

外部規範參考：[IETF RFC 6238 - TOTP 標準](https://datatracker.ietf.org/doc/html/rfc6238)｜[Wikipedia: Multi-factor Authentication](https://en.wikipedia.org/wiki/Multi-factor_authentication)。

App 官方說明：<a href="https://support.google.com/accounts/answer/1066447" rel="nofollow noopener" target="_blank">Google Authenticator help</a>｜<a href="https://learn.microsoft.com/en-us/azure/active-directory/authentication/concept-authentication-methods" rel="nofollow noopener" target="_blank">Microsoft Authenticator docs</a>｜<a href="https://authy.com/" rel="nofollow noopener" target="_blank">Authy 官方</a>｜<a href="https://support.1password.com/one-time-passwords/" rel="nofollow noopener" target="_blank">1Password TOTP help</a>｜<a href="https://bitwarden.com/help/authenticator-keys/" rel="nofollow noopener" target="_blank">Bitwarden TOTP help</a>。
