# perch_data_resources


en_vocab_ranked.txt  ← 現行使用
排序：hermitdave / OpenSubtitles 字幕頻率，與 en_50k 相同（排序不動）
成員：與 wordfreq、SUBTLEX、enwiki 各前 10 萬名比對，需得 2 票以上
      且需在 ECDict 有條目
      含連字號者只要求 ECDict（各語料對連字號分詞不一致，票數是雜訊）
      前 5000 名無條件保留（保護 mr./uh-huh/nothin 這類會被成員判準誤濾的字）
產出腳本：youtube_g_caption/scripts/build_vocab_list.py
72,325 詞，涵蓋 99.44% running text（與 en_50k 相同涵蓋率，但全為真詞彙）

為何要用它取代 en_50k：hermitdave 前 5 萬名裡約 9% 是專有名詞與分詞碎片
（Teemu、MacGyver、didn、chffffff 這類）。它們佔走名次，把使用者其實認識的
真詞擠到 cutoff 之外，反倒被標成生詞。新清單把那些位置還給真詞。


en_50k_words_only.txt  ← 已由 en_vocab_ranked.txt 取代，保留備查
來源：https://github.com/hermitdave/FrequencyWords

去掉了後面的 詞頻數字


phrases_list.txt源自Wiktionary篩選出來的

phrase_kst: 構建phrase list的各種參考文件
* phrase_ecdict.txt源自ECDict 手動 各種 篩篩 出來的 =》現在不用
* phrase_old.txt源自 英漢詞典extract獲取的, lazyworm嗎？不記得了
* mwe_list.txt 源自 Book:A Frequency Dictionary of Multi-Word Expressions in British English Core Phrases and Exercises for Learners，的epub文件，通過ch11.xhtml抽取的，作爲參考

現在不要雙dict了，我也不想構建和維護了；全部由Translate Service查詢，可選四類：
* Google Translate -- 但限流
* Libre Translate -- local 但小衆
* AI -- 可local但需要自己部署，可雲但有一定費用
* Chrome Device-in Ai -- 但不穩定而且Chrome限定

讓用戶使用AI Explain的時候當場調整寫入--這個是custom dict查詢優先級最高
