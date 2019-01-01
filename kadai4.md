# 課題4レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG=imread('Rename1.jpg'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，カラー画像を白黒濃淡画像へ変換した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai4_1.png?raw=true)  
図1 白黒濃淡画像

画像の濃度ヒストグラムを表示するには, imhist関数を使えばよい.

imhist(ORG); % ヒストグラムの表示

画像の濃度ヒストグラムを図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai4_2.png?raw=true)  
図2 画像の濃度ヒストグラム

結果から, 複数の山があるヒストグラムが生成された. 