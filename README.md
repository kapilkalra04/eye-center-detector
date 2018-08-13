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
		train_loss 	~ 1.5e-04
		val_loss 	~ 2.5e-03
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
		train_loss 	~ 7e-05
		val_loss 	~ 5e-02
	* Overfitting = The NeuralNet has the ability to learn complex patterns
	* We will train CNN_3 now with dropout to reduce val_loss

### 2018/08/11:
#### CNN3
	Neural Network Architecture
	* (3x3) | 32
	* Dropout | 0.1
	* (3x3) | 64
	* Dropout | 0.2
	* Flatten
	* Dense | 128
	* Dropout | 0.3
	* Dense | 128
	* Dropout | 0.4
	* Dense | 4

	Training Set
	* 7033 : Eye Centers
	* 7033 : Eye Centers; Data Augmented (LR Flipped)

	Insights Gained:
	* Ran for **2000** epochs
	* Model still showed signs of overfitting but this time rate of overfitting was slow
		train_loss 	~ 6.2e-03
		val_los 	~ 7.4e-02
	* Total params: 4,000,904. Let's try to reduce this in CNN_4 while improving on val_loss

#### CNN4
	Neural Network Architecture:
	* (3x3) | 32
	* (3x3) | 64
	* Flatten
	* Dense | 64
	* Dense | 64
	* Dense | 4

	Training Set:
	* 7033 : Eye Centers

	Insights Gained:
	* Ran for **1000** epochs
	* Model still overfits
		train_loss 	~ 1.1e-04
		val_loss 	~ 1.9e-03
	* Total params: 2,005,768. Even with half params than before the NN overfits. Therefore reducing the width of our NN was a good idea, Next step is to if data augmentation can help us 

