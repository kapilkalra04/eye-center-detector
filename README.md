# eye-center-detector
Build a CNN to locate eye centers in cropped face images using the facial keypoints dataset available on [kaggle](https://www.kaggle.com/c/facial-keypoints-detection/data)

## Progress Details -
### 2018/08/10: 
	Neural Network Architecture:
	* (3x3) | 32
	* (3x3) | 64
	* Dense | 128
	* Dense | 128
	* Dense | 4

	Training Set:
	* 7033 : Eye Centers Kaggle

	Insights Gained:
	* Ran for **1000** epochs
	* Model showed clear signs of overfitting -
		train_loss ~ 1.5e-04
		val_loss ~ 2.5e-03
	* We will train CNN_2 now with data augmentation as well
