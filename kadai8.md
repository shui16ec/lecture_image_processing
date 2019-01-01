# 課題8レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG = imread('Rename1.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み，カラー画像を白黒濃淡画像へ変換した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai8_1.png?raw=true)  
図1 白黒濃淡画像

画像を二値化するには, 256段階の濃度のしきい値を128で区切る方法がある. 

IMG = ORG > 128; % 閾値128で二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

濃度のしきい値による二値化画像を図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai8_2.png?raw=true)  
図2 しきい値による二値化画像

二値化された画像の連結成分にラベルをつけるには, bwlabeln関数を用いる. 

連結成分のラベリング画像を図３に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai8_3.png?raw=true)  
図3 連結成分のラベリング画像

結果から, 連結部分ごとに色が異なっていることがわかる. 