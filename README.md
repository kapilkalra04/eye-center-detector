# eye-center-detector
Build a CNN to locate eye centers in cropped face images using the facial keypoints dataset available on [kaggle](https://www.kaggle.com/c/facial-keypoints-detection/data)

## Progress Details -
### 2018/08/10:
#### CNN1
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
	* Overfitting = The NeuralNet has the ability to learn complex patterns
	* We will train CNN_2 now with data augmentation as well
#### CNN2
	Neural Network Architecture:
	* (3x3) | 32
	* (3x3) | 64
	* Dense | 128
	* Dense | 128
	* Dense | 4

	Training Set:
	* 7033 : Eye Centers Kaggle
	* 7033 : Data Augmented Eye Centers Kaggle

	Insights Gained:
	* Ran for **1000** epochs
	* Model showed clear signs of overfitting -
		train_loss ~ 7e-05
		val_loss ~ 5e-02
	* Overfitting = The NeuralNet has the ability to learn complex patterns
	* We will train CNN_2 now with data augmentation and dropout to reduce val_loss