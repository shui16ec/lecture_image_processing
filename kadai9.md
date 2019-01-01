# 課題9レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG = imread('Rename1.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み，カラー画像を白黒濃淡画像へ変換した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai9_1.png?raw=true)  
図1 白黒濃淡画像

ノイズを添付するには, imnoise関数を用いる, ここでは, salt & pepper をパラメータに指定する. 

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

ノイズを添付した画像を図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai9_2.png?raw=true)  
図2 ノイズを添付した画像

ノイズを除去するには, 平滑化フィルタを用いる方法がある. 

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

平滑化フィルタを用いて雑音を除去した画像を図３に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai9_3.png?raw=true)  
図3 平滑化フィルタを用いて雑音を除去した画像

ノイズを除去するには, メディアンフィルタを用いる方法もある. 

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

メディアンフィルタを用いて雑音を除去した画像を図４に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai9_4.png?raw=true)  
図4 メディアンフィルタを用いて雑音を除去した画像

ノイズを除去するには, フィルタを設計する方法もある. 

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

設計したフィルタを用いて雑音を除去した画像を図５に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai9_5.png?raw=true)  
図5 設計したフィルタを用いて雑音を除去した画像

結果から, メディアンフィルタを用いたものが一番綺麗に除去できていることがわかる. 