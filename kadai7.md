# 課題7レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG = imread('Rename1.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み，カラー画像を白黒濃淡画像へ変換した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai7_1.png?raw=true)  
図1 白黒濃淡画像


画像の濃度ヒストグラムを表示するには, imhist関数を使えばよい.

imhist(ORG); % ヒストグラムの表示

画像の濃度ヒストグラムを図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai7_2.png?raw=true)  
図2 画像の濃度ヒストグラム

画像のダイナミックレンジを256段階に拡大するには, 画像の濃度値の最大最小値を求めて, その幅と, 
ある画素の濃度値との割合に255を掛けて新たな濃度値とすればよい. 

ORG = double(ORG);
mn = min(ORG(:)); % 濃度値の最小値を算出
mx = max(ORG(:)); % 濃度値の最大値を算出
ORG = (ORG-mn)/(mx-mn)*255;
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

画素のダイナミックレンジを256段階に拡大した画像を図３に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai7_3.png?raw=true)  
図3 ダイナミックレンジを拡大した画像

画像の濃度ヒストグラムを表示するには, imhist関数を使えばよい.

ORG = uint8(ORG); % この行について考察せよ
imhist(ORG); % 濃度ヒストグラムを生成、表示

レンジ拡大後の画像の濃度ヒストグラムを図４に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai7_4.png?raw=true)  
図4 レンジ拡大後の画像の濃度ヒストグラム

unit8関数を使用するのは, 小数に変換した濃度値を整数に戻して, 処理前と処理後の縦のレンジを揃えるためだと考えられる. 