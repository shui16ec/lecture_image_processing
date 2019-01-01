# 課題10レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG = imread('Rename1.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); %カラーからグレイへの変換
imagesc(ORG); colormap('gray'); colorbar;% 画像表示

によって，原画像を読み込み，カラー画像を白黒濃淡画像へ変換した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai10_1.png?raw=true)  
図1 白黒濃淡画像

画像のエッジを検出するにはプレウィット法がある. 

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

エッジを検出した画像を図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai10_2.png?raw=true)  
図2 エッジを検出した画像

画像のエッジを検出するにはソベル法もある. 

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

エッジを検出した画像を図３に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai10_3.png?raw=true)  
図3 エッジを検出した画像

画像のエッジを検出するにはキャニー法もある. 

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

エッジを検出した画像を図４に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai10_4.png?raw=true)  
図4 エッジを検出した画像

結果から, キャニー法が一番綺麗にエッジを検出できていることがわかる. 