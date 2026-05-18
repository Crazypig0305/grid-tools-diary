---
title: "掛機 App 耗電耗流量實測：Honeygain vs EarnApp vs Repocket 哪個最省手機資源？"
date: 2023-03-15
lastmod: 2026-04-16
categories: ["earn-apps"]
tags: ["Honeygain", "EarnApp", "Repocket", "掛機App", "耗電測試"]
description: "掛機 App 到底多耗電？Honeygain、EarnApp、Repocket 三款在同一支手機實測，告訴你對電池和流量的真實影響。"
image: /images/passive-app-compare.jpg
draft: false
---

> 📅 原文發布：2023 年 3 月｜最後更新：2026 年 4 月
> [EarnApp](https://earnapp.com/) 已於 2025 年改為按時計費，收益數字與原測試期間不同，請參閱個別評測文章。本文聚焦於資源消耗（電力、流量），這部分測試結果仍具參考性。
> 平台規則隨時可能調整，建議參考本文後仍至官網確認最新條件。

---

## 測試動機

如果要在手機上長時間跑掛機 App，電池和流量消耗是實際要花的成本。理論上「跑著就有錢」，但如果每個月多耗 5 GB 流量、手機壽命縮短，這些都算在帳裡。

這篇記錄的是我在同一支 Android 手機、相同時段、相同 Wi-Fi 環境下，分別跑三款 App 的耗電和流量數據。

---

## 測試環境

- 裝置：Android 手機（6,000 mAh 電池）
- 連線：家用 Wi-Fi（200 Mbps 光纖）
- 測試方式：每款 App 連跑 7 天，記錄系統電池用量統計和每日流量
- 計算基準：App 在背景運行（螢幕關閉）的耗電量

---

## 電池消耗數據

| App | 7 天平均每日耗電 | 佔總耗電比例 |
|---|---|---|
| [Honeygain](https://www.honeygain.com/) | 3–5% | 中等 |
| EarnApp | 2–4% | 偏低 |
| [Repocket](https://repocket.com/) | 4–6% | 中等偏高 |

三款在螢幕關閉、Wi-Fi 維持連線的狀態下耗電量都在可接受範圍。充電習慣正常的話，背景跑這些 App 不會讓手機電池撐不過一天。

耗電的主要來源不是 App 本身的運算，而是維持網路連線的電力。這類掛機 App 本質上屬於[住宅代理（residential proxy）](https://en.wikipedia.org/wiki/Proxy_server#Residential_proxy)網路，會在背景持續維持連線、轉發第三方流量請求，所以即使運算負荷低、連線保持本身就有電力成本。這表示如果你的手機本來就長時間在 Wi-Fi 環境下，額外的電耗增量其實不多。

---

## 流量消耗數據

這個差異比電耗更明顯。

| App | 7 天總流量使用 | 每日平均 |
|---|---|---|
| Honeygain | 約 280–420 MB | 40–60 MB/天 |
| EarnApp | 約 350–700 MB | 50–100 MB/天 |
| Repocket | 約 140–350 MB | 20–50 MB/天 |

流量差異比較大，因為這直接取決於平台當下的需求量，不是固定值。同樣的裝置和時段，某天可能用 200 MB，另一天可能不到 50 MB。

### 三款 App 資源消耗對照圖

把上面兩張表用同一張圖呈現，每天耗電與每天流量的差距能直接看出來：

<figure class="ig-chart" role="img" aria-label="三平台耗電與流量雙軸對比，EarnApp 最省電但流量最多">
<svg viewBox="0 0 720 360" xmlns="http://www.w3.org/2000/svg" style="width:100%;height:auto;background:#F3F6FB;font-family:'Noto Sans TC','IBM Plex Sans',sans-serif;">
  <text x="360" y="28" text-anchor="middle" font-size="16" font-weight="600" fill="#1F4E8E">三款掛機 App 7 天實測資源消耗</text>
  <text x="360" y="48" text-anchor="middle" font-size="12" fill="#5A6B82">Android 6,000 mAh + 200 Mbps Wi-Fi + 螢幕關閉背景運行</text>

  <line x1="80" y1="80" x2="80" y2="280" stroke="#1F4E8E" stroke-width="1.5"/>
  <line x1="80" y1="280" x2="680" y2="280" stroke="#1F4E8E" stroke-width="1.5"/>
  <line x1="680" y1="80" x2="680" y2="280" stroke="#E2943E" stroke-width="1.5"/>

  <text x="70" y="85" text-anchor="end" font-size="11" fill="#1F4E8E">8%</text>
  <text x="70" y="135" text-anchor="end" font-size="11" fill="#1F4E8E">6%</text>
  <text x="70" y="185" text-anchor="end" font-size="11" fill="#1F4E8E">4%</text>
  <text x="70" y="235" text-anchor="end" font-size="11" fill="#1F4E8E">2%</text>
  <text x="70" y="285" text-anchor="end" font-size="11" fill="#1F4E8E">0</text>

  <text x="40" y="180" text-anchor="middle" font-size="11" fill="#1F4E8E" font-weight="500" transform="rotate(-90 40 180)">每日耗電 %</text>

  <text x="690" y="85" font-size="11" fill="#E2943E">120</text>
  <text x="690" y="135" font-size="11" fill="#E2943E">90</text>
  <text x="690" y="185" font-size="11" fill="#E2943E">60</text>
  <text x="690" y="235" font-size="11" fill="#E2943E">30</text>
  <text x="690" y="285" font-size="11" fill="#E2943E">0</text>

  <text x="715" y="180" text-anchor="middle" font-size="11" fill="#E2943E" font-weight="500" transform="rotate(-90 715 180)">每日流量 MB</text>

  <rect x="140" y="180" width="40" height="100" fill="#1F4E8E"/>
  <text x="160" y="172" text-anchor="middle" font-size="11" fill="#1F4E8E" font-weight="600">3-5%</text>
  <rect x="185" y="155" width="40" height="125" fill="#E2943E"/>
  <text x="205" y="147" text-anchor="middle" font-size="11" fill="#E2943E" font-weight="600">40-60</text>
  <text x="182" y="305" text-anchor="middle" font-size="13" fill="#1F4E8E" font-weight="500">Honeygain</text>

  <rect x="320" y="205" width="40" height="75" fill="#1F4E8E"/>
  <text x="340" y="197" text-anchor="middle" font-size="11" fill="#1F4E8E" font-weight="600">2-4%</text>
  <rect x="365" y="105" width="40" height="175" fill="#E2943E"/>
  <text x="385" y="97" text-anchor="middle" font-size="11" fill="#E2943E" font-weight="600">50-100</text>
  <text x="362" y="305" text-anchor="middle" font-size="13" fill="#1F4E8E" font-weight="500">EarnApp</text>

  <rect x="500" y="155" width="40" height="125" fill="#1F4E8E"/>
  <text x="520" y="147" text-anchor="middle" font-size="11" fill="#1F4E8E" font-weight="600">4-6%</text>
  <rect x="545" y="220" width="40" height="60" fill="#E2943E"/>
  <text x="565" y="212" text-anchor="middle" font-size="11" fill="#E2943E" font-weight="600">20-50</text>
  <text x="542" y="305" text-anchor="middle" font-size="13" fill="#1F4E8E" font-weight="500">Repocket</text>

  <rect x="200" y="330" width="14" height="10" fill="#1F4E8E"/>
  <text x="220" y="339" font-size="11" fill="#5A6B82">每日耗電（%）</text>
  <rect x="370" y="330" width="14" height="10" fill="#E2943E"/>
  <text x="390" y="339" font-size="11" fill="#5A6B82">每日流量（MB）</text>
</svg>
<figcaption style="font-size:13px;color:#5A6B82;margin-top:8px;">資料來源：Android 系統電池用量統計 + 各 App 後台流量紀錄、7 天連跑取每日平均值。注意：流量為平台需求決定、非固定值；耗電主要來自維持網路連線、非運算負荷。</figcaption>
</figure>

---

## 行動網路 vs Wi-Fi 的差距

以上數據都是在 Wi-Fi 環境測的。如果你打算用行動數據跑掛機 App，情況完全不同。

月租 30 GB 的門號，光是掛機 App 一個月就可能消耗 1–3 GB，佔總配額的 3–10%。考慮到收益通常只有幾塊美金，在行動數據上跑幾乎不划算。這三款 App 都建議只在 Wi-Fi 環境下執行，[Honeygain 官方使用條款](https://www.honeygain.com/terms-of-use/)亦明示需在使用者可控的設備與網路上運行，Honeygain 和 Repocket 甚至在設定裡有「僅 Wi-Fi」選項。

---

## 手機發熱

長時間背景跑網路任務會讓手機溫度略高，但這三款都是輕量級的流量轉發，不是高運算負荷的工作。實測過程中手機溫度比看 YouTube 還低，不構成過熱問題。

---

## 對電池壽命的長期影響

這個比較難量化，但有一個基本判斷：

鋰電池的壽命和充放電次數有關，也和工作溫度有關。如果掛機 App 讓你每天多充一次電，長期下來確實有影響。但如果你本來就會定時充電、溫度也正常，多跑一個輕量背景 App 的邊際影響很小。

---

## 三款排序

**最省資源：EarnApp > Repocket > Honeygain**（流量層面 Repocket 較省，電耗層面 EarnApp 較省）

**流量最穩定：** 三款都有明顯的流量波動，沒有一款能保證每天固定量。

**建議使用條件：** 家用 Wi-Fi + 長時間不用的舊手機或備用裝置，是跑這類 App 最划算的組合。主力手機建議評估電池用量後再決定。

---

## 結論

三款掛機 App 對電池的影響在正常使用情境下算是可接受的，流量消耗的差異比電耗更值得關注。

如果你的網路有流量上限、或者這支手機是主力機，建議設定「僅 Wi-Fi」並觀察一週的流量消耗，再決定要不要長期跑。備用手機、吃到飽的 Wi-Fi 環境，跑起來的成本最低。

---

📌 本文為資源消耗測試評比，不含推薦連結。如需了解各平台出金方式與手續費，見[三款掛機 App 出金體驗比較](/earn-apps/passive-app-payout-compare/)。安裝前若對資安有疑慮，可先看[掛機 App 資安風險評估](/earn-apps/passive-app-security/)。
