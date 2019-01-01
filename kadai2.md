# 課題2レポート

画像「Rename1」を原画像とする．この画像は縦4099画素，横2864画素による長方形のディジタルカラー画像である．

ORG=imread('Rename1.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，グレースケールで表示した結果を図１に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/gray_org_img.png?raw=true)  
図1 グレースケールの原画像

原画像から２階調画像を生成するには，画像の輝度値の256段階を2等分して128をしきい値として区切ってそれぞれ画素を分割すればよい. 

IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;

２階調画像の結果を図２に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai2_1.png?raw=true)  
図2 ２階調画像

同様に原画像から４階調画像を生成するには，画像の輝度値の256段階を4等分して64をしきい値として区切ってそれぞれ画素を分割すればよい. すなわち，

IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;

とする．４階調画像の結果を図３に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai2_2.png?raw=true)  
図3 ４階調画像

８階調画像は，画像の輝度値の256段階を8等分して32をしきい値として区切ってそれぞれ画素を分割すればよい. すなわち，

IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>96;
IMG3 = ORG>128;
IMG4 = ORG>160;
IMG5 = ORG>192;
IMG6 = ORG>224;
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;

とする．８階調画像の結果を図４に示す．

![原画像](https://github.com/shui16ec/lecture_image_processing/blob/master/image/kadai2_3.png?raw=true)  
図4 ８階調画像

さらに１６階調にするには, 16をしきい値として同様に分割すればよいと考えられる. 