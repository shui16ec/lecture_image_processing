# 課題6レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG=imread('Rename1.jpg'); % 原画像の入力
ORG= rgb2gray(ORG);
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み，カラー画像を白黒濃淡画像へ変換した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai6_1.png?raw=true)  
図1 白黒濃淡画像

画像を二値化するには, 256段階の濃度のしきい値を128で区切る方法と, ディザ法によるものがある. 

IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;

IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

濃度のしきい値による二値化画像を図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai6_2.png?raw=true)  
図2 濃度による二値化画像

ディザ法による二値化画像を図３に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai6_3.png?raw=true)  
図3 ディザ法による二値化画像

結果から, ディザ法による画像のほうが, しきい値による画像よりも細かい部分を表現できていることがわかる. 