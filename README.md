# VPS 價格：拆解月付 $6.9 到 $500 的價差來源，附 DMIT 洛杉磯、香港、東京全方案價格表與選購建議

搜「VPS 價格」的人，心裡通常有兩個版本的問題。第一個是「現在行情大概多少」，第二個才是真正卡住人的那個：「為什麼看起來一樣的 1 核 2G，有人賣 $6.9 一個月，有人賣 $39.9？」

先講結論：CPU 和記憶體幾乎不是價差的主因。真正讓帳單翻好幾倍的，是流量用完之後會發生什麼事、回國路由走哪條線，以及你買的是月付還是年付。這篇用 DMIT 的方案當樣本拆給你看——它在洛杉磯、香港、東京三個機房各開了 Premium、Eyeball、Tier 1 三條產品線，剛好把「價格階梯」這件事擺得很清楚。

## 先確定你要付的是哪一種錢

同樣標 1 核 2G，DMIT 洛杉磯就有三個幾乎同規格、價格卻不同的選擇：

- Tier 1 TINY：1 核 1G、20G SSD、2000GB 流量、4Gbps 端口，**$6.90/月**
- Premium TINY：1 核 2G、20G SSD、1000GB 流量、1Gbps 端口，**$10.90/月**
- Eyeball TINY：1 核 2G、20G SSD、1500GB 流量、2Gbps 端口，**$10.90/月**

Tier 1 給的記憶體和流量都更多，價格卻最低。差別只有一個：它的路由是純國際 BGP，沒有針對中國大陸做優化。如果你的使用者在新加坡、德國或美國本地，選 T1 是省錢；如果使用者主要在中國大陸，T1 在晚高峰的表現就不是同一回事。

所以第一步不是比價，是先回答「我的流量要往哪個方向跑」。

## 三個真正決定帳單的變數

### 1. 流量超量之後怎麼處理

這是很多低價方案真正貴的地方。常見處理方式有三種：直接停機、按 GB 加收、降速但繼續跑。DMIT 採第三種，官方在各方案頁標明超量後的限速值。

以洛杉磯 AS3 為例，Pro 系列 TINY 到 STARTER 超量後降到 4Mbps，MINI 以上是 8Mbps，MEDIUM 是 10Mbps；Tier 1 系列則寬鬆得多，超量後還有 100Mbps 到 500Mbps。同樣「流量用完」，一個月內你還能跑多少東西，差距就是這樣出來的。

有整理文章提到 DMIT 的流量是雙向計算（上下行都算），如果你的業務是上傳導向，選方案前值得先確認這一點。

### 2. 計費週期

DMIT 的價格表通常同時給月付和年付。拿 Tier 1 來看：TINY 月付 $6.90，年付攤下來約 $6.9×12；而 WEE 是 $36.90/年、每月 1000GB 流量，換算約等於每月 $3.08。

年付的 WEE 比月付的 TINY 便宜一半以上，代價是流量從 2000GB 降到 1000GB，而且必須一次付清一年。這筆帳划不划算，取決於你確定這個節點會用滿 12 個月，還是三個月後就想換機房。

### 3. IP 與附加資源

原生 IP、IPv4 + IPv6 雙棧、以及被牆後換 IP 的規則，都會反映在價格裡。有第三方整理提到 DMIT 每 15 天可免費更換一次被牆 IP，其他情況收費；實際規則請以官網政策頁為準，這類條款變動頻率高。

## DMIT 三條線路的定位差異

| 線路 | 路由特徵 | 大陸訪問表現 | 適合誰 | 起價 |
| --- | --- | --- | --- | --- |
| Premium（Pro） | 自有骨幹 + 中國電信 CN2 GIA | 最穩，晚高峰波動最小 | 對大陸訪問有硬要求 | 洛杉磯 $10.90/月 |
| Eyeball（EB） | Tier 1 + CMIN2 / 9929 等盡力優化 | 中等，行動網路較佳 | 預算優先但要好過普通線路 | 洛杉磯 $10.90/月 |
| Tier 1（T1） | 純國際 BGP，無大陸專項優化 | 不保證 | 國際業務、備援、CI/CD、中轉 | 三機房皆 $6.90/月 |

官網也提供 Looking Glass 與測試 IP 供下單前摸底，例如香港 Premium 的測試 IP 是 103.117.100.199。先 ping 再付錢，比看任何評測都準。

## 洛杉磯 LAX.AS3 全方案價格表

平台為 AMD EPYC 7003，以下為月付價。

**Premium（三網 CN2 GIA 回程）**

| 方案 | 配置 | 流量 / 帶寬 | 超量後 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- |
| TINY | 1 核 / 2G / 20G | 1000GB @ 1Gbps | 4Mbps | $10.90/月 | [ 查看洛杉磯 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| Pocket | 2 核 / 2G / 40G | 1500GB @ 4Gbps | 4Mbps | $16.90/月 | [ 查看洛杉磯 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| STARTER | 2 核 / 2G / 80G | 3000GB @ 10Gbps | 4Mbps | $34.90/月 | [ 查看洛杉磯 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| MINI | 4 核 / 4G / 80G | 5000GB @ 10Gbps | 8Mbps | $62.90/月 | [ 查看洛杉磯 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| MICRO | 4 核 / 4G / 160G | 7000GB @ 10Gbps | 8Mbps | $87.90/月 | [ 查看洛杉磯 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| MEDIUM | 6 核 / 8G / 160G | 14000GB @ 10Gbps | 10Mbps | $199.90/月 | [ 查看洛杉磯 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |

**Eyeball（CMIN2 / 9929）**

| 方案 | 配置 | 流量 / 帶寬 | 超量後 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- |
| TINY | 1 核 / 2G / 20G | 1500GB @ 2Gbps | 4Mbps | $10.90/月 | [ 查看洛杉磯 Eyeball 方案](https://www.dmit.io/aff.php?aff=12046) |
| Pocket | 2 核 / 2G / 40G | 3000GB @ 4Gbps | 4Mbps | $16.90/月 | [ 查看洛杉磯 Eyeball 方案](https://www.dmit.io/aff.php?aff=12046) |
| STARTER | 2 核 / 2G / 80G | 5000GB @ 10Gbps | 4Mbps | $34.90/月 | [ 查看洛杉磯 Eyeball 方案](https://www.dmit.io/aff.php?aff=12046) |
| MINI | 4 核 / 4G / 80G | 10000GB @ 10Gbps | 8Mbps | $62.90/月 | [ 查看洛杉磯 Eyeball 方案](https://www.dmit.io/aff.php?aff=12046) |
| MICRO | 4 核 / 4G / 160G | 14000GB @ 10Gbps | 8Mbps | $87.90/月 | [ 查看洛杉磯 Eyeball 方案](https://www.dmit.io/aff.php?aff=12046) |
| MEDIUM | 6 核 / 8G / 160G | 30000GB @ 10Gbps | 10Mbps | $199.90/月 | [ 查看洛杉磯 Eyeball 方案](https://www.dmit.io/aff.php?aff=12046) |

EB 和 Pro 在 TINY 到 MEDIUM 這幾檔價格完全一樣，差異體現在流量給得多、端口更大，但路由檔次低一階。同樣 $34.90，EB 給 5000GB，Pro 給 3000GB——這 2000GB 就是你為 CN2 GIA 付的錢。

**Tier 1（國際 BGP）**

| 方案 | 配置 | 流量 / 帶寬 | 超量後 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- |
| WEE | 1 核 / 1G / 20G | 1000GB @ 4Gbps | 100Mbps | $36.90/年 | [ 查看洛杉磯 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| TINY | 1 核 / 1G / 20G | 2000GB @ 4Gbps | 200Mbps | $6.90/月 | [ 查看洛杉磯 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| STARTER | 2 核 / 2G / 40G | 4000GB @ 10Gbps | 200Mbps | $12.90/月 | [ 查看洛杉磯 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| MINI | 2 核 / 4G / 80G | 8000GB @ 10Gbps | 200Mbps | $21.90/月 | [ 查看洛杉磯 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| MICRO | 4 核 / 4G / 120G | 16000GB @ 10Gbps | 500Mbps | $32.90/月 | [ 查看洛杉磯 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |

洛杉磯另有 AN4（EPYC 9004）與 AN5（EPYC 9005）平台的同檔位方案，規格相近但定價高於 AS3，價差依平台與補貨批次變動，這裡不列具體數字，避免你照著舊價下單。

## 香港 HKG 方案價格表

香港距離大陸最近，也是三個機房裡價格最高的一個。Tier 1 系列價格與洛杉磯相同，Pro 系列則直接跳一個量級。

**Premium（AS3，EPYC 7003）**

| 方案 | 配置 | 流量 | 價格 | 購買 |
| --- | --- | --- | --- | --- |
| TINY | 1 核 / 1G / 20G | 500GB @ 1Gbps | $39.90/月 | [ 查看香港 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| STARTER | 1 核 / 2G / 40G | 1000GB @ 1Gbps | $79.90/月 | [ 查看香港 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| MINI | 2 核 / 2G / 60G | 1500GB @ 1Gbps | $126.90/月 | [ 查看香港 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| MICRO | 2 核 / 4G / 80G | 2000GB @ 1Gbps | $179.90/月 | [ 查看香港 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| MEDIUM | 4 核 / 4G / 160G | 2500GB @ 1Gbps | $239.90/月 | [ 查看香港 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |

**Premium（AN5，EPYC 9005）**

| 方案 | 配置 | 流量 | 價格 | 購買 |
| --- | --- | --- | --- | --- |
| MINI | 2 核 / 2G / 80G | 1500GB @ 1Gbps | $149.90/月 | [ 查看香港 AN5 方案](https://www.dmit.io/aff.php?aff=12046) |
| MICRO | 2 核 / 4G / 160G | 2000GB @ 1Gbps | $159.90/月 | [ 查看香港 AN5 方案](https://www.dmit.io/aff.php?aff=12046) |
| MEDIUM | 4 核 / 4G / 160G | 2500GB @ 1Gbps | $180.00/月 | [ 查看香港 AN5 方案](https://www.dmit.io/aff.php?aff=12046) |
| LARGE | 4 核 / 8G / 320G | 3000GB @ 1Gbps | $240.00/月 | [ 查看香港 AN5 方案](https://www.dmit.io/aff.php?aff=12046) |
| GIANT | 8 核 / 16G / 640G | 6000GB @ 1Gbps | $500.00/月 | [ 查看香港 AN5 方案](https://www.dmit.io/aff.php?aff=12046) |

**Tier 1（國際 BGP）**

| 方案 | 配置 | 流量 / 帶寬 | 超量後 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- |
| WEE | 1 核 / 1G / 20G | 1000GB @ 4Gbps | 50Mbps | $36.90/年 | [ 查看香港 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| TINY | 1 核 / 1G / 20G | 2000GB @ 4Gbps | 100Mbps | $6.90/月 | [ 查看香港 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| STARTER | 1 核 / 2G / 40G | 4000GB @ 10Gbps | 100Mbps | $12.90/月 | [ 查看香港 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| MINI | 2 核 / 2G / 60G | 8000GB @ 10Gbps | 100Mbps | $21.90/月 | [ 查看香港 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| MICRO | 4 核 / 4G / 80G | 16000GB @ 10Gbps | 200Mbps | $32.90/月 | [ 查看香港 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| MEDIUM | 4 核 / 8G / 160G | 32000GB @ 10Gbps | 200Mbps | $49.90/月 | [ 查看香港 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| LARGE | 8 核 / 16G / 320G | 64000GB @ 10Gbps | 500Mbps | $99.90/月 | [ 查看香港 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| GIANT | 8 核 / 24G / 640G | 128000GB @ 10Gbps | 1Gbps | $199.90/月 | [ 查看香港 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |

香港 Tier 1 的 STARTER 只要 $12.90 就有 4TB 流量，比同價格的洛杉磯 T1 STARTER 多了一倍記憶體。缺點已經說過了：它的路由不為大陸優化，電信使用者買 T1 可能出現延遲比美西更高的情況。

## 東京 TYO 方案價格表

東京 Premium 是三個機房裡最容易被忽略的一檔，但它的入門價比香港低不少。

| 方案 | 線路 | 配置 | 流量 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- |
| TINY | Premium | 1 核 / 1G / 20G | 500GB @ 1Gbps | $21.90/月 | [ 查看東京 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| TINY | Tier 1 | 1 核 / 1G / 20G | 2000GB | $6.90/月 | [ 查看東京 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| STARTER | Tier 1 | 1 核 / 2G / 40G | 4000GB | $12.90/月 | [ 查看東京 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| MINI | Tier 1 | 2 核 / 2G / 60G | 8000GB | $21.90/月 | [ 查看東京 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| MICRO | Tier 1 | 4 核 / 4G / 80G | 16000GB | $32.90/月 | [ 查看東京 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| MEDIUM | Tier 1 | 4 核 / 8G / 160G | 32000GB | $49.90/月 | [ 查看東京 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| LARGE | Tier 1 | 8 核 / 16G / 320G | 64000GB | $99.90/月 | [ 查看東京 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |
| GIANT | Tier 1 | 8 核 / 24G / 640G | 128000GB | $199.90/月 | [ 查看東京 Tier 1 方案](https://www.dmit.io/aff.php?aff=12046) |

東京 Premium 的 STARTER 以上方案同樣在售，價格依配置遞增，介於香港同檔與洛杉磯同檔之間，這裡不逐一列出未經交叉確認的數字。另外，東京 Eyeball 系列已在先前下架，香港 Eyeball 也曾出現下線後又恢復庫存的情況——這條線的供應狀況比其他兩條不穩定。

## 年付、季付、月付：折扣實際省多少

DMIT 的折扣有兩種來源，別混在一起看。

第一種是官方直接寫在價格表裡的週期折扣。有整理資料提到洛杉磯 Pro 系列的 TINY 年付約 75 折、其他方案年付約 9 折，而且不需要輸入優惠碼。這種折扣最實在，因為它不會過期。

第二種是優惠碼。多個第三方整理文章都提到 `LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF`，適用於洛杉磯 Eyeball TINY 以上、季付或更長週期，屬循環折扣；另一組 `Lite-Annually-Recur-30OFF` 與 `Lite-Semi-Annually-Recur-20OFF` 則對應年付 7 折、半年付 8 折。

幾點提醒：

1. 這些代碼的名稱裡就寫明了適用產品線和付款週期，填錯組合不會生效。
2. 帶年份字樣的節慶碼（例如 2025 聖誕系列）通常有期限，整理文章收錄不代表現在還能用。
3. 結帳頁有驗證按鈕，按下去能算出來的才算數。

年付的另一個隱性成本是彈性。用季付多花一點、三個月後發現線路不合再換，通常比鎖一年便宜。

## 按預算挑：三種常見情境

**每月 $10 以內。** 洛杉磯 Tier 1 TINY $6.90 是最低門檻，2000GB 流量、4Gbps 端口，國際業務夠用。如果使用者在大陸，多花 $4 上 Premium TINY 或 Eyeball TINY（都是 $10.90），換到 CN2 GIA 或 CMIN2 路由，這 $4 買的是晚高峰的穩定度。

[👉 直接比較 $10 以內的三條線路方案](https://www.dmit.io/aff.php?aff=12046)

**每月 $15 到 $40。** 洛杉磯 Pro Pocket $16.90 是這一檔裡配置和價格最平衡的選擇：2 核 2G、40G SSD、1500GB 流量、4Gbps 端口。需要更多儲存和流量就往上到 STARTER $34.90，80G SSD 加 3000GB。香港這一檔只有 Tier 1 可選，如果想要香港 Pro，預算得拉到 $39.90 起。

**每月 $60 以上、或需要香港節點。** 洛杉磯 MINI（$62.90）給 4 核 4G 和 5TB（Pro）或 10TB（EB）流量，適合有多站點或高併發需求的場景。香港 Pro TINY $39.90 的配置其實很低（1 核 1G、500GB），它的價格幾乎全花在 CN2 GIA 路由和香港的地理位置上——如果你不需要香港 IP，同樣的錢在洛杉磯能買到規格高好幾倍的機器。

## 常見問題

**付款方式有哪些？** 多個整理文章一致提到支援支付寶、微信支付、PayPal 和信用卡，並提供中文客服。

**流量用完會直接停機嗎？** 不會。DMIT 的方案都是超量後降速繼續跑，限速值寫在方案頁上，從 4Mbps 到 1Gbps 不等。選方案時這個數字比流量額度更值得看。

**可以先測速再買嗎？** 可以，官網提供 Looking Glass 與各機房測試 IP。正式部署前先 ping 一輪，比看任何人的評測都可靠。

**庫存一直變動是正常的嗎？** 是。DMIT 的庫存補貨與下架頻繁，洛杉磯 AS3 多次補貨，熱門款（例如 Pocket）常在短時間內售完。你看到這篇文章時的價格和庫存，可能已經和整理時不同，實際仍以下單頁顯示為準。

[👉 查看 DMIT 目前實際在售方案與價格](https://www.dmit.io/aff.php?aff=12046)

**價格之外還要考慮什麼？** 一個常被忽略的點：官方對新平台（例如洛杉磯 AS3）曾提示仍處於持續優化階段，磁碟效能與 SLA 可能低於成熟平台，建議先在測試環境驗證再放正式業務。這種提示比價格差幾美元重要得多。
