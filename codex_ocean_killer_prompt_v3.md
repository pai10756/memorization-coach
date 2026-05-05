# 《海洋的殺手》七段背誦攻略小教室 — Codex Prompt v3

> **此檔為主 Prompt（HTML 主體）**
> 用途：給 ChatGPT Codex 從零生成單檔 HTML 學習工具
> 圖片生成：使用 Codex 內建 GPT-image 能力，依本檔末尾 Image Block 規格生成

---

## 一、設計理念（請 Codex 先理解）

### 1.1 真實使用情境

- **使用者**：台灣國小五年級學生 + 家長
- **學校要求**：每天背一段課文（共七段，分七天背完）
- **學習工具不是要推翻學校要求，而是要幫孩子用更科學的方式達成「逐字背完」這個目標**
- **典型使用場景**：放學後，家長花 15-20 分鐘陪孩子用這個工具完成當天那一段

### 1.2 應用的學習科學原理

| 原理 | 在本工具的落實方式 |
|------|-------------------|
| Dual Coding（雙重編碼） | 每段配視覺概念圖 + 文字 |
| Chunking（組塊化） | 每段壓縮成 4-5 字記憶標籤 + 7 段壓縮成總骨架 |
| Retrieval Practice（提取練習） | 用測驗、填空、遮蔽、自背取代反覆閱讀 |
| Spaced Practice（分散練習） | 每天一段、跨天累積複習 |
| Fading Prompts（漸退式提示） | 從畫面 → 骨架 → 關鍵詞 → 句首 → 原文，五階段漸退 |
| Generative Effect（生成效應） | 鼓勵孩子用自己的話講一遍，而非死背 |
| Cognitive Load（認知負荷） | 長段落拆分鏡圖、短段落用單張圖 |

### 1.3 設計優先序（遇到衝突時的決策）

1. **能讓孩子真的背完今天那一段** > 任何美觀或創新功能
2. **促進孩子主動回想** > 被動觀看
3. **家長能順手帶背** > 孩子單獨使用
4. **離線可用、單檔可攜** > 雲端功能

---

## 二、全文七段資料（原文 + 完整資料結構）

### 段落總骨架

```
美麗小島有垃圾
  → 黃色小鴨解開謎團
  → 塑膠微粒進入食物鏈
  → 塑膠成為海洋殺手
  → 塑膠大量使用又難分解
  → 人類必須源頭減塑
  → 海洋發出警訊
```

### 七段短標題（記憶標籤）

| 段號 | 短標題 |
|------|--------|
| 1 | 美麗小島 |
| 2 | 小鴨洋流 |
| 3 | 塑膠微粒 |
| 4 | 海洋殺手 |
| 5 | 塑膠災難 |
| 6 | 源頭減塑 |
| 7 | 海洋警訊 |

### 第一段｜美麗小島

```yaml
id: 1
title: 美麗卻堆滿垃圾的亨德孫島
shortTitle: 美麗小島
originalText: |
  南太平洋的亨德孫島，雪白沙灘環繞，擁有豐富美麗的生態，彷彿世外桃源，是世界少數僅存的珊瑚環礁。然而，這座面積大約只有三十七平方公里的無人小島，竟累積了十八公噸來自各國的塑膠垃圾！這些垃圾究竟是從哪裡來的呢？
plainText: |
  亨德孫島位在南太平洋，原本是一座雪白沙灘環繞、生態豐富、像世外桃源一樣的美麗小島。但是這座無人小島竟然堆積了十八公噸來自各國的塑膠垃圾，讓人想知道垃圾到底從哪裡來。
keywords:
  - 南太平洋
  - 亨德孫島
  - 雪白沙灘
  - 豐富生態
  - 世外桃源
  - 珊瑚環礁
  - 然而
  - 三十七平方公里
  - 無人小島
  - 十八公噸
  - 各國塑膠垃圾
memoryHint: 美麗小島，竟有垃圾。
skeleton: 南太平洋 → 亨德孫島 → 雪白沙灘 → 豐富生態 → 世外桃源 → 珊瑚環礁 → 然而 → 無人小島 → 十八公噸垃圾 → 垃圾從哪裡來？
shortSkeleton: 美麗小島 → 世外桃源 → 無人島 → 十八公噸垃圾 → 垃圾來源之謎
visualType: single  # 單張對比圖
parentQuestions:
  - 亨德孫島在哪裡？
  - 它原本看起來像什麼？
  - 為什麼這段後面讓人驚訝？
quizQuestions:
  - type: choice
    q: 亨德孫島位在哪裡？
    options: [太平洋, 大西洋, 印度洋, 北海]
    answer: 0
  - type: fill
    q: 課文說亨德孫島彷彿什麼？
    answer: 世外桃源
  - type: fill
    q: 這座無人小島累積了多少塑膠垃圾？
    answer: 十八公噸
parentToOriginalCheatsheet:
  - colloquial: 亨德孫島在南太平洋
    original: 南太平洋的亨德孫島
  - colloquial: 沙灘很白，圍繞著小島
    original: 雪白沙灘環繞
  - colloquial: 像天堂一樣
    original: 彷彿世外桃源
  - colloquial: 但是這個小島竟然有垃圾
    original: 然而，這座面積大約只有三十七平方公里的無人小島，竟累積了十八公噸來自各國的塑膠垃圾
```

### 第二段｜小鴨洋流

```yaml
id: 2
title: 黃色小鴨與洋流漂流
shortTitle: 小鴨洋流
originalText: |
  西元一九九二年「黃色小鴨」的事件，解答了這個謎團。那一年，一艘貨輪遇上風暴，導致船上將近三萬隻黃色塑膠鴨在北太平洋落海。這些小鴨隨波逐流，有的北上，陸續漂流到北極海、美國東岸，甚至到達英國。有的南下，漂向夏威夷、印尼，還一路到澳洲和南美洲。原來海洋中有一條條如高速公路的洋流，不斷循環流動，這也讓這些塑膠旅客順著洋流漂游到各地。在洋流的環流系統中，不只是海面漂流著塑膠垃圾，連深海也被塑膠大軍占領。
plainText: |
  一九九二年的「黃色小鴨」事件，解開了塑膠垃圾從哪裡來的謎團。那一年，一艘貨輪遇到風暴，船上將近三萬隻黃色塑膠鴨掉進北太平洋。這些小鴨跟著海水漂流，有些往北漂到北極海、美國東岸，甚至英國；有些往南漂到夏威夷、印尼、澳洲和南美洲。原來海洋裡有像高速公路一樣的洋流，會不斷循環流動，把塑膠垃圾帶到各地。不只是海面有塑膠垃圾，連深海也被塑膠垃圾占領。
keywords:
  - 西元一九九二年
  - 黃色小鴨
  - 解答謎團
  - 貨輪
  - 風暴
  - 將近三萬隻
  - 北太平洋
  - 落海
  - 隨波逐流
  - 北上
  - 北極海
  - 美國東岸
  - 英國
  - 南下
  - 夏威夷
  - 印尼
  - 澳洲
  - 南美洲
  - 高速公路
  - 洋流
  - 循環流動
  - 塑膠旅客
  - 深海
  - 塑膠大軍占領
memoryHint: 小鴨落海，洋流帶到世界各地。
skeleton: 西元一九九二年 → 黃色小鴨事件 → 解答謎團 → 貨輪遇風暴 → 將近三萬隻黃色塑膠鴨 → 北太平洋落海 → 隨波逐流 → 有的北上 → 北極海、美國東岸、英國 → 有的南下 → 夏威夷、印尼、澳洲、南美洲 → 洋流像高速公路 → 不斷循環流動 → 塑膠旅客漂游各地 → 海面有塑膠垃圾 → 深海也被塑膠大軍占領
shortSkeleton: 小鴨落海 → 北上南下 → 洋流高速公路 → 塑膠漂各地 → 深海也占領
visualType: storyboard6  # 六格分鏡
parentQuestions:
  - 黃色小鴨事件解答了什麼謎團？
  - 為什麼將近三萬隻黃色塑膠鴨會落海？
  - 小鴨北上漂到哪些地方？
  - 小鴨南下漂到哪些地方？
  - 課文把洋流比喻成什麼？
  - 塑膠垃圾只在海面上嗎？
quizQuestions:
  - type: fill
    q: 黃色小鴨事件發生在哪一年？
    answer: 一九九二年
  - type: choice
    q: 將近多少隻黃色塑膠鴨在北太平洋落海？
    options: [三千隻, 三萬隻, 三十萬隻, 三百萬隻]
    answer: 1
  - type: fill
    q: 課文把洋流比喻成什麼？
    answer: 高速公路
  - type: choice
    q: 除了海面，哪裡也被塑膠大軍占領？
    options: [天空, 陸地, 深海, 河川]
    answer: 2
parentToOriginalCheatsheet:
  - colloquial: 1992 年發生黃色小鴨事件
    original: 西元一九九二年「黃色小鴨」的事件
  - colloquial: 解開了垃圾從哪來的謎
    original: 解答了這個謎團
  - colloquial: 貨輪遇到風暴
    original: 一艘貨輪遇上風暴
  - colloquial: 三萬隻塑膠鴨掉進海裡
    original: 將近三萬隻黃色塑膠鴨在北太平洋落海
  - colloquial: 小鴨跟著海水漂
    original: 這些小鴨隨波逐流
  - colloquial: 一些往北漂到北極、美國、英國
    original: 有的北上，陸續漂流到北極海、美國東岸，甚至到達英國
  - colloquial: 一些往南漂到夏威夷、印尼、澳洲、南美
    original: 有的南下，漂向夏威夷、印尼，還一路到澳洲和南美洲
  - colloquial: 洋流像高速公路
    original: 海洋中有一條條如高速公路的洋流
  - colloquial: 連深海都有塑膠垃圾
    original: 連深海也被塑膠大軍占領
```

### 第三段｜塑膠微粒

```yaml
id: 3
title: 塑膠微粒與食物鏈
shortTitle: 塑膠微粒
originalText: |
  塑膠在海中受到日照與風浪拍打，分解成極小的塊狀、細絲或球體狀的塑膠微粒。科學家發現，這些幾乎看不見的塑膠，不僅會釋放有毒物質，影響海洋生物的生長，還會吸附海洋汙染物與細菌，成為更毒的懸浮物。由於微粒體積小，常被浮游生物吸收食入，連生存在地球最深的馬里亞納海溝中的浮游生物，體內也藏著塑膠微粒，科學家還將牠們命名為「塑膠鉤蝦」。而在「大魚吃小魚，小魚吃蝦米」的食物鏈下，海洋正形成一種駭人的生態系統——海洋塑膠生物圈。你可曾想過，大口吃著美味海鮮時，到底吃進了什麼？
plainText: |
  塑膠在海中被太陽曬、被風浪打，會碎成極小的塑膠微粒。這些微粒幾乎看不見，卻可能釋放毒物，也會吸附汙染物和細菌，變得更毒。因為微粒太小，浮游生物會吃下去，連最深的馬里亞納海溝生物體內也發現塑膠微粒。塑膠透過食物鏈傳遞，最後人類吃海鮮時也可能吃進去。
keywords:
  - 日照
  - 風浪拍打
  - 塑膠微粒
  - 極小
  - 塊狀
  - 細絲
  - 球體狀
  - 有毒物質
  - 海洋汙染物
  - 細菌
  - 懸浮物
  - 浮游生物
  - 馬里亞納海溝
  - 塑膠鉤蝦
  - 大魚吃小魚
  - 小魚吃蝦米
  - 食物鏈
  - 海洋塑膠生物圈
  - 海鮮
memoryHint: 塑膠微粒，進入食物鏈。
skeleton: 塑膠受日照與風浪拍打 → 分解成塑膠微粒 → 極小的塊狀、細絲或球體狀 → 釋放有毒物質 → 影響海洋生物生長 → 吸附汙染物與細菌 → 成為更毒的懸浮物 → 浮游生物吃下去 → 馬里亞納海溝也有 → 塑膠鉤蝦 → 大魚吃小魚，小魚吃蝦米 → 海洋塑膠生物圈 → 人類吃海鮮也可能吃進去
shortSkeleton: 塑膠變微粒 → 微粒更毒 → 小生物吃下 → 食物鏈傳遞 → 人類可能吃進去
visualType: crossSection  # 海洋垂直剖面圖
parentQuestions:
  - 塑膠為什麼會變成微粒？
  - 塑膠微粒可怕在哪裡？
  - 為什麼人類吃海鮮也可能受影響？
quizQuestions:
  - type: fill
    q: 塑膠在海中受到什麼影響會分解？
    answer: 日照與風浪拍打
  - type: fill
    q: 哪個深海地點也發現塑膠微粒？
    answer: 馬里亞納海溝
  - type: fill
    q: 科學家把馬里亞納海溝裡含塑膠微粒的浮游生物命名為什麼？
    answer: 塑膠鉤蝦
parentToOriginalCheatsheet:
  - colloquial: 塑膠在海裡被太陽曬風浪打
    original: 塑膠在海中受到日照與風浪拍打
  - colloquial: 變成很小的塑膠微粒
    original: 分解成極小的塊狀、細絲或球體狀的塑膠微粒
  - colloquial: 會放出毒物
    original: 釋放有毒物質
  - colloquial: 還會吸附汙染物和細菌變得更毒
    original: 吸附海洋汙染物與細菌，成為更毒的懸浮物
  - colloquial: 連最深的海溝都有
    original: 連生存在地球最深的馬里亞納海溝中的浮游生物
  - colloquial: 大魚吃小魚最後傳到人類
    original: 大魚吃小魚，小魚吃蝦米
```

### 第四段｜海洋殺手

```yaml
id: 4
title: 無孔不入的海洋殺手
shortTitle: 海洋殺手
originalText: |
  無孔不入的塑膠就像海洋的殺手，除了帶來環境改變的威脅，更對海洋生態造成巨大傷害，從海岸、海面到深海都無一倖免。海洋經常上演著種種觸目驚心的畫面：吞食塑膠的海鳥、被魚網困住的海龜、遭垃圾覆蓋的珊瑚礁、體內充滿塑膠垃圾的鯨魚……。根據二〇一六年聯合國報告，全球受海洋塑膠垃圾影響，而且面臨生存威脅的生物，已高達八百種。
plainText: |
  塑膠到處都有，就像海洋的殺手，不只改變環境，也嚴重傷害海洋生態。從海岸、海面到深海都受影響。海鳥會吞食塑膠，海龜會被魚網困住，珊瑚礁被垃圾覆蓋，鯨魚體內也可能充滿塑膠垃圾。根據聯合國報告，全球受到海洋塑膠垃圾影響、面臨生存威脅的生物已經高達八百種。
keywords:
  - 無孔不入
  - 海洋殺手
  - 環境改變
  - 海洋生態
  - 海岸
  - 海面
  - 深海
  - 無一倖免
  - 觸目驚心
  - 海鳥
  - 海龜
  - 魚網
  - 珊瑚礁
  - 鯨魚
  - 二〇一六年
  - 聯合國報告
  - 八百種
memoryHint: 塑膠像殺手，海洋生物都受害。
skeleton: 無孔不入的塑膠 → 像海洋的殺手 → 帶來環境改變的威脅 → 傷害海洋生態 → 海岸、海面、深海無一倖免 → 海鳥吞食塑膠 → 海龜被魚網困住 → 珊瑚礁遭垃圾覆蓋 → 鯨魚體內充滿塑膠垃圾 → 二〇一六年聯合國報告 → 八百種生物受威脅
shortSkeleton: 海洋殺手 → 海岸海面深海 → 海鳥海龜珊瑚鯨魚 → 八百種生物受威脅
visualType: collage4  # 四格拼貼圖
parentQuestions:
  - 課文說塑膠像什麼？
  - 哪些海洋生物受到塑膠垃圾影響？
  - 受威脅的生物已經高達多少種？
quizQuestions:
  - type: fill
    q: 課文用什麼比喻塑膠？
    answer: 海洋殺手
  - type: choice
    q: 從海岸、海面到哪裡都無一倖免？
    options: [陸地, 河川, 深海, 天空]
    answer: 2
  - type: fill
    q: 聯合國報告說受威脅的生物高達多少種？
    answer: 八百種
parentToOriginalCheatsheet:
  - colloquial: 塑膠到處都有像殺手
    original: 無孔不入的塑膠就像海洋的殺手
  - colloquial: 從海岸海面到深海都受害
    original: 從海岸、海面到深海都無一倖免
  - colloquial: 海鳥吃塑膠、海龜被網住、珊瑚被覆蓋、鯨魚體內有塑膠
    original: 吞食塑膠的海鳥、被魚網困住的海龜、遭垃圾覆蓋的珊瑚礁、體內充滿塑膠垃圾的鯨魚
  - colloquial: 2016 年聯合國說 800 種生物受影響
    original: 根據二〇一六年聯合國報告，全球受海洋塑膠垃圾影響，而且面臨生存威脅的生物，已高達八百種
```

### 第五段｜塑膠災難

```yaml
id: 5
title: 塑膠災難：便宜耐用，但難以分解
shortTitle: 塑膠災難
originalText: |
  塑膠便宜耐用、取得便利，因此被人們大量使用，但因難以在環境中自然分解，已成為僅次於氣候變遷的全球災難。學者估計，目前每年約有一千一百萬公噸的塑膠垃圾流進海洋，若不採取行動，到二〇四〇年甚至會增加到兩千九百萬公噸。這些垃圾主要來自人口密集的河川、海岸以及船隻漁具的廢棄物，且大多是一次性的塑膠製品。
plainText: |
  塑膠因為便宜、耐用、方便取得，所以被大量使用。但它很難自然分解，因此成為全球災難。現在每年約有一千一百萬公噸塑膠垃圾流入海洋，如果不採取行動，到二〇四〇年可能增加到兩千九百萬公噸。這些垃圾多來自河川、海岸、船隻漁具和一次性塑膠製品。
keywords:
  - 便宜耐用
  - 取得便利
  - 大量使用
  - 難以自然分解
  - 氣候變遷
  - 全球災難
  - 一千一百萬公噸
  - 二〇四〇年
  - 兩千九百萬公噸
  - 河川
  - 海岸
  - 船隻漁具
  - 廢棄物
  - 一次性塑膠製品
memoryHint: 便宜耐用，卻難以分解。
skeleton: 塑膠便宜耐用 → 取得便利 → 被大量使用 → 難以自然分解 → 成為僅次於氣候變遷的全球災難 → 每年約一千一百萬公噸流進海洋 → 若不採取行動 → 二〇四〇年增加到兩千九百萬公噸 → 來源是人口密集的河川、海岸、船隻漁具 → 大多是一次性塑膠製品
shortSkeleton: 便宜耐用 → 大量使用 → 難分解 → 垃圾暴增 → 一次性塑膠
visualType: dataChart  # 資訊圖表式
parentQuestions:
  - 為什麼人類大量使用塑膠？
  - 塑膠最大的問題是什麼？
  - 如果不採取行動，二〇四〇年可能增加到多少？
quizQuestions:
  - type: fill
    q: 塑膠有哪些特點讓人們大量使用？
    answer: 便宜耐用、取得便利
  - type: fill
    q: 目前每年約有多少塑膠垃圾流進海洋？
    answer: 一千一百萬公噸
  - type: fill
    q: 二〇四〇年可能增加到多少？
    answer: 兩千九百萬公噸
parentToOriginalCheatsheet:
  - colloquial: 塑膠便宜耐用又方便所以大家用很多
    original: 塑膠便宜耐用、取得便利，因此被人們大量使用
  - colloquial: 但很難分解
    original: 但因難以在環境中自然分解
  - colloquial: 變成僅次於氣候變遷的全球災難
    original: 已成為僅次於氣候變遷的全球災難
  - colloquial: 每年 1100 萬公噸流進海洋
    original: 目前每年約有一千一百萬公噸的塑膠垃圾流進海洋
  - colloquial: 不行動 2040 會變 2900 萬
    original: 若不採取行動，到二〇四〇年甚至會增加到兩千九百萬公噸
  - colloquial: 主要來自河川海岸船和一次性塑膠
    original: 主要來自人口密集的河川、海岸以及船隻漁具的廢棄物，且大多是一次性的塑膠製品
```

### 第六段｜源頭減塑

```yaml
id: 6
title: 源頭減塑：政府、民間、個人一起行動
shortTitle: 源頭減塑
originalText: |
  人類與生態環境相互影響，正視塑膠危害，「源頭減塑」才是根本解決之道。聯合國在二〇一八年提出「塑戰塑決」以維護海洋生態與環境，越來越多國家也發現問題的嚴重性，紛紛制定了「減塑、限塑」相關辦法。除此以外，民間團體自發性舉辦淨灘活動，喚起更多人的關注。人們更配合減塑、回收再利用和自備環保用品等，以行動實踐地球的永續發展。
plainText: |
  人類和生態環境互相影響，所以要正視塑膠的危害。真正根本的解決方式是從源頭減少塑膠使用。聯合國提出塑戰塑決，許多國家制定減塑和限塑辦法，民間也舉辦淨灘活動。每個人也可以減塑、回收再利用、自備環保用品，幫助地球永續發展。
keywords:
  - 人類與生態環境
  - 相互影響
  - 正視塑膠危害
  - 源頭減塑
  - 根本解決之道
  - 聯合國
  - 二〇一八年
  - 塑戰塑決
  - 維護海洋生態與環境
  - 減塑
  - 限塑
  - 民間團體
  - 淨灘活動
  - 喚起關注
  - 回收再利用
  - 自備環保用品
  - 永續發展
memoryHint: 源頭減塑，人人行動。
skeleton: 人類與生態環境相互影響 → 正視塑膠危害 → 源頭減塑是根本解決之道 → 聯合國二〇一八年提出塑戰塑決 → 維護海洋生態與環境 → 各國制定減塑、限塑辦法 → 民間團體舉辦淨灘活動 → 喚起更多人關注 → 減塑、回收再利用 → 自備環保用品 → 實踐永續發展
shortSkeleton: 正視危害 → 源頭減塑 → 政府限塑 → 民間淨灘 → 個人自備環保用品
visualType: collage4  # 四格行動拼貼
parentQuestions:
  - 根本解決方法是什麼？
  - 政府和聯合國做了什麼？
  - 一般人可以怎麼做？
quizQuestions:
  - type: fill
    q: 課文說什麼才是根本解決之道？
    answer: 源頭減塑
  - type: fill
    q: 聯合國在二〇一八年提出什麼？
    answer: 塑戰塑決
  - type: fill
    q: 個人可以用哪些行動減塑？
    answer: 回收再利用、自備環保用品
parentToOriginalCheatsheet:
  - colloquial: 人類和環境互相影響
    original: 人類與生態環境相互影響
  - colloquial: 要正視塑膠危害
    original: 正視塑膠危害
  - colloquial: 源頭減塑才是根本辦法
    original: 「源頭減塑」才是根本解決之道
  - colloquial: 聯合國 2018 年提出塑戰塑決
    original: 聯合國在二〇一八年提出「塑戰塑決」
  - colloquial: 越來越多國家制定減塑限塑
    original: 越來越多國家也發現問題的嚴重性，紛紛制定了「減塑、限塑」相關辦法
  - colloquial: 民間團體辦淨灘活動
    original: 民間團體自發性舉辦淨灘活動，喚起更多人的關注
  - colloquial: 人們減塑回收自備環保用品
    original: 人們更配合減塑、回收再利用和自備環保用品等，以行動實踐地球的永續發展
```

### 第七段｜海洋警訊

```yaml
id: 7
title: 海洋警訊：未來可能撿不到貝殼
shortTitle: 海洋警訊
originalText: |
  大海面對日益嚴重的塑膠汙染，已不斷發出警訊。我們需要每個人付出行動，否則未來在海邊隨手撿起的可能不是貝殼，而是寶特瓶的瓶蓋……。
plainText: |
  海洋塑膠污染越來越嚴重，大海正在提醒我們要趕快行動。如果人類不改變，未來在海邊撿到的可能不是美麗的貝殼，而是寶特瓶瓶蓋。
keywords:
  - 大海
  - 日益嚴重
  - 塑膠汙染
  - 發出警訊
  - 每個人
  - 付出行動
  - 海邊
  - 隨手撿起
  - 貝殼
  - 寶特瓶瓶蓋
memoryHint: 海洋警訊，別變瓶蓋。
skeleton: 大海面對日益嚴重的塑膠汙染 → 不斷發出警訊 → 需要每個人付出行動 → 否則未來在海邊 → 隨手撿起的可能不是貝殼 → 而是寶特瓶的瓶蓋
shortSkeleton: 海洋警訊 → 人人行動 → 不是貝殼 → 是瓶蓋
visualType: single  # 單張收尾圖
parentQuestions:
  - 大海發出了什麼警訊？
  - 課文說需要誰付出行動？
  - 最後的「不是貝殼，而是瓶蓋」是在提醒什麼？
quizQuestions:
  - type: fill
    q: 大海面對什麼問題？
    answer: 日益嚴重的塑膠汙染
  - type: fill
    q: 未來海邊可能撿到什麼（不是貝殼）？
    answer: 寶特瓶的瓶蓋
parentToOriginalCheatsheet:
  - colloquial: 海洋污染越來越嚴重大海在警告
    original: 大海面對日益嚴重的塑膠汙染，已不斷發出警訊
  - colloquial: 需要每個人行動
    original: 我們需要每個人付出行動
  - colloquial: 不然以後撿到的不是貝殼是瓶蓋
    original: 否則未來在海邊隨手撿起的可能不是貝殼，而是寶特瓶的瓶蓋
```

---

## 三、互動模式設計（共八個模式）

### 3.1 首頁

#### 標題與副標
- 主標：《海洋的殺手》七段背誦攻略小教室
- 副標：用七段故事線、關鍵詞骨架和漸進測驗，把課文一步一步背起來

#### 今日進度看板
- 顯示「今天該背第 X 段」（從 localStorage 讀取，若無則預設第 1 段）
- 顯示「已完成段落」標記（綠色 checkmark）
- 「我要背今天那一段」CTA 按鈕（一鍵跳到原文還原模式 + 預選今日段落）

#### 三個快速入口
1. **看七段故事總覽**（→ 故事模式）
2. **背今天那一段**（→ 原文還原模式）
3. **15 分鐘闖關**（→ 闖關模式）

#### 給家長的話（摺疊區塊）

```
📖 設計理念
這份工具不要求孩子囫圇吞棗死背七段，而是用學習科學的方式幫他真的記得。
但我們也尊重學校要求——「原文還原模式」就是專門幫孩子完成「逐字背一段」這個功課。

📅 七天背誦排程建議
- 第 1 天：背第 1 段（亨德孫島）
- 第 2 天：背第 2 段，順便快速複習第 1 段
- 第 3 天：背第 3 段，順便快速複習第 1-2 段
- ...以此類推
- 第 7 天：背第 7 段，順便完整跑一次七段

🆘 孩子卡住時
請按照「家長陪背模式」裡的提示順序：畫面 → 短骨架 → 關鍵詞 → 句首 → 才看原文。
不要直接給答案，那會讓他失去主動記憶的機會。

⏰ 每天大約 15-20 分鐘
建議流程：故事模式 5 分鐘理解 → 原文還原模式 10 分鐘背誦 → 睡前 1 分鐘快速回想。
```

### 3.2 故事模式 (Story Mode)

- 七張段落卡片橫向排列（手機改直向），用箭頭連起來
- 每張卡片顯示：段號、shortTitle、視覺概念圖、4-5 字 shortSkeleton 摘要
- 點擊任一卡片展開詳細抽屜：originalText / plainText / keywords / memoryHint / skeleton
- 七段視覺化呈現「問題 → 真相 → 危害 → 規模 → 解決 → 行動」議論文骨架

### 3.3 逐段學習 (Learn Mode)

- 一次只顯示一段，垂直版面：
  1. 段落概念圖（依 visualType 不同呈現方式）
  2. 段落標題 + shortTitle
  3. originalText（可點關鍵字看解釋彈窗）
  4. plainText 白話對照
  5. keywords（chip 樣式，hover 顯示在原文哪個位置）
  6. memoryHint
  7. skeleton（完整骨架）
- 上一段 / 下一段切換按鈕
- 進度條顯示 X / 7
- 「我已讀懂」按鈕（記入 localStorage）

### 3.4 關鍵詞骨架 (Skeleton Mode)

- 每段顯示 shortSkeleton（5 個節點 → 連線）
- 三段難度切換：
  - **完整骨架**：所有節點顯示
  - **只看第一個詞**：每節點只顯示第一個字
  - **全部遮住**：節點都是 `___`
- 點擊任一節點翻開答案
- 提供「下一段骨架」「上一段骨架」切換

### 3.5 遮蔽測試 (Test Mode)

依段落長度自動調整難度策略：

#### 短段落（< 100 字，如第 7 段）
- Level 1：遮蔽關鍵動詞和數字
- Level 2：每句只保留首字
- Level 3：只顯示 memoryHint，原文全部遮住

#### 中長段落（100-200 字，如第 1, 4, 5, 6 段）
- Level 1：遮蔽關鍵詞（chip 化）
- Level 2：每句只保留前 2-4 字
- Level 3：完全遮蔽，只顯示 memoryHint

#### 長段落（> 200 字，如第 2, 3 段）
- Level 1：保留主語+遮蔽論述
- Level 2：每句首 3-5 字提示
- Level 3：只顯示 shortSkeleton

每段測試完顯示：
- 揭曉答案按鈕
- 答對 / 還要練 兩個自評按鈕
- 該段累積答對率（從 localStorage 讀寫）

### 3.6 打亂順序問答 (Quiz Mode)

至少 14 題，涵蓋七段（每段至少 2 題）。

題型分布：
- 選擇題：5 題
- 填空題：6 題
- 看提示猜段落：2 題
- 段落排序題：1 題（給打亂的七個 shortTitle，拖拉排回正確順序）

答錯時的回饋：
- 不要只說「答錯了」
- 顯示正確答案 + 該答案來自哪一段
- 提供「跳到那一段複習」按鈕
- 鼓勵語：「沒關係，記住這題的答案就好」

題目範例（請以每段的 quizQuestions 為基礎）：

```
1. [選擇] 亨德孫島位在哪裡？選項：太平洋 / 大西洋 / 印度洋 / 北海
2. [填空] 第一段說亨德孫島彷彿___（答：世外桃源）
3. [填空] 黃色小鴨事件發生在哪一年？（答：一九九二年）
4. [選擇] 將近多少隻黃色塑膠鴨在北太平洋落海？三千 / 三萬 / 三十萬 / 三百萬
5. [填空] 課文把洋流比喻成什麼？（答：高速公路）
6. [填空] 第三段中，馬里亞納海溝的塑膠浮游生物被命名為什麼？（答：塑膠鉤蝦）
7. [填空] 「大魚吃小魚，小魚吃蝦米」是在說什麼概念？（答：食物鏈）
8. [填空] 課文用什麼比喻塑膠？（答：海洋殺手）
9. [選擇] 從海岸、海面到哪裡都無一倖免？陸地 / 河川 / 深海 / 天空
10. [填空] 聯合國報告說受威脅的生物高達多少種？（答：八百種）
11. [選擇] 為什麼塑膠被大量使用？因為昂貴 / 因為便宜耐用 / 因為稀有 / 因為可分解
12. [填空] 二〇四〇年塑膠垃圾可能增加到多少？（答：兩千九百萬公噸）
13. [填空] 課文說什麼才是根本解決之道？（答：源頭減塑）
14. [排序] 把七段的 shortTitle 排回正確順序
```

### 3.7 原文還原模式 (Restore Mode) — **核心輸出端**

> **這個模式是工具的核心**——孩子的學校功課就是「逐字背一段」，這個模式專門幫他達成。

使用流程：

1. **段落選擇器**：讓孩子或家長選定要背的段落（預設今天那一段）
2. **四階段漸進還原**（依序通關）：

#### 階段 1：看骨架說大意（理解輸出層）
- 顯示該段的 shortSkeleton（5-6 個節點）
- 顯示該段的概念圖
- 引導語：「請你看著這個骨架，用自己的話講一遍這段在說什麼。」
- 只有「我說完了」按鈕（不需判斷對錯，這階段練的是理解）
- 過關後進入階段 2

#### 階段 2：看句首提示接原文（語法重建層）
- 把 originalText 按「，」「。」斷句
- 每句只顯示前 3-5 字，後半用 `___` 遮住
- 例：
  ```
  南太平洋的亨德___
  雪白沙灘環___
  擁有豐富___
  ```
- 孩子看著提示在腦中接出原文
- 提供「揭曉」按鈕對照
- 「我都接出來了」按鈕進入階段 3

#### 階段 3：關鍵詞填空（記憶喚回層）
- 顯示完整 originalText，但每個 keyword 變成 `___`
- 例（以第 1 段為例）：
  ```
  ___的亨德孫島，___環繞，擁有___美麗的生態，
  彷彿___，是世界少數僅存的___。
  ___，這座面積大約只有___的___，
  竟累積了___來自各國的塑膠垃圾！
  ```
- 提供 keyword 候選詞區塊（含部分混淆選項），讓孩子拖拉或點選填回
- 答對顯示綠色，答錯顯示正確答案
- 全部填完進入階段 4

#### 階段 4：完整遮蔽背誦（流暢輸出層）
- 整段全部遮住，只顯示段落標題與一張概念圖
- 提供兩種模式選擇：
  - **打字模式**：逐字輸入，比對 originalText，錯字標紅
  - **口說模式**：3 分鐘倒數計時，背完後孩子自評（流暢/卡住但完成/還要練）
- 完成後存入 localStorage，標記該段為「今日已完成背誦」

#### 通關回饋
- 顯示鼓勵語：「你已經完成第 X 段的背誦！」
- 顯示明天提示：「明天起床先快速回想一次，鞏固記憶。」
- 顯示複習排程：「3 天後（X 月 X 日）會提醒你再背一次。」

### 3.8 家長陪背模式 (Parent Mode)

每段提供：

#### A. 家長提問清單
（直接從 parentQuestions 取）

#### B. 漸退式提示順序

```
階段 1（最粗）：給畫面提示
  - 給孩子看該段的概念圖
  - 問：「看這張圖，這一段在講什麼？」

階段 2：給短骨架
  - 顯示該段 shortSkeleton（5 個節點）
  - 問：「跟著這條線，你能說出大意嗎？」

階段 3：給關鍵詞
  - 顯示該段所有 keywords（chip 化）
  - 問：「用這些詞，能拼回課文意思嗎？」

階段 4：給句首提示
  - 顯示每句前 3-5 字
  - 問：「能接出後面的字嗎？」

階段 5（最後手段）：才看原文
  - 一起讀原文 1 次
  - 然後立刻遮起來，讓孩子重背
```

#### C. 白話 → 原文 對照卡（**核心新增功能**）

從 parentToOriginalCheatsheet 取資料，呈現雙欄對照：

```
孩子用白話說的版本                    課本原文版本
═══════════════════════════════════════════════════════════
1992 年發生黃色小鴨事件         →   西元一九九二年「黃色小鴨」的事件
解開了垃圾從哪來的謎             →   解答了這個謎團
貨輪遇到風暴                     →   一艘貨輪遇上風暴
3 萬隻塑膠鴨掉進海               →   將近三萬隻黃色塑膠鴨在北太平洋落海
小鴨跟著海水漂                   →   這些小鴨隨波逐流
洋流像高速公路                   →   海洋中有一條條如高速公路的洋流
連深海都有塑膠垃圾               →   連深海也被塑膠大軍占領
```

家長使用方式（在 UI 顯示一段說明）：

```
💡 怎麼用對照卡
1. 讓孩子先用白話說一遍
2. 你拿著對照卡，每聽到一句白話就指出對應的原文
3. 重點不是糾正孩子，而是讓他建立「白話 ↔ 原文」的對應感
4. 多練幾段後，孩子會自己學會這種「換句說話」的能力
```

#### D. 鼓勵語庫（隨機顯示）

```
- 你已經抓到這段的方向了。
- 先不用一字不差，先把骨架說出來。
- 卡住很正常，我們看關鍵詞再接回去。
- 你不是背不起來，只是這一句還沒黏牢。
- 先背故事線，再補課本原文。
- 這一段你已經比剛剛順很多了。
- 很好，現在我們把白話換回課本句子。
- 不急，先從第一個畫面開始。
- 你已經完成一大半了。
- 再試一次，這次只看提示卡。
```

### 3.9 15 分鐘闖關 (Challenge Mode)

七個關卡，總計 15 分鐘：

| 關卡 | 時長 | 內容 |
|------|------|------|
| 關卡 1 | 2 分 | 看七段故事總覽 |
| 關卡 2 | 2 分 | 背第 1 段骨架（美麗小島） |
| 關卡 3 | 3 分 | 背第 2 段骨架（小鴨洋流，最長） |
| 關卡 4 | 3 分 | 背第 3 段骨架（塑膠微粒，最難） |
| 關卡 5 | 2 分 | 背第 4-5 段骨架（海洋殺手 + 塑膠災難） |
| 關卡 6 | 2 分 | 背第 6 段骨架（源頭減塑） |
| 關卡 7 | 1 分 | 背第 7 段結尾警訊 |

每關獨立倒數計時，過關後解鎖下一關。
全部完成後顯示恭喜畫面 + 「明天再來複習」提醒。

---

## 四、視覺類型設計（按 visualType 分類）

不要全部用單張圖，依 visualType 採用不同呈現方式：

### 4.1 `single` — 單張對比圖（第 1, 7 段）
- 整版單張概念圖
- 適合：場景對比、收尾意象
- 圖片佔比：60% 寬度，置中

### 4.2 `storyboard6` — 六格分鏡（第 2 段）
- 2 行 × 3 列分鏡圖（手機改 6 行 × 1 列）
- 每格對應 shortSkeleton 一個節點
- 適合：複雜事件序列
- **第 2 段必用此類型**，因為它包含事件+多路線+結論

### 4.3 `crossSection` — 垂直剖面圖（第 3 段）
- 從上到下三層垂直剖面
- 上：海面塑膠瓶 / 中：破碎塑膠塊 / 下：深海塑膠鉤蝦
- 適合：呈現空間層次

### 4.4 `collage4` — 四格拼貼（第 4, 6 段）
- 2x2 四格圖
- 每格一個元素（第 4 段：海鳥/海龜/珊瑚/鯨魚；第 6 段：聯合國/政府/民間/個人）
- 適合：列舉並列項目

### 4.5 `dataChart` — 資訊圖表式（第 5 段）
- 含視覺化數據元素（柱狀對比 1100 → 2900 萬）
- 周邊有汙染源圖示（河川/海岸/船隻）
- 適合：呈現數量與規模

---

## 五、圖片生成（Image Block — 給 GPT-image 用）

### 統一風格 [STYLE_BLOCK]

```
Hand-painted watercolor + ink illustration on warm beige paper.
Soft, slightly textured background. Limited color palette.
Children-safe, age 10-12 educational illustration style.

Color palette:
- Ocean blue (#0A4D68, #1B6B8C)
- Sky cyan (#5BCEFA)
- Sand beige (#F5EFE0)
- Coral red (#E63946) for warnings/contrast
- Leaf green (#7BAA66)
- Charcoal ink lines (#2D3142)

NEGATIVE PROMPTS (must avoid):
❌ No realistic photo, no 3D render, no anime, no glossy CG
❌ No text, no Chinese characters, no English words, no captions
❌ No watermarks, no logos, no signatures
❌ No graphic gore, no bloody scenes, no dead animal close-ups
❌ No human faces in detail (vague silhouettes only if needed)
```

### 七張圖的個別 prompt

#### Image 1（第 1 段 / single）

```
[STYLE_BLOCK]
Aerial view of a small tropical Pacific island with white sandy beach,
turquoise ocean, coral reef ring, lush vegetation. The left half of the
beach is pristine and beautiful (paradise feeling). The right half of
the beach is covered with scattered plastic debris (bottles, bags,
containers) in muted colors. Strong visual contrast between heaven and
pollution. Watercolor texture, soft outlines.
Aspect ratio: 16:9
```

#### Image 2（第 2 段 / storyboard6）

```
[STYLE_BLOCK]
Six-panel storyboard layout (2 rows × 3 columns), each panel separated
by thin ink lines:

Panel 1: A cargo ship at sea on a calm day, year 1992 atmosphere
        (vintage feel, no text)
Panel 2: The same cargo ship caught in a violent storm, large waves,
        yellow rubber ducks tumbling out of containers into the dark
        Pacific Ocean
Panel 3: A simplified northern hemisphere map showing yellow ducks
        drifting along arrows northward — to Arctic, US East Coast,
        and UK (use small duck silhouettes on ocean currents, no
        country names written)
Panel 4: A simplified southern hemisphere map showing yellow ducks
        drifting along arrows southward — to Hawaii, Indonesia,
        Australia, South America (small duck silhouettes, no labels)
Panel 5: A stylized world map showing ocean currents as glowing
        highway-like ribbons looping around continents, with tiny
        yellow ducks riding along them
Panel 6: A vertical cross-section of the ocean — surface has plastic
        bottles floating, deep sea floor has scattered plastic debris,
        showing plastic occupies both surface and depth

Each panel watercolor + ink style, slightly faded edges.
Aspect ratio: 16:9 overall (or 6:9 if mobile-vertical needed)
```

#### Image 3（第 3 段 / crossSection）

```
[STYLE_BLOCK]
Vertical cross-section of the ocean, three layers from top to bottom:

Top layer (sunlit surface): A few intact plastic bottles and bags
floating, sun rays piercing the water from above
Middle layer (twilight zone): Plastic breaking down into smaller
fragments — irregular pieces, thin filaments, tiny spheres, suspended
in water with bacteria/pollutant particles attached
Bottom layer (deep ocean / Mariana Trench): Dark blue-black background,
small zooplankton (amphipod-like creatures) swimming, with translucent
bodies showing tiny plastic specks inside
A subtle food-chain arrow on the right side: small creature → small
fish → big fish → human fork (no text labels)

Watercolor with ink line work. Educational diagram aesthetic.
Aspect ratio: 9:16 (vertical, suits cross-section)
```

#### Image 4（第 4 段 / collage4）

```
[STYLE_BLOCK]
Four-panel collage (2x2 grid), each panel separated by thin ink lines.
Tone: solemn but not gory, suitable for children.

Panel 1 (top-left): A seabird (gannet or albatross style) on a beach
with plastic fragments around its beak (suggestion only, not graphic)
Panel 2 (top-right): A sea turtle entangled in a fishing net,
struggling but still alive (hopeful tone, not dead)
Panel 3 (bottom-left): A coral reef partially covered by plastic bags
and bottles, dimmed colors showing damaged ecosystem
Panel 4 (bottom-right): A whale silhouette swimming, semi-transparent
body outline showing plastic debris inside (educational diagram style,
not realistic gore)

Watercolor + ink. Muted palette to convey concern.
Aspect ratio: 1:1 (square, suits 2x2)
```

#### Image 5（第 5 段 / dataChart）

```
[STYLE_BLOCK]
Editorial information graphic illustration style.

Center: Two stylized garbage piles drawn as watercolor mounds — left
mound smaller (representing 11 million tons / current), right mound
much larger (representing 29 million tons / 2040 projection). An
arrow grows from left to right showing the increase. The mounds are
made of mixed plastic shapes (bottles, bags, fishing nets).

Surrounding the central scene (in vignette panels):
- Top-left: a river flowing into ocean carrying plastic
- Top-right: a coastal urban area with plastic litter
- Bottom-left: a fishing boat with discarded nets
- Bottom-right: single-use plastic items (cup, straw, bag, container)

All elements drawn in unified watercolor + ink style. No numbers shown
as text — use visual mass to convey scale.
Aspect ratio: 16:9
```

#### Image 6（第 6 段 / collage4）

```
[STYLE_BLOCK]
Four-panel collage (2x2 grid), warm and hopeful tone, brighter palette
than other images.

Panel 1 (top-left): UN-style building with a globe symbol on the
facade, suggesting international cooperation
Panel 2 (top-right): A storefront with "ban" symbols on plastic bags
(no Chinese text), suggesting government regulation
Panel 3 (bottom-left): A group of diverse children and adults on a
beach with reusable bags picking up trash, smiling and active
Panel 4 (bottom-right): Personal eco items — a reusable water bottle,
cloth shopping bag, bamboo utensils, and a recycling symbol

Watercolor + ink. Bright, optimistic palette with greens and warm
earth tones. Conveys "everyone can do something."
Aspect ratio: 1:1
```

#### Image 7（第 7 段 / single）

```
[STYLE_BLOCK]
Close-up of a child's small hand reaching down to a sandy beach,
fingers about to pick up an object. The object is a plastic bottle
cap (clearly recognizable as a bottle cap, not a shell). Around the
hand, a few seashells are present but the focus is the bottle cap.
Background: soft gradient sunset over calm ocean, peaceful but with
a melancholic undertone. Lots of negative space (empty sky/sand) to
let the image breathe and feel reflective.

Watercolor + ink, soft pastel sunset colors (pale orange, dusty pink,
muted blue). Quiet, contemplative mood.
Aspect ratio: 16:9
```

---

## 六、視覺風格與技術要求

### 6.1 整體 UI 風格
- 海洋水彩 + 現代簡潔 UI
- 適合小五生，不要太幼稚也不要太正式
- 有環保警示感但不要恐怖
- Mobile-first，桌面版也要好看

### 6.2 配色（CSS 變數）
```css
:root {
  --bg-primary: #F5EFE0;     /* 沙灘米 */
  --bg-secondary: #FFFFFF;
  --text-primary: #2D3142;    /* 深灰 */
  --text-secondary: #5C6378;
  --accent-deep: #0A4D68;     /* 深海藍 */
  --accent-light: #5BCEFA;    /* 淺海藍 */
  --warning: #E63946;         /* 警示紅 */
  --success: #7BAA66;         /* 行動綠 */
  --gold: #C9A961;            /* 金點綴 */
}
```

### 6.3 字體
- 標題：Noto Serif TC（思源宋體），fallback 系統 serif
- 內文：Noto Sans TC（思源黑體），fallback 系統 sans-serif
- 課文段落字級：手機 18px / 桌面 20px
- 關鍵詞、數據用 `<strong>` + 顏色強調

### 6.4 互動細節
- 每個按鈕 hover/active 都要有視覺反饋
- 模式切換用 transform + opacity 平滑過渡（300ms）
- 答對 / 答錯有微動畫（綠色打勾彈跳 / 紅色搖頭）

### 6.5 技術硬性要求
- ✅ 單一 HTML 檔案
- ✅ 所有 CSS、JS、圖片 base64 都內嵌
- ✅ 不依賴外部 CDN
- ✅ 不使用 React / Vue / 任何框架
- ✅ Vanilla JavaScript ES6+
- ✅ Responsive：375px ~ 1920px 都好看
- ✅ 可離線使用

### 6.6 localStorage 設計

```javascript
{
  "currentMode": "story",                  // 最後使用的模式
  "todayParagraph": 3,                     // 今天該背第幾段
  "completedParagraphs": [1, 2],           // 已標記讀懂的段落
  "memorizedParagraphs": [1],              // 已完成原文還原的段落
  "quizScores": {                          // 每段答對率
    "1": { "total": 6, "correct": 5 },
    "2": { "total": 8, "correct": 6 }
  },
  "challengeProgress": 4,                   // 闖關進度（已完成幾關）
  "lastVisit": "2025-05-05T20:30:00",      // 最後使用時間
  "reviewSchedule": {                       // 複習排程（D+3, D+7, D+30）
    "1": { "next": "2025-05-08", "interval": 3 }
  }
}
```

---

## 七、驗收標準

請確保完成的 HTML 滿足以下檢查清單，**輸出前先逐項自我檢查**：

```
□ 所有七段 originalText 與課文完全一致（一字不差）
□ 八個模式（含原文還原模式）都能從導覽列切換，切換無錯誤
□ 七張圖片成功生成且風格一致
□ 第 2 段是六格分鏡，不是單張圖
□ 第 3 段是垂直剖面圖
□ 第 5 段含資訊圖表元素（不是純插畫）
□ 「原文還原模式」四階段全部實作（看骨架說大意 → 句首提示 → 關鍵詞填空 → 完整遮蔽）
□ 「家長陪背模式」含白話→原文對照卡
□ Mobile（375px 寬）和 Desktop（1280px 寬）都好看
□ localStorage 在重新整理後能保留進度
□ 任何按鈕點下去都有視覺反饋
□ 沒有任何外部 CDN 或 API 依賴
□ 整份 HTML 可以單獨開啟（不需要 server）
□ 七段 quizQuestions 全部融入 Quiz Mode
```

如果有任何項目做不到，**請在輸出 HTML 前先說明哪一項做不到、原因為何**。

---

## 八、輸出要求

1. **直接輸出完整可執行的單檔 HTML**
2. 不要省略 CSS（即使很長）
3. 不要省略 JavaScript（即使很長）
4. 不要只給資料結構或說明
5. 不要要求另外安裝任何套件
6. 不要依賴任何外部資源

### 如果遇到 token 限制

按以下優先序輸出：

1. **必輸出**：HTML 結構 + CSS + 七段資料（JS data 區）+ 故事模式 + 逐段學習模式 + **原文還原模式**
2. **次優先**：家長陪背模式 + 關鍵詞骨架模式
3. **可後續迭代**：遮蔽測試模式 + 打亂問答模式 + 闖關計時模式

並在開頭明確標示：「本次輸出包含 X 個模式，剩餘 Y 個模式請於下次 prompt 補上。」

---

## 九、給 Codex 的最後叮嚀

- 設計優先序：**能讓孩子真的背完今天那一段** > 任何其他考量
- 遇到 UI 不確定時：選擇「促進主動回想」的方案，而非「只是好看」
- 七段內容**請逐字確認與本 prompt 中的 originalText 完全一致**
- 第 2 段是分鏡圖、第 3 段是剖面圖、第 5 段是資訊圖表，**不要全部偷懶用單張圖**
- 學習科學是骨架，UI 是肉，**不要顛倒**

請開始製作。
