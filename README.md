# perch_data_resources


en_50k_words_only.txt
來源：https://github.com/hermitdave/FrequencyWords

去掉了後面的 詞頻數字


phrases_list.txt源自Wiktionary篩選出來的

phrase_kst: 構建phrase list的各種參考文件
* phrase_ecdict.txt源自ECDict 手動 各種 篩篩 出來的 =》現在不用
* phrase_old.txt源自 英漢詞典extract獲取的, lazyworm嗎？不記得了

現在不要雙dict了，我也不想構建和維護了；全部由Translate Service查詢，可選四類：
* Google Translate -- 但限流
* Libre Translate -- local 但小衆
* AI -- 可local但需要自己部署，可雲但有一定費用
* Chrome Device-in Ai -- 但不穩定而且Chrome限定

讓用戶使用AI Explain的時候當場調整寫入--這個是custom dict查詢優先級最高
