# 課題3レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG=imread('Rename1.jpg'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み，カラー画像を白黒濃淡画像へ変換した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai3_1.png?raw=true)  
図1 白黒濃淡画像

しきい値を設定し, 2値画像にするには, 輝度値がしきい値以上の画素を1，その他を0に変換すればよい.

IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換
imagesc(IMG); colormap(gray); colorbar;

しきい値64での2値画像の結果を図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai3_2.png?raw=true)  
図2 しきい値64での2値画像

しきい値 96, 128, 192 で処理するには, それぞれ

IMG = ORG > 96;
imagesc(IMG); colormap(gray); colorbar;
pause;

IMG = ORG > 128;
imagesc(IMG); colormap(gray); colorbar;
pause;

IMG = ORG > 192;
imagesc(IMG); colormap(gray); colorbar;

とすればよい. 結果をそれぞれ図3~図5に示す. 

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai3_3.png?raw=true)  
図3 しきい値96での2値画像

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai3_4.png?raw=true)  
図4 しきい値128での2値画像

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai3_5.png?raw=true)  
図5 しきい値192での2値画像

結果から, しきい値が大きくなると黒い画素の割合が多くなることがわかる. 