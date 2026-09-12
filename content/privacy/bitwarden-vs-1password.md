---
title: "Bitwarden vs 1Password：小資族選免費還是付費密碼管理器？"
date: 2023-02-01
lastmod: 2026-09-13T00:19:00+08:00
categories: ["privacy"]
tags: ["Bitwarden", "1Password", "密碼管理器", "資安工具", "隱私安全"]
description: "Bitwarden 免費版 vs 1Password 付費版，差在哪裡？功能、安全性、價格逐項比較，直接說哪個值得用。"
image: /images/bitwarden-vs-1password.jpg
draft: false
---

> 📅 原文發布：2023 年 2 月｜最後更新：2026 年 9 月
> ⚠️ 定價更新：[Bitwarden](https://bitwarden.com/) Premium 於 2026 年 1 月 21 日從 $10 漲至 $19.80/年（[官方公告](https://bitwarden.com/blog/bitwarden-launches-enhanced-premium-plan/)；舊價見 [Internet Archive 存的 2025 年 11 月官方定價頁](https://web.archive.org/web/20251115091230/https://bitwarden.com/pricing/)「$10/Year」）；[1Password](https://1password.com/) 於 2026 年 3 月 27 日起調漲（新價在當天或之後的第一次續訂套用）。
> 本文所有價格已於 2026 年 9 月 12 日對照 [Bitwarden 官方定價頁](https://bitwarden.com/pricing/)與 [1Password 官方定價頁](https://1password.com/pricing/personal)逐筆查證（1Password 定價頁另掛新客首年促銷價，本文一律以原價計）。
> 平台規則隨時可能調整，建議參考本文後仍至官網確認最新條件。

---

## 兩個工具分別是什麼

密碼管理器解決一件事：你不可能記住所有帳號的獨立強密碼，它幫你記，你只需要記一個主密碼。

[Bitwarden](/privacy/bitwarden-review/) 是開源的密碼管理器，有完全免費的版本。1Password 是主打體驗設計和功能整合的付費工具，沒有真正的免費方案（只有 14 天試用）。

---

## 基本資料

<!-- IG-data: 兩家 2026 年漲價後的價格於 2026-09-05 逐筆對照官方定價頁後並排，直接讀得出一個對照：1Password 個人版 $47.88/年（1 人）與 Bitwarden 家庭版 $47.88/年（最多 6 人）年費完全相同，同一筆錢涵蓋的人數上限差 6 倍——這是兩邊官方定價頁各看各的時看不到的 -->

| 項目 | Bitwarden | 1Password |
|---|---|---|
| 免費方案 | 有（功能完整，長期可用）| 無（14 天試用）|
| 個人付費方案 | $19.80/年（Premium）| $47.88/年（Individual）|
| 家庭方案 | $47.88/年，最多 6 人 | $71.88/年，最多 5 人 |
| 開源 | 是 | 否 |
| 無限密碼（免費版）| 是 | — |
| 跨裝置同步（免費版）| 是 | — |
| 第三方安全稽核 | 每年找外部資安公司稽核，[稽核清單與報告](https://bitwarden.com/help/is-bitwarden-audited/)公開；[SOC 2](https://en.wikipedia.org/wiki/System_and_Organization_Controls) Type II、SOC 3、ISO 27001 等認證（[官方合規頁](https://bitwarden.com/compliance/)）| 有第三方稽核，ISO 27001／27017／27018／27701 與 SOC 2 Type 2 等多項認證（[官方稽核說明](https://support.1password.com/security-assessments/)）|

---

## Bitwarden 免費版到底夠不夠用

對大多數人來說是夠的。

免費版包含：無限密碼儲存、無限裝置同步、基本[兩步驟驗證](https://en.wikipedia.org/wiki/Multi-factor_authentication)（TOTP app 或 email）、資料外洩基本檢查、文字型的安全傳輸功能（Send）。這些對個人日常使用幾乎已經覆蓋完整。

不包含的項目：整合式 TOTP 驗證碼產生器、加密附件上傳、緊急存取、保險庫健康報告。這些是 Premium（$19.80/年）的範圍。

如果你只是要儲存密碼、跨裝置同步、基本的兩步驟保護，Bitwarden 免費版就能用，不需要付費。

---

## 1Password 多出什麼

**Travel Mode（旅行模式）** 是 1Password 獨有的功能：出入邊境前可以暫時隱藏指定的保險庫，只留你願意讓人看到的資料。這對商務出差、常出國的人有實際意義。

**Watchtower** 是整合式的密碼健康監控，自動通知你哪些帳號被外洩、密碼太弱、重複使用。這一塊 Bitwarden 已經追上來：2026 年 1 月 21 日的 Premium 改版加了「保險庫健康警示」與密碼提醒（[官方公告](https://bitwarden.com/blog/bitwarden-launches-enhanced-premium-plan/)：Identify and resolve vulnerabilities and risks to your digital security — reused, exposed, or weak passwords），所以兩家付費版在這一塊的差距已經不大；只有 Bitwarden 免費版沒有這些提醒。

**TOTP 驗證器整合** 在 1Password 所有付費方案都包含，密碼和驗證碼在同一個地方管理。但這一項不是 1Password 獨有：Bitwarden Premium（$19.80/年）同樣能產生 TOTP 驗證碼（見下面的功能對照表），所以如果你只是想「密碼和驗證碼放一起」，不需要為此付 1Password 的價格。

---

## 安全性

兩者都採 AES-256 加密、零知識架構。至於「有沒有出過事」，這篇不替任何一家做「從未出事」的保證：Bitwarden 在 2026 年 4 月 22 日有約一個半小時，命令列工具（CLI）的 npm 套件 2026.4.0 版被植入惡意程式，官方[事件聲明](https://community.bitwarden.com/t/bitwarden-statement-on-checkmarx-supply-chain-incident/96127)表示目前沒有發現用戶保險庫資料被存取、正式環境也沒有被入侵；2026 年 2 月 ETH Zurich 的研究則在「伺服器被攻破」的假設下，對兩家都找出了攻擊方式（Bitwarden 12 種、1Password 6 種，[論文](https://eprint.iacr.org/2026/058)），細節見[隱私政策比較那篇](/privacy/password-manager-privacy-policy-compare/)。

1Password 額外有 Secret Key 機制——帳號密碼 + Secret Key 雙重驗證才能登入新裝置，即使密碼洩露也無法只用密碼入侵。1Password 在[官方 Secret Key 說明](https://support.1password.com/secret-key-security/)裡寫明這把密鑰的關鍵特性：「Your Secret Key was created on your own device. We have no record of your Secret Key and can't recover it.」（你的 Secret Key 是在你自己的裝置上產生的，我們沒有任何紀錄，也無法復原它。）同一份文件也載明「Like your account password, your Secret Key is never sent to us.」（如同你的帳號密碼，你的 Secret Key 從不會傳送給我們。）同一頁也寫明它的用途：「Someone who attempts a brute-force attack on our servers won’t be able to decrypt your data without your Secret Key, which we never have.」（有人對我們的伺服器發動暴力破解，沒有你的 Secret Key 也解不開你的資料。）——也就是說，就算伺服器上的加密資料被偷走，光猜到你的密碼還不夠。（它防的是暴力破解；前面提到的 ETH 研究處理的是伺服器本身被攻破、主動作惡的情境，那是另一回事。）Bitwarden 沒有 Secret Key 這個設計；它的做法是每年找外部公司稽核並公開報告，[稽核清單](https://bitwarden.com/help/is-bitwarden-audited/)上列的有 Cure53（多份）、Fracture Labs（2024、2025 年網頁版與網路元件）、Mandiant 等，另有 SOC 2 Type II 認證（[官方合規頁](https://bitwarden.com/compliance/)）。

Bitwarden 是開源的，代碼公開可審查，這對在意透明度的人是加分。這不是我幫它說好話，Bitwarden 在[官方安全說明](https://bitwarden.com/help/is-bitwarden-audited/)的「Codebase on GitHub」段落裡直接寫：「Bitwarden is focused on open source software with the entirety of the codebase available on github.com.」（Bitwarden 專注於開源軟體，整套程式碼都公開在 github.com 上。）開源的具體意義就在這句——你不用「相信」它安全，可以自己（或讓資安研究員）去看程式碼。1Password 不開源，信任基礎是第三方稽核與認證（ISO 27001／27017／27018／27701、SOC 2 Type 2，見[官方稽核說明](https://support.1password.com/security-assessments/)）；Bitwarden 同樣有 ISO 27001 與 SOC 2，再加上程式碼公開。

實際上，兩者的安全基礎都是可信任的，差距主要在功能和體驗，不在安全性本身。如果你對手機 App 的資安風險有更廣泛的疑問，可以參考[掛機 App 資安風險評估](/earn-apps/passive-app-security/)。

---

## 三個功能對照

| 功能 | Bitwarden Free | Bitwarden Premium | 1Password Individual |
|---|---|---|---|
| 無限密碼 + 裝置同步 | ✓ | ✓ | ✓ |
| TOTP 驗證碼產生 | — | ✓ | ✓ |
| 緊急存取（指定聯絡人）| — | ✓ | —（沒有這個功能；[Emergency Kit](https://support.1password.com/emergency-kit/) 是存有帳號資料的 PDF，由你自己保管、也可以交一份給信任的人，不是系統內建的授權機制）|
| Travel Mode | — | — | ✓ |
| 密碼健康監控／提醒 | 基本 | 健康報告＋健康警示（2026 年 1 月新增）| Watchtower |
| 年費 | $0 | $19.80 | $47.88 |

---

## 誰該用哪個

**用 Bitwarden 免費版**：你的需求就是儲存密碼、跨裝置同步、基本兩步驟保護，不需要其他功能。這個組合是市場上性價比最高的選項，永久免費而且功能完整。

**升 Bitwarden Premium**：你想要 TOTP 整合、緊急存取、完整健康報告，但不想花 1Password 的價格。在本站比較過、查得到官方價格的付費方案裡（1Password、Proton Pass 等），$19.80/年是最便宜的一個。

**選 1Password**：你需要 Travel Mode、或者重視體驗設計的整合感。只是想把密碼和驗證碼放在一起的話，Bitwarden Premium 就做得到，不構成選 1Password 的理由。

---

## 結論

大多數人適合 Bitwarden 免費版，沒有理由付錢。如果你的密碼管理需求超過基本範圍，Bitwarden Premium $19.80/年是升級的第一步，不需要直接跳到 1Password 的價位。

1Password 的 $47.88/年不是貴到不合理，但它相對 Bitwarden Premium 多出的主要是 Travel Mode 和整體介面體驗，要真的用到才值得，不是為了「感覺更安全」而付費。

先用 Bitwarden 免費版一個月，如果沒感覺到限制，就繼續用；如果有，再評估哪個付費方案適合你的使用模式。

在挑哪一款之前，還有一個更前面的問題值得想：Passkey 在三大平台落地後，密碼管理器到底還要不要繼續用？[Passkey vs 密碼管理器的四維度比較](/privacy/passkey-vs-password/)把這件事說清楚——結論是兩者目前並存而非取代，所以選一款密碼管理器仍然成立。

→ [Bitwarden 官網（免費版）](https://bitwarden.com)｜[1Password 官網](https://1password.com)

---

📌 本文部分連結為聯盟行銷連結，透過連結購買後我會收到一小筆佣金，不影響你的費用，也不影響本文的評測立場。
