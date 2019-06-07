# Chatacter-Recognition

矩陣範例

![image]https://github.com/wele7764/Chatacter-Recognition/blob/master/Matrix.jpg

其中第一直行表示 A 的辨認中,辨認為A的樣本數有405個,便認為B的樣本數有6個.... 依此類推



我們將資料量分成A,B,C個級數

並用 Random Forests , Xgboost , SVM  三種算法來辨識圖片

A 集 :

images[A].shape = (1872L, 28L, 28L)<br/>
images[B].shape = (1873L, 28L, 28L)<br>
images[C].shape = (1873L, 28L, 28L)<br>
images[D].shape = (1873L, 28L, 28L)<br>
images[E].shape = (1873L, 28L, 28L)<br>
images[F].shape = (1872L, 28L, 28L)<br>
images[G].shape = (1872L, 28L, 28L)<br>
images[H].shape = (1872L, 28L, 28L)<br>
images[I].shape = (1872L, 28L, 28L)<br>
images[J].shape = (1872L, 28L, 28L)<br>
Total datasets size<br>
===================<br>
n_samples: 18724<br>
n_features: 784<br>
n_classes: 10<br>
===================<br>

B 集 :

images[A].shape = (6546L, 28L, 28L)<br>
images[B].shape = (7689L, 28L, 28L)<br>
images[C].shape = (8261L, 28L, 28L)<br>
images[D].shape = (7788L, 28L, 28L)<br>
images[E].shape = (7507L, 28L, 28L)<br>
images[F].shape = (7885L, 28L, 28L)<br>
images[G].shape = (7788L, 28L, 28L)<br>
images[H].shape = (7757L, 28L, 28L)<br>
images[I].shape = (8071L, 28L, 28L)<br>
images[J].shape = (7955L, 28L, 28L)<br>
Total datasets size<br>
===================<br>
n_samples: 77247<br>
n_features: 784<br>
n_classes: 10<br>
===================<br>

C 集 :

images[A].shape = (54781L, 28L, 28L)<br>
images[B].shape = (54784L, 28L, 28L)<br>
images[C].shape = (54785L, 28L, 28L)<br>
images[D].shape = (54784L, 28L, 28L)<br>
images[E].shape = (54785L, 28L, 28L)<br>
images[F].shape = (54784L, 28L, 28L)<br>
images[G].shape = (54784L, 28L, 28L)<br>
images[H].shape = (54784L, 28L, 28L)<br>
images[I].shape = (54784L, 28L, 28L)<br>
images[J].shape = (54783L, 28L, 28L)<br>
Total datasets size<br>
===================<br>
n_samples: 547838<br>
n_features: 784<br>
n_classes: 10<br>
===================<br>

來去做各種比對

就資料量而言:
A組(最少=18724): 由Xgboost得到最好的準確性

B組(中等=77247):SVM和Xgboost得到的準確差不多

C組(最多=547838):由於SVM程式執行讓電腦跑不太動，我們將SVM的資料集字母A的部分增加到跟其他演算法的資料量一樣多(54781)，最後只看A字母的精準度。
最後由SVM的準度大大提升，所以如果資料十分充足的情況下SVM最為精準。

最後得到:

Romdan Forests : 處理速度最快，可以得到不錯的結果

Xgboost : 資料量少時，發揮彌補資料缺失性的功能

SVM : 資料充足時，圖片辨識效果最好，但執行時間過於冗長


附檔 NotMNIST為A組資料量


參考 http://ihong-blog.logdown.com/posts/463271-font-recongonition-notmnist-svm 來實作
