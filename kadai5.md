# 課題5レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG=imread('Rename1.jpg'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，カラー画像を白黒濃淡画像へ変換した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai5_1.png?raw=true)  
図1 白黒濃淡画像

判別分析法を用いて画像を二値化するには, 濃度ヒストグラムを２つのクラスに分け, 
クラス内分散とクラス間分散を求めてその比率が最大となるようにしきい値を求め, そのしきい値により濃度を2分化する.

H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納
myu_T = mean(H);
max_val = 0;
max_thres = 1;
for i=1:255
C1 = H(1:i); %ヒストグラムを2つのクラスに分ける
C2 = H(i+1:256);
n1 = sum(C1); %画素数の算出
n2 = sum(C2);
myu1 = mean(C1); %平均値の算出
myu2 = mean(C2);
sigma1 = var(C1); %分散の算出
sigma2 = var(C2);
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出
if max_val<sigma_B/sigma_w
max_val = sigma_B/sigma_w;
max_thres =i;
end
end

IMG = ORG > max_thres;
imagesc(IMG); colormap(gray); colorbar;

二値化画像を図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai5_2.png?raw=true)  
図2 二値化画像

結果から, 黒い二値化画像が表示され, しきい値が255近辺だということがわかる. 