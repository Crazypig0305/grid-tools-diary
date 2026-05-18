---
title: "2FA Authenticator App 怎麼選？2026 五款主流工具實測比較"
description: "2FA 該用哪個 Authenticator App？Google / Microsoft / Authy / 1Password 內建 / Bitwarden 內建五款主流工具實測比較，含跨裝置同步、備份機制、開源狀態、企業 admin 觀察三場景風險矩陣，最後給三種使用情境的明確推薦組合。"
date: 2026-05-18
lastmod: 2026-05-18
canonicalURL: "https://gridtoolsdiary.com/privacy/2fa-authenticator-app-compare/"
categories: ["privacy"]
tags: ["2FA", "authenticator", "雙因素驗證", "passkey", "資安"]
image: /og-default.jpg
draft: false
---

只用密碼登入的時代已經結束。從 Google、Apple、Microsoft 到大部分銀行與政府服務，現在預設都會推使用者開啟「兩步驟驗證（2FA）」——除了密碼之外，再加一道由 Authenticator App 產生的六位數動態驗證碼。

問題是：Authenticator App 不只一款。手機商店上隨便搜「authenticator」，列出十幾個介面長得幾乎一樣的選項。對非技術背景的使用者來說，要判斷「哪個比較安全」「換手機時會不會把所有驗證碼弄丟」「公司強制裝的那個跟我自己用的可以共存嗎」這類問題並不容易。

本文比較 2026 年五款最常被推薦的 Authenticator App——**Google Authenticator、Microsoft Authenticator、Authy、1Password 內建、Bitwarden 內建**——從跨裝置同步、備份機制、開源狀態、企業 admin 可見性四個維度評估，並針對三種典型使用情境給明確的推薦組合。

文章後段也會處理兩個近年常被問到的問題：**Passkey 出現後，2FA App 是不是要被淘汰了？備援碼（recovery code）到底應該怎麼保管？**

## 為什麼 2FA 不能只靠簡訊？

在比較 App 之前，先釐清一個常見誤解：**簡訊 2FA 不算「真正的雙因素驗證」**。

依據國際 [Internet Engineering Task Force (IETF) RFC 6238 規範](https://datatracker.ietf.org/doc/html/rfc6238)，標準的時間型一次性密碼（Time-based One-Time Password, TOTP）應該由「使用者裝置上的應用程式」依共享密鑰與當前時間獨立產生，伺服器端不傳輸驗證碼本身。

簡訊 2FA 不符合這個原則：驗證碼是由伺服器產生後傳送到電信網路，過程中可能被 SIM swap 攻擊（攻擊者向電信業者申辦補卡）或 SS7 信令網路漏洞攔截。[Wikipedia 的 Multi-factor Authentication 條目](https://en.wikipedia.org/wiki/Multi-factor_authentication)也明確指出，自 2017 年起美國國家標準暨技術研究院（NIST）已不再建議將簡訊作為高安全等級帳戶的第二因素。

換句話說，**只要你有更好的選項，就不應該依賴簡訊 2FA**。而「更好的選項」就是 Authenticator App。

## 五款主流 Authenticator App 比較

下表整理五款主流 App 在 2026 年的功能差異。所有「不開源」的 App 都不代表不安全，但「開源」意味著資安研究員可以審核程式碼，是長期信任的加分項。

| App | 費用 | 跨裝置同步 | 備份機制 | 開源 | 企業 admin 可見 |
|---|---|---|---|---|---|
| **Google Authenticator** | 免費 | ✅（2023 年新增）| 透過 Google 帳號 | ❌ | ❌（個人帳號）|
| **Microsoft Authenticator** | 免費 | ✅ | 透過 Microsoft 帳號 | ❌ | ⚠️（企業 M365 環境可見）|
| **Authy** | 免費 | ✅（多裝置）| 雲端加密備份 | ❌ | ⚠️（Twilio Enterprise 可見）|
| **1Password 內建** | 付費（USD 36/年起）| ✅（隨密碼庫）| 隨密碼庫雲端備份 | ❌ | ❌（個人方案）|
| **Bitwarden 內建** | Premium USD 10/年 | ✅（隨密碼庫）| 隨密碼庫雲端備份 | ✅ | ❌（個人方案）|

### Google Authenticator

Google 自家的 Authenticator 從 2010 年問世，原本最大的缺點是「不支援雲端同步」——一旦手機掉了或刷機，所有驗證碼必須一個一個重設。2023 年加入 Google 帳號同步後解決了這個問題，但也引發資安界對「同步密鑰是否加密傳輸」的討論（[Google 官方說明](https://support.google.com/accounts/answer/1066447)指出已採用端對端加密選項，但預設未開啟）。

介面在五款中最陽春，沒有資料夾分類、沒有搜尋功能，超過 30 個帳號後管理不便。

### Microsoft Authenticator

最大優勢是整合 Microsoft 365 SSO（單一登入）：在企業環境若公司用 M365，這個 App 同時負責公司帳號登入確認與 MFA 通知推播，整合度最高。

注意點是**企業 admin 在 M365 後台可以看到員工的 Microsoft Authenticator 註冊狀態與設備指紋**（屬於 Conditional Access 的合法功能）。所以若用同一個 App 同時放公司帳號與個人帳號（例：個人 Gmail、個人 Apple ID），技術上 admin 看不到個人帳號內容，但裝置層的 metadata 仍會被企業 MDM 採集。建議公司帳號與個人帳號分用兩個 App。

[Microsoft 官方 help](https://learn.microsoft.com/en-us/azure/active-directory/authentication/concept-authentication-methods) 也有完整的方法清單。

### Authy

Twilio 旗下產品（[Authy 官方](https://authy.com/)），五款裡多裝置同步體驗最完整：手機、平板、桌機可同時登入同一個 Authy 帳號，跨平台順暢。雲端備份採用使用者自設密碼加密，Twilio 自己也無法解密。

缺點是**桌面版於 2024 年底已停止更新並下架**，現在只剩手機版。對於需要桌機產生驗證碼的工作流（例如 IT 管理員），這是明顯的退步。

### 1Password 內建 2FA

如果已經用 1Password 管理密碼，內建的 TOTP 功能是最自然的選擇：每個帳號的密碼與驗證碼存在同一條目，登入時 1Password 會自動填入兩者，操作步驟比「打開另一個 App 抄六位數」少很多。

但這也是 1Password 內建 2FA 最大的爭議點——**密碼與第二因素存在同一個保險庫，本質上違反了「雙因素應該獨立」的設計原則**。如果 1Password 主密碼洩漏，攻擊者可同時取得密碼與 2FA，等於只有單因素保護。

1Password 的回應是：主密碼配合 Secret Key 雙重保護下，這個風險可接受。但對高敏感帳號（主要 Email、銀行、加密貨幣交易所），仍建議把 2FA 放在另一個獨立的 App。

延伸閱讀：[1Password 2026 漲價分析]({{< ref "/privacy/1password-price-hike-2026" >}})。

### Bitwarden 內建 2FA

Bitwarden Premium（USD 10/年）內建 TOTP 功能，邏輯與 1Password 相同，但有兩個關鍵差異：**價格只要 1Password 的三分之一不到，且程式碼完全開源**（[Bitwarden GitHub](https://github.com/bitwarden) 可審閱）。

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
| Authy | Twilio 帳號被盜 = 全 2FA 暴露（且 Authy 2022 年確實發生過攻擊事件）|
| 1Password 內建 | 主密碼+Secret Key 被盜 = 密碼與 2FA 同時暴露 |
| Bitwarden 內建 | 主密碼被盜 = 密碼與 2FA 同時暴露 |

這個場景下，**沒有任何一款有雲端同步的 App 是免疫的**。唯一完全免疫的方案是用純本地 App（Android 的 Aegis、iOS 的 Raivo OTP），完全不上雲，但代價是手機掉了就真的要逐一重設。

### 場景三：企業 admin 可見性

| App | 企業環境曝光 |
|---|---|
| Google Authenticator | 個人 Google 帳號，企業看不到 |
| Microsoft Authenticator | M365 環境下，admin 可看到註冊裝置與 metadata |
| Authy | Twilio Enterprise 客戶的 admin 可見組織內成員清單 |
| 1Password 內建 | 個人方案完全私密；Business 方案 admin 可見條目數但不可見內容 |
| Bitwarden 內建 | 個人方案完全私密；Business 方案同上 |

若你高度在意「公司 IT 部門看不到我的個人帳號 2FA」，建議**個人帳號用 Bitwarden 內建或 Aegis，公司強制要裝的 Microsoft Authenticator 只放公司帳號**。

## Passkey 出來了，2FA 還要用嗎？

近兩年 Apple、Google、Microsoft 三家強推 Passkey（FIDO2 通行金鑰），讓不少人懷疑「Authenticator App 是不是要被淘汰了」。

答案是：**還要用，但角色會慢慢縮小。**

Passkey 的本質是「無密碼登入」——用裝置上的生物辨識（Face ID、指紋）取代密碼，且內建第二因素（裝置本身），所以同時取代密碼與 2FA。技術上比 TOTP 更安全（無 phishing 風險、無共享密鑰外洩可能）。

但 2026 年的現實是：**支援 Passkey 的服務還不到主流網站的 30%**。傳統銀行、政府網站、中小型 SaaS、許多企業內部系統仍只支援密碼 + TOTP 的組合。所以未來 5-10 年的合理策略是：

- 支援 Passkey 的服務 → 改用 Passkey（Google、Apple、Microsoft、Amazon、PayPal、GitHub 等已支援）
- 不支援 Passkey 的服務 → 繼續用密碼 + Authenticator App
- 兩者並行，不需要二選一

Passkey 本身的備份策略也仍在演進中：iCloud Keychain、Google Password Manager、1Password、Bitwarden 都已支援跨裝置同步 Passkey，但「裝置全失」的恢復流程目前各家差異很大，建議高敏感帳號仍保留 TOTP 作為備援機制。

## 備援碼（Recovery Code）怎麼保管？

幾乎所有支援 2FA 的服務都會在開啟時提供「備援碼」——通常是 8-10 組六位數或英數混合的字串，用來在「Authenticator App 完全無法使用」時恢復登入。

備援碼的價值極高（一次性可繞過 2FA），所以絕對不能放在以下位置：

- 截圖存在手機相簿（雲端同步即外洩）
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
- 高敏感帳號（主 Email、銀行）：另存於 **Aegis**（Android）或 **Raivo OTP**（iOS）做雙保險
- 備援碼：紙本 + 保險箱

**情境 B：已用 1Password、跨裝置體驗優先**
- Authenticator：**1Password 內建 2FA**（與密碼一起填入最順）
- 高敏感帳號：另存於 **Authy**（多裝置同步）
- 備援碼：印出收在抽屜 + 拍照存 KeePassXC 純本地檔

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
