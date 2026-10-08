<a name="zh"></a>

# 胖蛇大作戰 Gaboon Viper（原名 GUTSY／腸腸久久）

<p align="center">
  <img src="https://raw.githubusercontent.com/mkjohnny1003/esimmanager-web/main/assets/gutsy-icon.png" alt="Gaboon Viper Icon" width="108" height="108" style="border-radius: 22px;">
</p>

<p align="center">
  <strong>吃得下，不一定消化得了。</strong><br>
  <em>Eat big. Regret slowly.</em>
</p>

<p align="center">
  <a href="https://apps.apple.com/app/id6812165648"><img src="https://img.shields.io/badge/App_Store-Download-0D96F6?style=for-the-badge&logo=apple&logoColor=white" alt="Download on App Store"></a>
  <a href="https://getesimmanager.com/gutsy/play/"><img src="https://img.shields.io/badge/Web_Demo-Play_Online-22c55e?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Play Online Demo"></a>
  <img src="https://img.shields.io/badge/Version-v2.0.3-f59e0b?style=for-the-badge" alt="Version 2.0.3">
  <img src="https://img.shields.io/badge/Palette-GBA_/_8--SHADE_/_4--DMG-8b5cf6?style=for-the-badge" alt="Palettes">
  <img src="https://img.shields.io/badge/License-MIT-gray?style=for-the-badge" alt="License">
</p>

<p align="center"><strong>中文</strong> ｜ <a href="#english">English</a></p>

---

## 📖 專案簡介 (Overview)

**胖蛇大作戰（Gaboon Viper，原名 GUTSY／腸腸久久）** 是一款融合經典掌機點陣美學與真實消化負重機制的**革新派貪食蛇遊戲**。

傳統貪食蛇吃下食物立即變長；而在胖蛇大作戰中，吃下的食物會化為**體內腫塊（Lumps）**，隨著爬行步伐逐漸向尾端蠕動消化。過量進食會使胃容量超載而**撐爆暴斃（BURST）**，但長時間不進食又會引發**飢餓萎縮枯竭（STARVE）**！

本倉庫為 **胖蛇大作戰網頁純前端試玩版（Web Playable Prototype）**，零外部相依套件，採用原生 HTML5 Canvas + Web Audio API 打造，即開即玩。

👉 **[線上即刻試玩（官方網站）](https://getesimmanager.com/gutsy/play/)**

---

## 🚀 v2.0.3 更新：改名「胖蛇大作戰」＋搶食蛇 (What's New)

iOS 版 **v2.0.3** 已送交 App Store 審查（通過後自動更新）；本網頁試玩版已搶先同步：
* 🐍 **更名「胖蛇大作戰（Gaboon Viper）」**：全新 App 圖示、開機畫面與點陣標題，玩法與存檔不受影響。
* ⚔️ **全新挑戰「搶食蛇」**：每個世界第 5 關起，三角頭毒蛇會跟你搶蛋；搶到後要先消化（身上鼓一塊、變慢），消化完蛇頭一紅就回頭追咬你的尾巴。被牠碰到就陣亡，鑽石無敵時則能反撞把牠撞飛（+150 分）。一般與地圖模式登場，計時賽不受影響。
* 📱 **iOS 按鍵自動適配螢幕**：十字鍵與 A/B 依 iPhone 螢幕尺寸縮放，修正小螢幕按鍵重疊。

---

## 📱 iOS 正式完整版 (App Store)

正式完整版已在 Apple App Store 上線發布，**完全免費、無廣告、無內購、不收集個人資料**：

* **App Store 下載**：[https://apps.apple.com/app/id6812165648](https://apps.apple.com/app/id6812165648)
* **系統需求**：iOS 17.0 以上之 iPhone

### 🌟 iOS 完整版獨佔特色：
* 🗺️ **全 10 大主題世界、100 個挑戰關卡**：包含草原、仙人掌荒漠、俄羅斯方塊磚牆、CYBER 晶片電路、息肉腔室、冰川尖刺、鐘錶齒輪、珊瑚礁、熔岩火山與奇異點。
* 🔄 **直向 / 橫向雙模式隨心旋轉**：支援全方向陀螺儀適應，橫向模式具備左右獨立人體工學掌機握持按鈕。
* 🏆 **Apple Game Center 全球排行榜**：即時與全世界高玩競爭歷史最長體長與極限高分。
* 🎮 **實體遊戲手把完整支援**：相容 PS5 DualSense、Xbox 無線手把、Switch Joy-Con / Pro 手把及 MFi 認證控制器。
* 📳 **CoreHaptics 觸覺震動回饋**：吞嚥、消化破裂、爆炸與瀕死警報均有細膩震動。

---

## 🕹️ 核心遊戲機制 (Core Mechanics)

### 1. 延遲消化與負重系統 (Delayed Digestion)
* **食物腫塊（Lump）**：每顆蛋依尺寸不同具備對應體積（2 ~ 10px）。吃下後在蛇頭形成腫塊，每移動一步向後推移一節，在體內持續進行化學消化。
* **胃容量超載撐爆（BURST）**：HUD 上方即時顯示胃容量條（`GUT`）。當未消化腫塊總量超過安全上限（`GUT > GUT_MAX`）時，蛇身立即破裂陣亡！
* **消化負重減速**：胃容量越滿，爬行步伐越沉重緩慢，考驗生死邊緣的走位控制。

### 2. 飢餓倒數與枯竭萎縮 (Starvation & Shrinkage)
* **6 秒飢餓計時**：每次進食重置 6 秒倒數。若倒數歸零，HUD 觸發紅色 `!STARVE!` 警報與急促變速音樂。
* **飢餓萎縮**：挨餓狀態下每 2 秒蛇身縮減 1px；若長度萎縮低於生存極限（`LEN < 12px`），蛇身耗盡力氣死於**枯竭（TOO EMPTY）**。

### 3. 動態 5 物件生態圈 (5-Item Dynamic Density)
* 遊戲場景隨時維持 **5 個物件**（食物蛋保證至少 3 顆，特殊戰術道具上限 2 個），告別枯燥等待，每一次轉向都是決策。

### 4. 搶食蛇 (Rival Snake)
* **出場**：每個世界第 5 子關卡起（1-5、2-5、3-5……），從離你最遠的角落冒出，先閃爍 1.5 秒預警（這段時間碰不死）。只在一般模式與地圖模式出現。
* **搶蛋 → 消化 → 追尾**：牠會搶最近的蛋（被搶走的不算你的過關數）；搶到後消化 3 秒，身上看得到腫塊、速度減半；消化完頭頂跳「!」、蛇頭變紅，追咬你的尾巴 3 秒。
* **致命**：你的頭撞到牠，或牠的頭撞到你，都會陣亡（`RIVAL`）。牠本來就比空腹的你慢，直線逃開就甩得掉——但吃得越撐，你就越跑不動。
* **反擊**：鑽石無敵期間撞到牠，可以把牠撞飛（+150 分），6 秒後重生。

---

## 🎮 三大遊戲模式 (Game Modes)

| 模式名稱 | 玩法規則與特色 | 飢餓機制 | 胃容量負重 |
| :--- | :--- | :---: | :---: |
| 🟢 **START GAME<br>（一般模式）** | 經典闖關推進，循序挑戰前 3 大世界 30 個子關卡，具備進度存檔與關卡續玩功能。 | 正常（6秒倒數） | 正常（過量會撐爆） |
| 🗺️ **MAP MODE<br>（地圖模式）** | 自由選關訓練場！可任意選擇已解鎖的 World 1 ~ 3 及各子關卡切入練習走位。 | 正常（6秒倒數） | 正常（過量會撐爆） |
| ⚡ **TIME ATTACK<br>（5分鐘計時挑戰）** | **全新競技挑戰賽！** 限時 5 分鐘（300 秒）極速衝分！時間倒數最後 30 秒急促閃爍，最後 60 秒 BGM 狂飆加速！時間結束判定 `TIME UP` 結算總分。 | **無飢餓（`HNG ∞`）**<br>不扣長度、不餓死 | **無胃負擔（`GUT ∞`）**<br>不撐爆、無減速懲罰 |

---

## 💎 戰術道具與平衡性參數 (Items & Balance)

特殊道具壽命為 12 秒，在場上隨機生成。v2.0.2 版本針對各道具進行深度數值平衡：

| 道具圖示 | 道具名稱 | 出現機率 | 戰術功能與效果 | 獎勵分數 |
| :---: | :--- | :---: | :--- | :---: |
| 🧪 | **毒藥（POISON）** | **27.5%** | **代價重置鍵**：長度立即縮減 3px，並瞬間清空體內所有未消化腫塊（長度成長折損，但**不會倒扣歷史最高 MAX**），極速化解胃超載危機！ | — |
| ⛸️ | **溜冰鞋（SKATES）** | **27.5%** | **極速衝刺**：移動週期縮短至 ×0.82（可疊加，速度有安全上限），子關卡晉級時自動重置。 | **+50** |
| 💣 | **炸彈（BOMB）** | **27.5%** | **致命爆裂物**：經典加農砲圓球造型，帶有火花引信。直接碰觸立即被炸碎身亡；**僅在鑽石護盾期間可主動踩爆化解**！ | 踩爆 **+100** |
| 💎 | **鑽石（DIAMOND）** | **7.5%**<br>*(機率減半)* | **8 秒無敵無畏金身**：全場彩虹星芒流光！免疫除撞外牆以外的一切死因（免疫撞障礙、撞自己、撞炸彈、胃撐爆）。衝刺踩炸彈賺高分的黃金時刻！ | 吃下 **+200** |
| ⚗️ | **消化酵素（ENZYME）** | **10.0%** | **代謝 3 倍超頻**：5 秒內體內所有腫塊消化速度暴增 300%，極速將胃容量負載轉化為真實長度！ | **+50** |

---

## 📟 HUD 狀態列與指標對照 (Heads-Up Display)

遊戲畫面頂部提供即時精密儀表，各欄位意義如下：

```
[第一行]  TIME 02:45    STAGE 1-3 (5/8)    LEN 28
[第二行]  MAX 32        HNG 4S (或 ∞)      SCORE 1450    INV 5S    GUT [■■■■□□] (或 ∞)
```

* **`TIME`**：生存時間（每秒穩定累計 +2 分）；計時模式下顯示為倒數計時。
* **`STAGE`**：當前關卡編號與吃蛋進度（當前已吃 / 通關門檻）。
* **`LEN`**：當前蛇身實際長度（像素單位），低於 12px 進入枯竭瀕死狀態。
* **`MAX`**：本局歷史最大體長。結算時依照 `MAX × 5` 進行核心倍率計分（吃毒藥縮短不扣此項）。
* **`HNG`**：飢餓倒數（6 秒重置，$\le 2$ 秒紅色閃爍；計時模式顯示為 `HNG ∞`）。
* **`SCORE`**：即時動態總分（公式：道具得分 + MAX×5 + 生存秒數×2）。
* **`INV / FAST`**：目前生效中的特殊增益剩餘秒數（無敵金身 / 溜冰鞋加速）。
* **`GUT`**：消化胃容量長條圖（正常綠 $\rightarrow$ 警告黃 $\rightarrow$ 超載紅光閃爍；計時模式顯示為 `GUT ∞`）。

---

## 🎨 三種復古色彩模式 (Palette Modes)

支援於標題選單按 `SELECT` 鍵（或鍵盤 `C` 鍵），或至 `SETTINGS` 選單中自由切換：

1. **`GBA COLOR`（全新 32 位元彩色復古模式）**：
   - 保持 $240 \times 216$ 原生像素比例，賦予物件飽滿 GBA 色彩美學。
   - 多層漸層翠綠蛇身、體內透光琥珀金腫塊、無敵彩虹流光光環、金屬質感圓球炸彈、青翠草原、荒漠金沙與經典 7 色俄羅斯方塊立體浮雕。
2. **`8-SHADE`（8 階灰綠階調）**：
   - 細膩的經典掌機灰綠陰影階調，層次分明。
3. **`4-DMG`（初代 4 階綠經典液晶）**：
   - 重現初代掌機經典 4 色草綠液晶點陣質感。

---

## 🔊 8-Bit 動態聲學引擎 (Chiptune Audio Engine)

* **動態變速 Chiptune BGM**：背景音樂隨生存時長、溜冰鞋加速及挨餓倒數最後 2 秒，節奏由 1.0x 動態狂飆至 1.65x。
* **開局升音號角（Start Fanfare）**：開局三音爬升銜接第一拍重音。
* **真實白雜訊爆破音效（White Noise Decay）**：合成紅白機加農砲爆破震撼破片聲。
* **音量調節與一鍵靜音**：SETTINGS 選單支援 4 段音量（OFF / 35% / 70% / 100%），機身附帶實體紅色 MUTE LED 指示燈（按 `M` 鍵一鍵靜音）。

---

## ⌨️ 操作控制說明 (Controls)

### 電腦鍵盤 (Desktop Keyboard)

| 操作動作 | 按鍵 | 功能說明 |
| :--- | :--- | :--- |
| **轉向移動** | `↑` `↓` `←` `→`（方向鍵）／ `W` `A` `S` `D` | 控制蛇頭轉向；選單切換項目 |
| **A 鍵（確認 / 暫停）** | `Space` ／ `Enter` ／ `Z` | 確認選項、開始遊戲、手冊翻頁；遊戲中暫停 |
| **B 鍵（返回 / 繼續）** | `P` ／ `X`（官網版另可用 `Esc`） | 暫停中繼續遊戲；選單返回上一頁 |
| **SELECT 鍵** | `C` | 遊戲中開啟 SETTINGS；標題畫面切換 GBA / 8-SHADE / 4-DMG 調色盤 |
| **靜音切換** | `M` | 一鍵開關背景音樂與音效（LED 燈連動） |

畫面上的 START 鍵與 A 鍵作用相同。

### Game Over 結算畫面選單
陣亡時提供直覺選單，不再誤觸重開：
* `▲` / `▼`：切換 `RETRY [當前模式]` 或 `RETURN TO TITLE`
* `A`（Enter / Space）：確認執行
* `B`（Esc）：直接回到主選單

### 行動裝置 (Mobile Touch)
* **螢幕虛擬按鍵**：完整重現十字鍵（D-Pad）、A / B 圓形按鈕、START / SELECT 膠囊鍵與機身靜音 LED。
* **觸控滑動支援**：在遊戲畫面任意處滑動亦可快速轉向。

---

## 💻 本地執行與開發 (Run Locally)

本專案無任何 Node/npm 建置相依，僅需靜態網頁伺服器即可運行：

```bash
# 1. 複製本倉庫
git clone https://github.com/mkjohnny1003/gaboon-viper-web.git
cd gaboon-viper-web

# 2. 啟動任意本地靜態伺服器 (以 Python 3 為例)
python3 -m http.server 8080

# 3. 開啟瀏覽器訪問
open http://localhost:8080
```

---

## 📄 授權條款與聯絡資訊 (License & Contact)

* **授權協議**：本專案採用 [MIT License](LICENSE) 開源授權。
* **官方網站**：[https://getesimmanager.com/gutsy/](https://getesimmanager.com/gutsy/)
* **使用者支援**：[support.html](https://getesimmanager.com/gutsy/support.html)
* **隱私政策**：[privacy.html](https://getesimmanager.com/gutsy/privacy.html)
* **開發者信箱**：mkjohnny@gmail.com


---

<a name="english"></a>

# 🇺🇸 English

<p align="center"><a href="#zh">中文</a> ｜ <strong>English</strong></p>

## 📖 Overview

**Gaboon Viper (Chinese: 胖蛇大作戰; formerly GUTSY / 腸腸久久)** is a snake game that pairs classic handheld dot-matrix visuals with a real digestion-and-weight mechanic.

In classic snake, eating makes you longer instantly. In Gaboon Viper, food becomes a **lump** inside your body that slowly travels toward your tail while it digests. Overeat and your stomach **bursts (BURST)**; go too long without food and you **starve and shrink (STARVE)**.

This repository is the **browser-playable prototype** of Gaboon Viper: a single HTML file with no dependencies, built on HTML5 Canvas and the Web Audio API.

👉 **[Play online (official website)](https://getesimmanager.com/gutsy/play/?lang=en)**

---

## 🚀 What's New in v2.0.3: New Name + Rival Snake

iOS **v2.0.3** has been submitted to App Review (it updates automatically once approved). This web prototype already includes it:
* 🐍 **Renamed "Gaboon Viper" (胖蛇大作戰)**: new app icon, boot screen, and pixel title. Gameplay and saves are unchanged.
* ⚔️ **New challenge — the Rival Snake**: from stage 5 of every world, a triangle-headed viper competes for your eggs. After each steal it must digest (a visible bulge, moving slowly); then its head turns red and it chases your tail. One touch is fatal, but you can ram it away while invincible from a diamond (+150 points). Appears in Standard and Map modes; Time Attack is unchanged.
* 📱 **iOS controls fit every screen**: the D-pad and A/B buttons scale to the iPhone screen size, fixing overlapping controls on smaller screens.

---

## 📱 Full iOS Version (App Store)

The full game is available on the Apple App Store — **free, no ads, no in-app purchases, no personal data collected**:

* **Download**: [https://apps.apple.com/app/id6812165648](https://apps.apple.com/app/id6812165648)
* **Requirements**: iPhone with iOS 17.0 or later

### 🌟 iOS-exclusive features
* 🗺️ **10 themed worlds, 100 stages**: grassland, cactus desert, brick blocks, cyber circuit board, gut chamber, glacial spikes, clockwork gears, coral reef, volcano core, and the singularity.
* 🔄 **Portrait and landscape**: rotate freely; landscape places the D-pad and A/B buttons on either side of the screen for a two-handed grip.
* 🏆 **Apple Game Center global leaderboard**: compete with players worldwide for the longest body and the highest score.
* 🎮 **Game controller support**: PS5 DualSense, Xbox wireless controllers, Switch Joy-Con / Pro controllers, and MFi controllers.
* 📳 **Core Haptics feedback**: subtle vibrations for swallowing, digestion, explosions, and danger alerts.

---

## 🕹️ Core Mechanics

### 1. Delayed digestion and weight
* **Food lumps**: each egg has a size (2–10 px). Swallowing it creates a lump at the head that moves down the body with every step while it digests.
* **Stomach burst (BURST)**: the `GUT` meter in the HUD shows your current stomach load. If undigested lumps exceed the limit (`GUT > GUT_MAX`), the snake bursts and the run ends.
* **Weight slows you down**: the fuller your stomach, the slower you move — every turn becomes a risk.

### 2. Hunger and shrinking
* **6-second hunger timer**: every meal resets a 6-second countdown. When it runs out, the HUD flashes a red `!STARVE!` warning and the music speeds up.
* **Starvation**: while starving, the snake loses 1 px every 2 seconds. Drop below the minimum length (`LEN < 12px`) and you die of starvation (**TOO EMPTY**).

### 3. Five items on the field
* The field always holds **5 items** (at least 3 eggs, up to 2 power-ups), so there is always a decision to make.

### 4. Rival Snake
* **Arrival**: from stage 5 of every world (1-5, 2-5, 3-5, …) it appears in the corner farthest from you and blinks for 1.5 seconds first (it is harmless while blinking). Standard and Map modes only.
* **Steal → digest → chase**: it goes for the nearest egg (stolen eggs don't count toward your stage goal). After a steal it digests for 3 seconds — you can see the bulge, and it moves at half speed. Then a "!" pops up, its head turns red, and it chases your tail for 3 seconds.
* **Fatal**: if your head hits it, or its head hits you, you die (`RIVAL`). It is slower than you on an empty stomach, so running straight gets you away — but the more you have eaten, the slower you are.
* **Fight back**: ram it while invincible from a diamond to knock it out (+150 points); it comes back 6 seconds later.

---

## 🎮 Game Modes

| Mode | Rules | Hunger | Stomach load |
| :--- | :--- | :---: | :---: |
| 🟢 **START GAME<br>(Standard)** | Play through 30 stages across the first 3 worlds in order, with saved progress and Continue. | Normal (6 s timer) | Normal (can burst) |
| 🗺️ **MAP MODE** | Practice any stage of Worlds 1–3 directly. | Normal (6 s timer) | Normal (can burst) |
| ⚡ **TIME ATTACK<br>(5 minutes)** | Score as much as you can in 5 minutes (300 s). The timer flashes in the last 30 seconds and the music speeds up in the last 60. The run ends with `TIME UP`. | **None (`HNG ∞`)**<br>no shrinking, no starving | **None (`GUT ∞`)**<br>no bursting, no slowdown |

---

## 💎 Items & Balance

Power-ups last 12 seconds and spawn at random. Balance as of v2.0.2:

| Icon | Item | Spawn rate | Effect | Bonus |
| :---: | :--- | :---: | :--- | :---: |
| 🧪 | **POISON (laxative)** | **27.5%** | **Emergency reset**: shrinks you by 3 px and instantly clears all undigested lumps. Your recorded **MAX is never reduced**. | — |
| ⛸️ | **SKATES** | **27.5%** | **Speed boost**: movement interval × 0.82 (stacks, with a speed cap). Resets when you clear a stage. | **+50** |
| 💣 | **BOMB** | **27.5%** | **Deadly**: touching it blows you up — **unless you are invincible from a diamond**, which defuses it. | defuse **+100** |
| 💎 | **DIAMOND** | **7.5%** | **8 seconds of invincibility**: immune to everything except walls (obstacles, self-bites, bombs, bursting, the rival snake). | **+200** |
| ⚗️ | **ENZYME** | **10.0%** | **3× digestion** for 5 seconds, turning stomach load into length fast. | **+50** |

---

## 📟 HUD

```
[Row 1]  TIME 02:45    STAGE 1-3 (5/8)    LEN 28
[Row 2]  MAX 32        HNG 4S (or ∞)      SCORE 1450    INV 5S    GUT [■■■■□□] (or ∞)
```

* **`TIME`**: survival time (+2 points per second); counts down in Time Attack.
* **`STAGE`**: current stage and eggs eaten / eggs needed to clear.
* **`LEN`**: current body length in pixels; below 12 px you starve.
* **`MAX`**: longest length reached this run. Scored as `MAX × 5` (shrinking from poison does not reduce it).
* **`HNG`**: hunger countdown (resets to 6 s, flashes red at 2 s or less; shows `HNG ∞` in Time Attack).
* **`SCORE`**: live total (item bonuses + MAX × 5 + seconds survived × 2).
* **`INV / FAST`**: time left on invincibility / skates boost.
* **`GUT`**: stomach load bar (green → yellow → flashing red; shows `GUT ∞` in Time Attack).

---

## 🎨 Palette Modes

Switch with `SELECT` (keyboard `C`) on the title screen, or in the `SETTINGS` menu:

1. **`GBA COLOR`** — full-color pixels at the native 240 × 216 resolution: gradient green snake, glowing amber lumps, rainbow invincibility, metallic bombs, grassland, desert sand, and seven-color bricks.
2. **`8-SHADE`** — an eight-level gray-green palette with fine shading.
3. **`4-DMG`** — the classic four-tone green LCD look of first-generation handhelds.

---

## 🔊 8-bit Chiptune Audio

* **Adaptive BGM**: the music speeds up from 1.0× to 1.65× with survival time, skates, and the last 2 seconds of hunger.
* **Start fanfare**: a three-note rising jingle into the first beat.
* **White-noise explosions**: synthesized blast effects.
* **Volume and mute**: four volume levels in SETTINGS (OFF / 35% / 70% / 100%), plus a red MUTE LED on the shell (`M` to toggle).

---

## ⌨️ Controls

### Keyboard

| Action | Keys | What it does |
| :--- | :--- | :--- |
| **Move** | `↑` `↓` `←` `→` / `W` `A` `S` `D` | Steer the snake; move through menus |
| **A (confirm / pause)** | `Space` / `Enter` / `Z` | Confirm, start, turn manual pages; pause during play |
| **B (back / resume)** | `P` / `X` (the website version also accepts `Esc`) | Resume when paused; go back in menus |
| **SELECT** | `C` | Open SETTINGS during play; switch palettes on the title screen |
| **Mute** | `M` | Toggle music and sound (the LED follows) |

The on-screen START button works the same as A.

### Game Over menu
* `▲` / `▼`: choose `RETRY` or `RETURN TO TITLE`
* `A` (Enter / Space): confirm
* `B`: return to the title screen

### Mobile
* **On-screen buttons**: D-pad, A / B buttons, START / SELECT, and the mute LED.
* **Swipe**: swipe anywhere on the game screen to turn; tap to press A.

---

## 💻 Run Locally

No build step or dependencies — any static web server works:

```bash
# 1. Clone the repository
git clone https://github.com/mkjohnny1003/gaboon-viper-web.git
cd gaboon-viper-web

# 2. Start a static server (Python 3 example)
python3 -m http.server 8080

# 3. Open it in your browser
open http://localhost:8080
```

---

## 📄 License & Contact

* **License**: MIT
* **Website**: [https://getesimmanager.com/gutsy/en/](https://getesimmanager.com/gutsy/en/)
* **Support**: [support.html](https://getesimmanager.com/gutsy/en/support.html)
* **Privacy**: [privacy.html](https://getesimmanager.com/gutsy/en/privacy.html)
* **Email**: mkjohnny@gmail.com
