---
title: "Passkey vs Password：2026 還要不要繼續用密碼管理器？"
description: "Passkey 在 Apple / Google / Microsoft 三大平台全面落地後、密碼管理器要不要換掉？本文比較 Passkey 與傳統密碼 + 2FA 在跨裝置同步、釣魚抵抗、帳號救援、企業可用性四維度差異、給三種使用情境推薦組合。"
date: 2026-04-20T10:00:00+08:00
lastmod: 2026-05-25T10:28:00+08:00
canonicalURL: "https://gridtoolsdiary.com/privacy/passkey-vs-password/"
categories: ["privacy"]
tags: ["passkey", "密碼管理器", "FIDO", "webauthn", "雙因素驗證", "資安"]
image: /og-default.jpg
draft: false
---

> 📅 原文發布：2026 年 4 月｜最後更新：2026 年 5 月
> 本文資訊已於 2026 年 5 月對照 FIDO Alliance、Apple、Google、Microsoft 官方文件校對。
> Passkey 規範與平台支援更新較快，建議參考本文後仍至官網確認最新狀態。

Passkey 從 2022 年 Apple WWDC 首次商品化到現在已經四年。Google Account、Microsoft 365、GitHub、X、Adobe、PayPal 等主流服務全部支援，Apple iCloud Keychain / Google Password Manager / 1Password / Bitwarden / Dashlane 全部能存。也就是說——**Passkey 已經不是「未來技術」、是「現在預設選項」**。

<!-- IG-firsthand: 跨生態系（iPhone + Windows）親身踩過 Passkey 不能跨平台同步坑、實際情境驗證跨平台密碼管理器在 Passkey 時代仍必要 -->

對使用者來說、問題從「Passkey 是什麼」變成「我已經付了密碼管理器訂閱、Passkey 出現後還要繼續用嗎？」

本文比較 Passkey 與「傳統密碼 + 2FA」兩種登入方案、從跨裝置同步、釣魚抵抗、帳號救援、企業可用性四個維度評估、並針對三種典型使用情境給明確的推薦組合。文末也處理近期常被問到的兩個問題：**換手機時 Passkey 會不會弄丟？密碼管理器要不要解約省訂閱費？**

## 一、Passkey 到底是什麼？跟密碼差在哪？

Passkey 是 [FIDO Alliance](https://fidoalliance.org/passkeys/) 與 [W3C WebAuthn 工作組](https://www.w3.org/TR/webauthn-3/) 共同制定的無密碼登入規範。技術核心是 **公鑰加密（public-key cryptography）**：

- 註冊帳號時、你的裝置（手機 / 電腦）產生一對「私鑰 + 公鑰」
- **公鑰**送到網站伺服器存著
- **私鑰**永遠留在你裝置的安全晶片（iPhone 的 Secure Enclave / Android 的 Trusted Execution Environment / Windows 的 TPM）裡、**完全不離開裝置**
- 登入時、伺服器送一個隨機 challenge、你的裝置用私鑰簽名後回傳、伺服器用公鑰驗證

這跟傳統密碼最大差別：**伺服器永遠不知道你的「秘密」是什麼**。即使網站被駭、駭客拿到的是公鑰、公鑰沒辦法反推私鑰。

對比傳統密碼：你在 100 個網站用 100 個密碼、就有 100 份秘密散落在 100 個伺服器、任何一個被駭就漏一個密碼（如果你重複用同個密碼、就漏一票帳號）。

## 二、四維度比較表：Passkey vs 密碼 + 2FA

| 維度 | Passkey | 密碼 + 2FA App |
|---|---|---|
| **跨裝置同步** | iCloud Keychain（Apple）/ Google Password Manager（Android+Chrome）/ Microsoft Account（Windows）原生同步；1Password / Bitwarden 跨平台同步 | 密碼管理器負責同步、跟 Passkey 同 |
| **釣魚抵抗** | ✅ 強：Passkey 綁定 domain、釣魚網站無法重用 | ⚠️ 弱：用戶可能在釣魚網站手動輸入密碼 + 2FA 碼 |
| **帳號救援** | ⚠️ 中：Apple ID / Google Account 救援流程相對成熟、第三方 Passkey provider（1Password）有 emergency access | ✅ 強：密碼 + 2FA recovery code 已成熟、用戶熟悉 |
| **企業可用性** | ✅ 強：Microsoft Entra ID / Google Workspace / Okta 全支援 device-bound passkey 滿足 FIDO2 合規 | ⚠️ 中：企業要強制換 2FA App、admin 看不到員工 personal authenticator |
| **新裝置首次登入** | iCloud Sync 自動 / Google Auto-Fill 自動 / 跨生態系需要 QR code 跨裝置 | 密碼管理器 master password 解鎖即可 |
| **離線可用性** | ✅ 私鑰在本地、不需網路 | ✅ 2FA App 用 TOTP 算法、本地產生 |
| **支援網站範圍** | 2026 約 200+ 主流服務、持續擴增中 | 100% 網站支援密碼 |

<!-- IG-data: 四維度比較表整合 FIDO Alliance / WebAuthn 規範 + Google 實證數據、Passkey vs 密碼 + 2FA 並排對照、釣魚抵抗等具體量化差異 -->

關鍵差異點：**釣魚抵抗是 Passkey 的決定性優勢**。依 [Google 2023 年公布的數據](https://blog.google/technology/safety-security/the-beginning-of-the-end-of-the-password/)、Passkey 登入失敗率比密碼低 4 倍、登入速度快 50%。

## 三、Passkey 不是萬靈丹：4 個常見誤解

### 誤解 1：「Passkey 出來、密碼管理器就可以解約了」

**錯**。原因：

1. **Passkey 還沒覆蓋所有網站**——你的銀行 / 政府服務 / 公司內網 / 老舊論壇大多還沒支援、這些網站還是要密碼
2. **密碼管理器 = Passkey 跨生態系同步工具**——如果你 iPhone + Windows 雙生態系、iCloud Keychain Passkey 不能直接同步到 Windows、需要 1Password / Bitwarden / Dashlane 等跨平台密碼管理器當「中介層」
3. **密碼管理器 = 軟體式 password vault + Passkey vault 整合**——2026 主流密碼管理器都加 Passkey 支援（[1Password](https://1password.com/passkeys/) / [Bitwarden](https://bitwarden.com/passwordless-passkeys/) / Dashlane）

### 誤解 2：「Passkey 跟生物辨識是一樣的東西」

**錯**。Touch ID / Face ID 只是 **用來解鎖私鑰** 的本地驗證機制、Passkey 的密碼學核心是公鑰簽名、跟生物辨識本身無關。即使你用 PIN 解鎖、Passkey 安全模型仍然成立。

### 誤解 3：「換手機 Passkey 會全部弄丟」

**部份對部份錯**。情境分流：

- **同生態系換手機**（iPhone → iPhone / Android → Android）→ iCloud Keychain / Google Password Manager 自動同步、所有 Passkey 跟著走
- **跨生態系換手機**（iPhone → Android）→ Apple iCloud Passkey **不能直接搬到** Google Password Manager、要重新註冊（每個網站重新加 Passkey）。這時 1Password / Bitwarden 等跨平台 vault 顯出優勢
- **手機弄丟、沒同步備份**——只剩網站的 account recovery 流程（email reset / SMS / recovery code）。所以 **2FA App 的 recovery code 紙本備份在 Passkey 時代依然重要**

### 誤解 4：「企業強制用 Passkey、員工的 personal 帳號也跟著管」

**錯**。企業 Passkey（FIDO2 device-bound passkey）與 personal Passkey（synced passkey）是兩條軌道、admin 只看得到 organization scope 的 device-bound passkey、看不到員工 iCloud / Google 同步的 personal passkey。這跟 2FA App 時代「公司強制裝 Microsoft Authenticator + 員工自己用 Authy」可共存的邏輯一樣。

## 四、三種使用情境的推薦組合

### 情境 A：個人用、單一生態系（iPhone + Mac、或 Android + Chromebook）

**推薦：直接用平台原生 Passkey + iCloud Keychain / Google Password Manager**

- 不需付費密碼管理器
- iOS 17+ / macOS Sonoma+ / Android 9+ 全內建 Passkey 支援
- 還沒支援 Passkey 的網站、平台原生密碼管理器也夠用
- 唯一風險：跨生態系換手機要重來

### 情境 B：個人用、多生態系（iPhone + Windows PC、或 Android + Mac）

**推薦：1Password / Bitwarden / Dashlane 任一 + Passkey 啟用**

- 密碼管理器當「Passkey + 密碼」跨平台同步中介層
- 想免費 → [Bitwarden 免費版](https://bitwarden.com/pricing/) 已支援 Passkey 同步（個人帳號）
- 已付費 1Password → 直接用、不需換
- 1Password 2026 漲價 33% 後評估換不換、見另一篇分析

詳細密碼管理器選擇邏輯：[Bitwarden vs 1Password：小資族選免費還是付費密碼管理器？]({{< ref "privacy/bitwarden-vs-1password" >}})

### 情境 C：企業 admin 角度導入

**推薦：device-bound Passkey + FIDO2 合規方案**

- Microsoft Entra ID / Google Workspace 已內建支援
- 員工不需訂閱密碼管理器、organization Passkey 直接 enroll
- 不影響員工 personal Passkey
- 詳細 admin 觀察 + 五款 2FA App 風險矩陣見：[2FA Authenticator App 怎麼選？]({{< ref "privacy/2fa-authenticator-app-compare" >}})

## 五、Passkey 還沒解決的兩個問題

### 問題 1：跨生態系同步沒標準

iCloud Keychain Passkey 沒辦法直接同步到 Google Password Manager。FIDO Alliance 2024 年提出 [Credential Exchange Protocol（CXP）草案](https://fidoalliance.org/specifications-credential-exchange-specifications/) 試圖解決，但 2026 還在草案階段、主流平台尚未實裝。短期內想跨生態系、只能靠第三方 vault（1Password / Bitwarden）。

### 問題 2：帳號救援流程倒退到「email reset」

傳統密碼時代、忘記密碼可用 password manager master password 解開 vault 拿密碼。Passkey 時代、忘記 master password 或裝置遺失、第三方 vault provider 大多只有 emergency access（指定信任聯絡人）。沒設定 emergency access 的用戶、只能走網站本身的 account recovery（多半 email reset、有些網站 recovery 流程在 2026 仍很陽春）。

實務建議：每個重要帳號的 recovery code 仍要紙本備份（同 [密碼管理器隱私政策真的讀過嗎？]({{< ref "privacy/password-manager-privacy-policy-compare" >}}) 結論）。

## 六、結論：要不要換掉密碼管理器？

**對單一生態系個人用戶**（iPhone + Mac 或 Android + Chromebook）：可以不訂閱第三方密碼管理器、平台原生 Passkey + iCloud / Google Password Manager 夠用。但仍建議裝個 Bitwarden 免費版當備援（避免哪天 Apple / Google 突然改變策略）。

**對多生態系個人用戶**（iPhone + Windows、跨蘋果 / Google）：繼續訂閱密碼管理器、把 Passkey 存進去當 vault。1Password / Bitwarden / Dashlane 都行、依預算與 UI 偏好挑。

**對企業 admin**：device-bound Passkey + FIDO2 合規方案是 2026 標準做法、員工 personal Passkey 不受影響、共存無衝突。

最重要的結論：**Passkey 不是「密碼的替代」、是「密碼的升級版」**。對絕大多數人來說、答案不是二選一、而是「密碼管理器繼續用、但網站支援 Passkey 時就啟用 Passkey」。
