# seq2seq_model

整理一下看到並且自己實作過的seq2seq (or + attention) model，作業類型大約都是偏語言相關的，與時間序列資料(如趨勢預測)較無關聯。另外目前使用+實作的attention mechanism 皆為Bahdanau attention (keras, tensorflow)與Loung attention (tensorflow)，尚未使用到Attention is all you need 論文中的multi-head self attention (後續持續新增，有看到keras有人已實作muti-head self attention Layer)

---

## Demo 1

1. [seq2seq_tensorflow_demo1](https://github.com/tan800630/seq2seq_model/blob/master/seq2seq_tensorflow_demo1.ipynb)

以英法文翻譯為目標的seq2seq model，使用tensorflow框架 (自己嘗試過以此為基礎再加上attention mechanism 但效果差不多，也許是資料本  身的長度較短的原因，尚待嘗試)

2. [seq2seq_attenion_keras_demo1](https://github.com/tan800630/seq2seq_model/blob/master/seq2seq_attenion_keras_demo1.ipynb)

同樣使用英法文翻譯資料(與1.相同)，然而使用keras框架實作的attention model (Bahdanau attention，align function使用神經網路架構)，與原先的seq2seq比較起來正確率差異不大(約97.0%)

## Demo 2

3. [seq2seq_without_att_demo2](https://github.com/tan800630/seq2seq_model/blob/master/seq2seq_without_att_demo2.ipynb)

使用另一個top example訓練的seq2seq model (輸入一串隨機數字並要求模型只將偶數部分按順序回傳，並且重複兩次，例如輸入為： [1 2 3 4 5]，輸出應為： [2 4 2 4])。使用的框架為tensorflow，為比較有無attention的影響，故意將輸入數字串的長度調大(max length = 48)。

4. [seq2seq_attention_demo2](https://github.com/tan800630/seq2seq_model/blob/master/seq2seq_attention_demo2.ipynb)

同模型3. ，但以attention wrapper實作attention mechanism。可與模型3. 比較收斂速度、正確率、以及預測結果。

## Demo 3

5. [seq2seq_attention_keras_demo3](https://github.com/tan800630/seq2seq_model/blob/master/seq2seq_attention_keras_demo3.ipynb)

使用toy example 訓練的attention model (輸入一串隨機數字並只要求模型回傳前兩個數字，其他地方改輸出"0"，例如輸入為: [1 2 3 4 5]，輸出需為： [1 2 0 0 0])，使用的框架同樣為keras (與2.相同)，此作業在訓練時可以達到1.0的正確率，然而測試大概只有將近80%左右的正確率，應是有點overfitting了，可以考慮假資料產生的數量跟變異再大一點。


---
#### 註：參考之資源皆列在ipynb中，若有侵權等相關行為再請告知，我會盡速移除相關內容或做其他處理
