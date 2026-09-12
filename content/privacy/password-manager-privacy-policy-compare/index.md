---
title: "密碼管理器隱私政策真的讀過嗎？Bitwarden、1Password、Dashlane 條款比較"
date: 2026-02-25
lastmod: 2026-09-13T01:00:00+08:00
description: "密碼管理器存放了你所有的帳密，但你讀過它的隱私政策嗎？本文逐條比較 Bitwarden、1Password、Dashlane 三家的資料蒐集範圍、第三方分享條款與開源稽核透明度，給你一個有依據的評分。"
categories: ["privacy"]
tags: ["bitwarden", "1password", "dashlane", "密碼管理器", "隱私政策"]
image: "password-manager-privacy-policy-compare-hero.webp"
draft: false
---

> 📅 原文發布：2026 年 2 月｜最後更新：2026 年 9 月
> 本文條款內容初版於 2026 年 4 月校對，2026 年 9 月 12 日再次逐條對照三家官方隱私政策現行版本（[Bitwarden](https://bitwarden.com/privacy/)、[1Password](https://1password.com/legal/privacy/) 2025 年 12 月 29 日生效版、[Dashlane](https://www.dashlane.com/privacy) 2026 年 4 月 8 日更新版）；9 月 13 日再補對照 [1Password Cookie Policy](https://1password.com/legal/cookie-policy) 與 [Dashlane Cookie Policy](https://www.dashlane.com/privacy/cookiepolicy)，修正了幾處三家比較的說法，並把結論改成跟評分表一致（評分未變）。
> 文中出現的訂閱價格另於 2026 年 9 月 12 日對照 [Bitwarden 官方定價頁](https://bitwarden.com/pricing/)與 [1Password 官方定價頁](https://1password.com/pricing/personal)重新查證；Dashlane 的價格因官方定價頁未以靜態文字標示，本次改為不列數字。
> 各家政策隨時可能調整，建議參考本文後仍至官方政策頁確認最新版本。

把幾百組帳號密碼全部交給一個 App 保管，但從來沒去讀過這個 App 的隱私政策——這件事比你想的更常見。

大多數人選密碼管理器的邏輯是：推薦文說好用就用、評分高就付費、朋友在用就跟著用。「隱私政策」那個連結在 App 裡點開來通常是十幾頁的法律英文，直接關掉。

但這是一個專門用來存放你所有機密的工具。如果你對任何一個 App 的隱私政策應該有所了解，密碼管理器是排第一個的。

這篇不是功能比較文（[功能與費用比較看這篇](/privacy/1password-price-hike-2026/)），也不是安裝教學。我把三家的隱私政策逐條讀過，整理成你能看懂的格式——它們各自蒐集什麼、會分享給誰、有沒有辦法驗證它們說的是真的。如果你還沒決定要裝哪一款、想先有個「你是哪種人就裝哪個」的選擇框架，可以先看[密碼管理器推薦 2026：6 種情境幫你選對那一個](/privacy/password-manager-recommendation-2026/)，再回頭用這篇逐條檢視隱私條款。

---

## 「零知識」架構：不是你以為的全部保護

三家都有在宣傳「零知識（Zero-Knowledge）架構」，但這個詞的涵蓋範圍比你想的窄很多。

**零知識架構保護的是「密碼庫內容」**——你存的帳號密碼、信用卡號、安全備忘，這些資料在你的裝置上加密後才上傳到伺服器。三家的隱私政策都寫明自己讀不到這些內容，在正常營運下這個說法成立。但它有前提：2026 年初 ETH Zurich 的研究假設「伺服器已被攻破、會主動作惡」，在這個情境下，受測的四家（包含本文這三家）設計都沒有完全守住，細節見下方「ETH Zurich 研究」一段。

**零知識架構保護不了的是「行為數據」**：

- 你什麼時間點開了 App
- 你用了哪些功能（是否開啟了 Autofill、是否查看了外洩報告）
- 你的 IP 位址、裝置型號、作業系統版本
- 你的 Email、姓名、付款方式

這類資料三家的政策都寫了會蒐集，只是寫法詳略、用途和保留時間不同：1Password 與 Dashlane 逐項列出裝置、功能使用等細項；Bitwarden 寫得最概括，服務這邊只說會取得你「使用服務」過程中的個資、並分析服務怎麼被使用，裝置型號、作業系統版本是在官網段落才逐項列出。「零知識」不等於「不蒐集任何你的資料」，這個差距很重要。

---

## [Bitwarden](https://bitwarden.com/) 隱私政策：透明度最高，但有 Google Analytics

**蒐集什麼：**

Bitwarden 政策把服務本身處理的資料分兩類，官網另外處理：
- **密碼庫資料（Vault Data）**：用你掌控的金鑰加密，政策原文寫「Bitwarden cannot access Vault Data.」
- **行政資料（Administrative Data）**：姓名、Email、電話等聯絡資訊、密碼庫裡的項目數量，以及開帳號、使用服務、客服與付款過程中取得的個人資料
- **官網（Site）瀏覽**：另外用 Cookies 與分析工具追蹤（包含 Google Analytics，見下）

**會分享給哪些第三方：**

政策明確列出的第三方服務商類別包括：資料管理、資料庫託管、整合服務、專業服務、資訊安全與身分驗證、Email 通訊、財務作業（授權、帳務）等。政策同時寫明這些服務商「restricted by contract from using Personal Information in any way other than to provide services for Bitwarden」（受合約限制、只能替 Bitwarden 提供服務），也寫明依加州 CCPA 的定義，Bitwarden 不「出售」你的個資（原文：We do not "sell" your Personal Information）。

其中需要注意的是 **Google Analytics**——Bitwarden 政策的分析段寫，他們分析資料是為了「understand how the Site and Bitwarden Service are used」，用的工具「including Google Analytics」，並註明 Google 可能把你在官網的活動跟其他使用 GA 的網站連起來；Cookie 段則寫 GA 追蹤的是官網（Site）上的使用者行為。官方說可以透過 `tools.google.com/dlpage/gaoptout` 退出，但這個追蹤存在本身對一個強調隱私的密碼管理器是個需要留意的細節。（用 GA 的不只 Bitwarden：Dashlane 政策同樣寫明用 Google Analytics；1Password 的隱私政策正文沒點名，但它的 [Cookie Policy](https://1password.com/legal/cookie-policy) 列出的 cookie 清單裡就有 Google Analytics，見下方兩家的段落。）

**資料保留多久：**

行政資料保留到你是客戶的期間，以及法律要求的期限。帳號刪除後依保留政策處理。

**最關鍵的一點：**

Bitwarden 是三家裡**唯一整套開源**的：程式碼公開在 GitHub，任何人都可以自行審查它的安全實作。（Dashlane 在 2023 年也把 Android／iOS App 的原始碼放上 GitHub，但[官方公告](https://www.dashlane.com/blog/mobile-code-now-publicly-available)寫明是非商業授權、無法拿來自行編譯，範圍只到手機 App；1Password 則未開源。）這點 Bitwarden 在[官方稽核說明](https://bitwarden.com/help/is-bitwarden-audited/)裡寫明：「Bitwarden completed a dedicated source code audit and penetration test of the web app by security firm Cure53.」（Bitwarden 已由資安公司 Cure53 完成一次針對網頁版應用程式的專門原始碼稽核與滲透測試。）同一份文件也說明它的加密原則「Bitwarden takes a zero knowledge encryption approach to password management, meaning every piece of information in your vault is encrypted.」（Bitwarden 對密碼管理採取零知識加密，意即你保險庫裡的每一筆資訊都是加密的。）而且這個說明頁把歷年稽核報告的 PDF 直接掛出來（Cure53、Fracture Labs、Mandiant 等），任何人都能下載——這是「可自行驗證」與「只能信任公司說法」的差別。

此外，Bitwarden 是三家裡**唯一官方支援自架**的：[官方自架說明](https://bitwarden.com/help/self-host-an-organization/)寫明「Bitwarden can be run, using Docker, on Linux and Windows machines.」，密碼庫可以放在自己的伺服器上，不必依賴 Bitwarden 公司的雲端。另外還有第三方開發的相容伺服器 Vaultwarden（[專案頁](https://github.com/dani-garcia/vaultwarden)寫明與 Bitwarden 公司無關）。

**管轄地：**

Bitwarden Inc. 總部在加州聖塔芭芭拉，屬美國管轄，是「五眼聯盟」成員國。對強調避開特定司法管轄的用戶，這個地點需要納入考慮。

---

## [1Password](https://1password.com/) 隱私政策：密碼庫保護最明確，但有行銷追蹤、且閉源

**蒐集什麼：**

1Password 政策（2025 年 12 月 29 日生效版）把資料分三類：
- **你主動提供的資料**：聯絡方式、付款資訊、帳號設定偏好
- **自動蒐集**：技術使用資訊（IP、裝置、瀏覽器）、功能互動模式、診斷資料
- **來自第三方**：行銷平台、整合服務的資料（需管理員授權時）

「蒐集多少」這件事要分開看。第三方評測 [CyberInsider 的 1Password vs Bitwarden 比較](https://cyberinsider.com/password-manager/comparison/1password-vs-bitwarden/)（2026 年 2 月 21 日）比對兩家政策後，認為 1Password「collects slightly less personal data」；但它比的是兩家都會蒐集的帳號層個資（使用者名稱、Email、IP、付款方式、裝置資訊），只比了 1Password 和 Bitwarden 兩家，也沒有討論行銷追蹤。而 1Password 自己的政策寫明，它和行銷夥伴會用 cookie 等追蹤技術蒐集你在官網「和產品」上的互動資訊，用途包含廣告（原文：1Password and our marketing partners use cookies and other tracking technologies to collect information about your interactions with our websites and products for essential, functional, analytical, and advertising purposes），也會從行銷平台等第三方取得你的資料。這條要跟它的 [Cookie Policy](https://1password.com/legal/cookie-policy) 對著讀：Cookie Policy 寫明網頁版密碼庫與各平台 App 裡不使用第三方追蹤器（原文：We do not use third-party trackers in our web application (my.1password.com), or our client applications for macOS, Windows, Linux, Android or iOS），所以行銷夥伴的 cookie 實際放在官網；但隱私政策也寫明，1Password 自己會用你用了哪些產品或功能、瀏覽活動等資訊來優化廣告投放（原文：We use information about how you use our sites and Services, such as products or features used, … and browsing activity to optimize the delivery of our advertisements）。所以本文不採用「1Password 蒐集最少」這個說法。

1Password 真正站得住的強項在密碼庫本身：[官方隱私政策](https://1password.com/legal/privacy/)在資料所有權這一段寫得很明確：「Your Secure Data is your property. We claim no rights to it beyond those necessary to deliver Services to you.」（你的加密資料是你的財產，我們主張的權利僅限於向你提供服務所必要的範圍。）同一份文件並載明「We have no way of accessing or sharing Secure Data in a readable format or decrypting it, and we never receive copies of unencrypted Secure Data.」（我們無法以可讀格式存取或分享你的加密資料、也無法解密它，而且我們從不會收到未加密資料的副本。）——這是「正常營運下他們在技術上看不到你存了什麼」的官方依據（伺服器被攻破的情境見下方 ETH 研究段落）。

**會分享給哪些第三方：**

政策列出：支援服務的服務商（政策寫明他們只能用資料提供受託的服務、不得拿去做自己的直接行銷）、行銷夥伴、商業帳號的管理員（組織帳號情境下）、法律要求時的主管機關。

行銷夥伴那一條的原文是：「Marketing Partners. We may disclose your information to third-party marketing services which help us advertise our services to you. This may be considered a sale or sharing personal information data under applicable privacy laws.」——也就是 1Password 會把你的資訊揭露給幫它投廣告的第三方行銷服務商，政策自己也承認這在部分隱私法下可能算「出售或分享」個資。Cookie Policy 給的退出方式是到官網頁尾「Your Privacy Choices」，取消勾選「Sharing or sale of personal information」；瀏覽器開啟 Global Privacy Control（GPC）訊號，在官網上也會被當成退出。

**最重要的安全機制——Secret Key：**

1Password 有一個競品沒有的設計：**Secret Key**。這個密鑰在你設定帳號時在你的裝置上本地生成，不上傳到 1Password 伺服器。登入時使用 SRP（Secure Remote Password）協定，密碼本身不需要傳輸到網路上就能完成驗證——[官方說明](https://support.1password.com/secret-key-security/)的原話是「Someone who attempts a brute-force attack on our servers won’t be able to decrypt your data without your Secret Key, which we never have.」（有人對我們的伺服器發動暴力破解，沒有你的 Secret Key 也解不開你的資料）。要注意它防的是暴力破解；下方 ETH 研究處理的「伺服器本身被攻破、主動作惡」情境下，1Password 同樣被找出攻擊方式。（Dashlane 在你開啟兩步驟驗證後，也會把一把「User Secondary Key」併入密碼庫加密，但依 [Dashlane 架構說明](https://support.dashlane.com/hc/en-us/articles/32877446916498-3-Architecture-overview)，這把金鑰是在 Dashlane 伺服器端產生、通過 2FA 驗證後才發給你；1Password 的 Secret Key 則是在你的裝置上產生、公司手上沒有。Bitwarden 的[安全白皮書](https://bitwarden.com/help/bitwarden-security-white-paper/)寫明加密金鑰由主密碼加上 Email 當 salt 推導，沒有對應的第二把密鑰。）

**但核心問題在這裡：**

1Password 是**閉源的**。你沒辦法自己讀程式碼驗證它說的安全設計是不是真的在執行。你只能依賴它的第三方稽核與認證——確實有做（[官方稽核說明](https://support.1password.com/security-assessments/)列了 Independent Security Evaluators 等機構的評估，並持有 ISO 27001／27017／27018／27701 與 SOC 2 Type 2），但報告的取得方式跟 Bitwarden 不同：年度滲透測試報告自 2025 年 11 月 3 日起集中放在 1Password Trust Center，SOC 2 報告要另外申請，不像 Bitwarden 把每份報告 PDF 直接掛在說明頁上。

這不代表 1Password 不安全，它的信任基礎是多年的企業聲譽、稽核記錄、和 AgileBits 公司的誠信——只是這個信任是「信任公司」，不是「可以自己驗證的技術事實」。

**管轄地：**

1Password / AgileBits 總部在加拿大多倫多，同屬五眼聯盟。

---

## [Dashlane](https://www.dashlane.com/) 隱私政策：保留期限寫得最具體，但有兩條廣告分享條款、[VPN](https://zh.wikipedia.org/wiki/%E8%99%9B%E6%93%AC%E7%A7%81%E4%BA%BA%E7%B6%B2%E8%B7%AF) 另走第三方

**蒐集什麼：**

Dashlane 蒐集的帳號層個資跟另外兩家同類（細節見下方評分說明），政策寫得最細的是資料保留時間：

- **帳號刪除後 30 天內**：註冊資料（Registration Data）最多保留 30 天；裝置資料不刪除，但會在 30 天內匿名化
- **IP 位址**：生產日誌保留 45 天，備份另保留 1 年
- **支援錄音**：最多保留 2 年
- **Secured Data（加密密碼庫）**：帳號刪除時一併刪除；超過 13 個月未活動的帳號會被自動刪除，密碼庫也跟著刪

保留期限這一項，Dashlane 在三家中寫得最具體。Bitwarden 和 1Password 都沒有給天數：Bitwarden 寫行政資料保留到「as long as you are a customer of Bitwarden and as required by law」，至少把期限綁在「你還是不是客戶」這個看得到的時間點；1Password 寫保留「for as long as necessary to fulfill the purposes set forth in this Privacy Notice」，除非法律要求更久或你指示刪除（原文：unless a longer retention period is required or permitted by law, or you instruct us to delete your information）——你沒主動要求刪除時，要保留多久由它自己判斷什麼叫「必要」。Dashlane 則給出了具體的天數。

**VPN 第三方問題——只在你用內建 VPN 時才相關：**

Dashlane Premium 內建 VPN，但這個 VPN 不是 Dashlane 自己做的，而是跟 **Hotspot Shield** 合作——[Dashlane 官方部落格](https://www.dashlane.com/blog/improved-vpn-experience)原文是「Dashlane has partnered with Hotspot Shield to offer a fast, more-reliable VPN experience to our Premium customers—directly through Hotspot Shield's app.」。

既然是「直接透過 Hotspot Shield 的 App」使用，這代表：

1. 你使用 VPN 功能時，你的流量走的是 Hotspot Shield 的服務
2. Hotspot Shield 是另一家公司、有自己的使用條款和隱私政策
3. Dashlane 隱私政策對 Secured Data 的保證（傳輸與儲存都加密、Dashlane 自己沒有金鑰）講的是密碼庫內容；政策全文沒有提到 VPN，所以這份保證管不到你透過 VPN 產生的網路流量

換句話說，你以為在用一個隱私工具，但 VPN 的部分跑在 Hotspot Shield 的服務上，要看的是 Hotspot Shield 的隱私條款。

<!-- IG-synthesis: 把 Dashlane 隱私政策對 Secured Data 的加密保證（政策全文沒有提到 VPN）與官方部落格「VPN 跟 Hotspot Shield 合作、直接透過 Hotspot Shield 的 App 使用」交叉讀，得出前者涵蓋不到 VPN 流量這個結論——兩份文件各自都沒把這件事講出來，是跨文件對照才看得到的邊界 -->

**分析工具——同樣用 Google Analytics：**

Dashlane 政策（2026 年 4 月 8 日更新版）「Service Improvement and Analytics」段寫，他們會用你的個資分析你怎麼使用服務，包括哪些功能最常用、哪些最少用，接著直接寫「For example, we use Google Analytics for this purpose.」（例如，我們用 Google Analytics 做這件事），並附上退出 GA 的連結。也就是說，用 Google Analytics 這一點 Dashlane 和 Bitwarden 一樣（1Password 的 Cookie Policy 也列了 GA cookie）。寫法上有一個差別：Bitwarden 政策寫 Google 可能把你在官網的活動跟其他用 GA 的網站連起來；Dashlane 的 [Cookie Policy](https://www.dashlane.com/privacy/cookiepolicy) 則寫它的 _ga cookie 只屬於自家官網，Google 不能用它跨不相關的網站追蹤特定使用者（原文：The cookie is unique to the Site and cannot be used by Google to track a specific user or browser across unrelated websites）。

**行銷用途資料分享：**

Dashlane 政策明確說，他們會把**雜湊過的 Email 和裝置 ID** 提供給服務商，用來優化廣告投放（政策舉的例子是讓現有用戶不會在其他網站看到 Dashlane 的廣告），緊接著寫明這些服務商「prohibited from using this information for any other purpose」（不得挪作其他用途）。但政策在分享資料那一節開頭的白話摘要（政策註明各節摘要只供參考、嚴格來說不屬於政策條文）寫得更直接：「We share hashed user emails and device ids with advertisers to refine advertising efforts」——摘要裡交出去的對象直接寫成廣告商（advertisers），不是條文裡的「服務商」。另外，你點了廣告連到 Dashlane 官網時，Dashlane 會把一個識別碼傳給導流網站計算成效，政策自己寫這在加州隱私法下被視為「分享」（sharing）；政策同時寫明從不拿個資換錢或換其他對價。雜湊過的 Email 雖然不是明文，但這個用途本身就代表對方能用雜湊值比對出「這是同一個人」——這個分享行為對一個密碼管理器來說，算是一個值得留意的條款。

而且雜湊 Email 那條不是 Dashlane 唯一的廣告分享條款。政策「Marketing and Advertising」一節的「Interest-based advertising」另寫，Dashlane 和第三方廣告夥伴會用 cookie、pixel 等技術，蒐集你在服務內、Dashlane 發出的通訊、以及「other third-party online services over time」（一段時間內你在其他第三方網路服務上）的互動，用來投放它們認為你會感興趣的廣告；同一段接著寫「We may also share information about our users with these companies to facilitate interest-based advertising to those or similar users on other online properties.」——這一條泛稱「information about our users」，也沒有附上「不得挪作他用」的限制，那個限制只綁在雜湊 Email／裝置 ID 那一條。（Dashlane 的 Cookie Policy 另寫明 cookie 只用在官網，任何 App、包括瀏覽器擴充套件都不用 cookie。）政策給的退出方式寫在「Automated Decision Making and Profiling」段：「Disabling all but essential cookies or setting the slider to “active” on the Do Not Sell or Share my Personal Information page will prevent this.」——也就是關掉非必要 cookie，或到「Do Not Sell or Share my Personal Information」頁把開關切到 active。

**免費方案已於 2025 年 9 月停用：**

依 [Dashlane 官方公告](https://www.dashlane.com/blog/dashlane-free-ending)，免費方案在 2025-09-16 停止，之後舊免費帳號不能新增、編輯、複製，**連查看都不行，只能匯出**（原文：You will no longer be able to add to, edit, copy, or view your data in Dashlane, just export it）。官方給的**最後期限是 2026-09-16**：在那之前要升級付費方案或把資料匯出，否則會失去資料存取權。如果你讀到這裡時已經過了這個日期、舊帳號裡還有資料，請直接到官方公告頁或 Dashlane 客服確認現在還有沒有辦法取回。

**管轄地：**

Dashlane 總部在美國紐約，子公司在法國巴黎。跨司法管轄，適用 [GDPR](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) 和 CCPA。

---

## 三家橫向比較評分

<!-- IG-angle: 用「零知識架構保護不到的行為數據」當切角，把三家隱私政策拆成六個可比維度（政策透明度／資料蒐集量／第三方分享條款／開源稽核透明度／自架脫離廠商可能性／保留條款具體性）逐項評分——這套維度是本文自訂的比較框架，不是任何一家官方文件的分類方式 -->

以下評分基於官方政策文件、公開稽核資料與第三方技術評測（初版查證日：2026-04-26；2026-09-12 再次對照政策與稽核頁原文後，調整了資料蒐集量、第三方分享條款、自架三個維度的評分與說明；2026-09-13 補對照 1Password 與 Dashlane 的 Cookie Policy 後，修正了隱私政策透明度、資料蒐集量、第三方分享條款、資料保留條款具體性四個維度的說明，星等未變）。

| 評分維度 | Bitwarden | 1Password | Dashlane |
|---|---|---|---|
| 隱私政策透明度 | ★★★★★ | ★★★★☆ | ★★★★☆ |
| 資料蒐集量 | ★★★★☆ | ★★★☆☆ | ★★★☆☆ |
| 第三方分享條款 | ★★★★☆ | ★★★☆☆ | ★★★☆☆ |
| 開源 / 稽核透明度 | ★★★★★ | ★★★☆☆ | ★★★☆☆ |
| 自架 / 脫離廠商可能性 | ★★★★★ | ★★☆☆☆ | ★★☆☆☆ |
| 資料保留條款具體性 | ★★★☆☆ | ★★☆☆☆ | ★★★★★ |

**補充說明各維度：**

**隱私政策透明度**：Bitwarden 開源 + 稽核報告 PDF 直接公開是最強的。1Password 與 Dashlane 各少一顆星，扣的是同一件事——外人沒辦法像查 Bitwarden 那樣自己驗證：1Password 閉源，滲透測試報告集中在 Trust Center、SOC 2 報告要另外申請；Dashlane 公開的只有手機 App 原始碼（非商業授權、無法自行編譯）。Dashlane 給出具體保留天數是加分，但補不回這一顆。要說明的是，這一維的加扣分理由和下面「開源／稽核透明度」「資料保留條款具體性」兩維重疊——Bitwarden 的開源與公開報告、Dashlane 的保留天數，等於各被算了兩次；這一維請當成那兩維的綜合印象來讀，不是另一個獨立的證據。

**資料蒐集量**：三家都蒐集帳號層的個資（Email、付款、IP、裝置資訊），也都記錄你的密碼庫存了多少：Bitwarden 記「the number of items」，Dashlane 記存了幾筆帳密，1Password 記得最細——政策寫它蒐集「the number of vaults, number and types of items in vaults, who may access your vaults, and when and from where vaults are accessed」（有幾個保險庫、裡面有幾筆、哪些類型、誰能存取、何時從哪裡存取）。三家也都用 Google Analytics：Bitwarden 與 Dashlane 在隱私政策裡點名，1Password 隱私政策正文沒點名，但它的 Cookie Policy 列出的 cookie 清單裡就有。所以差別不在用不用 GA，而在蒐集延伸到哪裡、拿去做什麼。Bitwarden 也分析服務本身怎麼被使用，加州段落列出的用途也包含廣告與行銷、衡量廣告曝光，但政策沒有寫到讓第三方廣告夥伴蒐集你的資料，還寫明不跨第三方網站追蹤官網訪客（原文：We do not track visitors to the Site across third-party websites），資料來源也只寫你和官網、服務的互動；它少的一顆星在用了 GA（Cookie 段寫明 GA 追的是官網上的行為，分析段註明 Google 可能把你在官網的活動跟其他用 GA 的網站連起來）。1Password 隱私政策寫明它和行銷夥伴用 cookie 等追蹤技術蒐集你的互動、用途包含廣告，也會從行銷平台、公開資料庫等來源取得你的資料；它的 Cookie Policy 則把其中一類 cookie 歸為「Sale or Share of Personal Information Cookies」，寫明這類 cookie 幫它和廣告夥伴依你「across websites and online services」（跨網站與線上服務）的互動投放個人化廣告，同時寫明第三方追蹤器不放在網頁版密碼庫和 App 裡。Dashlane 除了在 App 內記錄事件資料（例如開了哪些功能、存了幾筆帳密）、記錄官網訪客來之前有沒有看過 Dashlane 的廣告，興趣廣告段還寫明它和第三方廣告夥伴會用 cookie、pixel 等技術，蒐集你在服務內、Dashlane 發出的通訊、以及「other third-party online services over time」上的互動，用來投放興趣廣告（Dashlane 的 Cookie Policy 寫明 App 與瀏覽器擴充套件都不用 cookie）；它也會從社群媒體、評論網站、論壇等公開來源取得使用者資料。後兩家都把蒐集延伸到廣告用途、而且涵蓋你在其他網站上的活動，所以同給三星。常被引用的「1Password 蒐集最少」，本文查到的出處（CyberInsider）只比了 1Password 與 Bitwarden 的帳號層個資、沒有討論行銷追蹤，撐不起三家排名，所以不採用。

**第三方分享條款**：三家都有服務商條款：Bitwarden 與 1Password 寫明服務商受合約限制、只能用這些資料替它們提供服務；Dashlane 條文寫的是只在提供服務所需的範圍內分享給服務商（原文：solely as required to provide the Services）；分享段開頭的白話摘要另寫這些服務商「contractually obliged to comply with Privacy Laws」（受合約約束、須遵守隱私法），但政策註明各節摘要只供參考、不屬於政策條文。判準是看最重的那一項：只到分析工具（Google Analytics）這一層的給四星，會把資料交給廣告相關第三方的給三星。Bitwarden 寫明不「出售」個資，政策也沒有把資料交給廣告夥伴的條款，但用了 Google Analytics（政策註明 Google 可能把你在官網的活動跟其他網站連起來），所以不給滿分。1Password 與 Dashlane 同樣用 GA，扣分點在更重的廣告條款：1Password 會把「your information」揭露給幫它投廣告的第三方行銷服務商，政策自己寫這可能構成隱私法下的「出售或分享」；Dashlane 把雜湊過的 Email／裝置 ID 交給服務商優化廣告，另把點廣告導流時傳出的識別碼認列為加州法下的「分享」。兩家的條款也說不上誰比較緊：Dashlane 雜湊 Email 那條講清楚交出去的是哪兩種資料、並寫明對方不得挪作他用（白話摘要則直接寫成交給廣告商），但它的興趣廣告段另寫會把「information about our users」分享給廣告夥伴、用於在其他網路平台對你或相似用戶投放廣告，這一條同樣泛稱、沒有用途限制；1Password 行銷夥伴那一條也泛稱「your information」、沒有列出資料種類。兩家都有泛稱的廣告分享條款、都會把資料交給廣告相關的第三方，所以同給三星。

**開源 / 稽核透明度**：Bitwarden 的差距主要在這一維度——整套程式碼開源可自行審查、稽核報告直接公開下載；Dashlane 只公開了手機 App 的原始碼（非商業授權），1Password 未開源。1Password 與 Dashlane 同給三星，是因為兩家各公開了一部分、但都做不到 Bitwarden 那樣整套自己查：1Password 可查的是第三方稽核與認證（程式碼不公開；年度滲透測試報告要進 Trust Center、SOC 2 報告要另外申請），Dashlane 可看的是部分原始碼（只有手機 App，而且是非商業授權、無法自行編譯）。兩家離 Bitwarden「整套開源＋稽核報告直接下載」都還差一段，所以同分。

**自架 / 脫離廠商可能性**：只有 Bitwarden 官方支援自架（另有第三方相容伺服器 Vaultwarden）。不使用 Bitwarden 公司的雲端服務就可以使用 Bitwarden，這在三家中是唯一做到的。1Password 和 Dashlane 都不能自架、只能用官方雲端，兩家能做的都是把資料匯出後換平台（1Password 可匯出 .1pux 或 CSV；Dashlane 連停用的舊免費帳號都保留匯出功能，但只到 2026-09-16 前），所以同給兩星。

**資料保留條款具體性**：Dashlane 給出註冊資料 30 天、IP 日誌 45 天加備份 1 年、客服錄音最多 2 年等具體期限；Bitwarden 沒給天數，但把行政資料的保留期綁在「你還是客戶的期間」加上法律要求；1Password 的主條款是保留到「達成政策所列目的所必要」的期間（除非法律要求更久，或你指示刪除），你沒主動要求刪除時要多久由它自己判斷，所以比 Bitwarden 再少一星。

---

## 2026 年 ETH Zurich 研究：伺服器被攻破時，三家都有破口

這一點值得單獨提，因為評估隱私政策時不能忽略底層安全現況。

瑞士聯邦理工學院（ETH Zurich）應用密碼學小組與義大利語瑞士大學（USI）的研究人員在 2026 年 1 月發表論文〈Zero Knowledge (About) Encryption: A Comparative Security Analysis of Four Cloud-based Password Managers〉（[IACR ePrint 2026/058](https://eprint.iacr.org/2026/058)，1 月 14 日收錄），ETH Zurich 在 2 月 16 日發了[新聞稿](https://ethz.ch/en/news-and-events/eth-news/news/2026/02/password-managers-less-secure-than-promised.html)。他們檢驗的不是日常使用的情境，而是更嚴格的一種：**假設密碼管理器的伺服器已經被攻破、會主動作惡**，廠商宣稱的「零知識」還守不守得住。論文摘要列出的攻擊數量是 Bitwarden 12 種、[LastPass](https://www.lastpass.com/) 7 種、Dashlane 6 種、1Password 6 種，嚴重程度從竄改特定用戶的保險庫，到整個組織的保險庫全數淪陷都有，其中多數攻擊能還原出密碼。研究團隊已事先通報廠商，論文發表時修補仍在進行中。（ETH 新聞稿只列 Bitwarden、LastPass、Dashlane 三家；1Password 的 6 種在論文裡。）

ETH 新聞稿提到各家修補的速度不一，但這件事說明的不是「不能用密碼管理器」，而是：

**你信任一個密碼管理器的條件，不是「它說自己安全」，而是「它有沒有機制讓你驗證它是安全的、出事時有沒有快速的修補程序」。**

在這個標準下，Bitwarden 開源的優勢最大——漏洞被發現時，外界可以直接看程式碼確認問題範圍與修補狀況，而不是只能等廠商公告。但也要把另一面講清楚：在這份研究裡，Bitwarden 被找出的攻擊數是四家最多的（12 種）。開源讓外界比較容易檢查，不代表設計本身比較沒有破口。（Bitwarden 的[稽核清單](https://bitwarden.com/help/is-bitwarden-audited/)上另列有一份 2025 年由 ETH Zurich 應用密碼學小組、以「伺服器完全惡意」為前提做的密碼學稽核報告。）

---

## 缺點不省略

**Bitwarden 的現實限制：**

- 免費版不含 TOTP（[2FA](https://en.wikipedia.org/wiki/Multi-factor_authentication) 整合），需升 Premium（$19.80/年）才有
- 行動版 App 設計陽春，視覺體驗明顯不如 1Password
- 使用了 Google Analytics，對極度重視隱私的用戶是矛盾點（Dashlane 政策同樣寫明用 GA，1Password 的 Cookie Policy 也列了 GA cookie，這一點不是 Bitwarden 獨有）
- 自架（官方版或第三方的 Vaultwarden）都需要懂 Docker，普通用戶不適合

**1Password 的現實限制：**

- 閉源，信任基礎是公司聲譽 + 稽核報告，不是可自行驗證的程式碼
- 政策寫明會把你的資訊揭露給幫它投廣告的第三方行銷服務商，你在官網上的互動會被它和行銷夥伴用 cookie 等技術追蹤（Cookie Policy 寫明網頁版密碼庫與 App 裡不放第三方追蹤器），它自己也會用你的產品使用情況優化廣告投放——和 Dashlane 的廣告條款屬同一類問題
- 資料保留期限沒給天數：政策寫保留到「達成政策所列目的所必要」的期間，你沒主動要求刪除時要保留多久由它自己判斷（Dashlane 則逐項寫出天數）
- 無免費方案，只有 14 天試用；想長期免費使用沒有這個選項
- 2026 年漲價 33% 後，$47.88/年 的 CP 值明顯下降；官方定價頁另有新客直接在 1Password.com 訂閱的首年促銷價（個人版 $2.99/月），但只適用第一年，之後回到原價（詳見[1Password 漲價評測](/privacy/1password-price-hike-2026/)）

**Dashlane 的現實限制：**

- 免費方案已於 2025 年 9 月停用（官方定價頁仍有 Premium 14 天免費試用），而且年費金額在[官方個人方案定價頁](https://www.dashlane.com/pricing-personal)是動態載入的、查不到靜態標價，付錢前得自己開一次官網對
- 舊免費帳號只剩匯出功能，依 [Dashlane 官方公告](https://www.dashlane.com/blog/dashlane-free-ending)，最後期限 2026-09-16 前沒有升級或匯出就會失去資料存取權——期限前還能自己匯出；過了期限，請直接看官方公告或問 Dashlane 客服還有沒有辦法取回
- 會把雜湊過的 Email／裝置 ID 交給服務商優化廣告投放（政策的白話摘要直接寫成交給廣告商）；興趣廣告段另寫會和第三方廣告夥伴蒐集你在服務內、通訊與其他第三方網路服務上的互動，並把使用者資訊分享給他們，在其他網路平台對你或相似用戶投放廣告，這一條沒有用途限制。政策給的退出方式是關掉非必要 cookie，或到「Do Not Sell or Share my Personal Information」頁把開關切到 active（原文：Disabling all but essential cookies or setting the slider to “active” on the Do Not Sell or Share my Personal Information page will prevent this）。1Password 也有同性質的行銷夥伴條款，見上
- 內建 VPN 由第三方 Hotspot Shield 提供，這部分不在 Dashlane 的隱私聲明保護範圍內——只在你用這個 VPN 時才相關
- 政策寫明用 Google Analytics 分析服務使用情況——這一點和 Bitwarden 一樣（1Password 的 Cookie Policy 也列了 GA cookie）

---

## 結論：如果隱私是你唯一的判斷標準

直接說結論，不模糊：

**最注重隱私政策透明度的選擇：Bitwarden**

整套開源可自行審查、稽核報告直接公開、官方支援自架——這三點在本文比較的三家裡只有 Bitwarden 同時做到。如果你對「我怎麼知道你說的是真的」這個問題有強烈需求，在這三家裡 Bitwarden 最能給你「你可以自己查」這個答案。只是別把開源等同於沒有漏洞：上面 ETH 的研究裡，Bitwarden 被找出的攻擊數反而最多。

**1Password 與 Dashlane：條款打平，差在一把裝置端的密鑰**

照上面的評分表，1Password 和 Dashlane 六個維度裡有五個同分，唯一分出高下的是資料保留條款：Dashlane 逐項寫出天數（註冊資料 30 天、IP 日誌 45 天加備份 1 年、客服錄音最多 2 年），1Password 只寫保留到「達成政策所列目的所必要」的期間。所以單看隱私政策條款，Dashlane 不輸 1Password，保留期限還寫得更具體。在「少被拿去投廣告」這件事上兩家誰也不比誰好：兩家都有泛稱「your information」「information about our users」、沒有列出資料種類的廣告分享條款，也都用 cookie 追蹤你在官網上的互動。

1Password 多出來的東西不在條款、在架構：Secret Key 在你的裝置上產生、公司手上沒有，官方原文寫沒有它，對伺服器暴力破解也解不開你的資料。Dashlane 對應的 User Secondary Key 則是在伺服器端產生、而且要開啟兩步驟驗證才會有。（伺服器被攻破、主動作惡的情境下，兩家都被找出攻擊方式，見上方 ETH 研究。）

所以這兩家的排序取決於你要比哪一層：

- **比政策條款**（保留期限寫得多具體）→ Dashlane 略勝，勝在保留期限。
- **比密碼庫多一層保護**（萬一伺服器上的資料被拿走、有人拿去暴力破解）→ 1Password 勝，勝在裝置端的 Secret Key。

兩家跟 Bitwarden 比都有一段距離：閉源或只公開部分原始碼、不能自架、都有廣告分享條款。1Password 漲價後的 $47.88/年 值不值得，要另外評估（見前篇）。

**Dashlane 的內建 VPN：只在你會用它時才算數**

Dashlane Premium 內建的 VPN 由 Hotspot Shield 提供，只有你真的用這個 VPN，流量才會走到 Dashlane 隱私政策管不到的地方；不用它，這一點跟你無關，前面的條款比較也沒有把它算進任何一個評分維度。如果你正是為了內建 VPN 才考慮 Dashlane，那跟 Bitwarden 比它處於劣勢：買一個獨立的 VPN（[NordVPN](https://nordvpn.com/) 或 [ProtonVPN](https://protonvpn.com/)）加上 Bitwarden 免費版，比訂 Dashlane Premium 在隱私保護上更可控。「更可控」指的是兩件事：一是 VPN 由你自己挑、自己讀它的隱私條款，而不是跟著方案綁一家你沒選過的 Hotspot Shield——例如 Proton VPN 的[隱私政策](https://protonvpn.com/privacy-policy)寫明「Proton VPN is a no-logs VPN service」、不記錄使用者的流量，NordVPN 則在[官方部落格](https://nordvpn.com/blog/nordvpn-no-logs-assurance-engagement-2025/)公布 Deloitte 於 2025 年底對它的無紀錄（no-logs）聲明做的第六次獨立確信（報告全文要登入 Nord 帳號才看得到）；二是 Bitwarden 的隱私政策沒有把資料交給廣告夥伴的條款，不像 Dashlane 有雜湊 Email 與興趣廣告兩條廣告分享條款。跟 1Password 比則是另一回事：Dashlane 條款面不輸，差在沒有裝置端產生的第二把密鑰，這一點跟 VPN 無關。

**最後說一件更根本的事：**

正常營運下，三家的設計都讓廠商讀不到你的密碼庫內容，這個基礎是成立的；但 ETH 的研究也提醒了，伺服器一旦被攻破，四家受測產品的設計都沒有完全守住——「零知識」是基本門檻，不是免死金牌。隱私政策裡另一個真正值得在意的，是密碼庫以外的行為數據——你什麼時間點開 App、用了什麼功能、IP 是什麼——這類資料三家都在蒐集（政策寫法詳略不同），差異在會不會拿去做廣告、寫得透不透明、保留多久。讀隱私政策的目的，不是期待找到一個「什麼都不蒐集」的工具，而是知道你在用的工具蒐集了什麼，然後做出有依據的選擇。

---

相關文章：

- [密碼管理器推薦 2026：6 種情境，幫你選對那一個](/privacy/password-manager-recommendation-2026/)
- [1Password 漲價 33% 後還值得訂嗎？2026 家庭版 vs 個人版 vs Bitwarden 試算](/privacy/1password-price-hike-2026/)
- [Bitwarden vs 1Password：小資族選免費還是付費密碼管理器？](/privacy/bitwarden-vs-1password/)
- [Bitwarden 好用嗎？免費開源密碼管理器三個月真實評測](/privacy/bitwarden-review/)
