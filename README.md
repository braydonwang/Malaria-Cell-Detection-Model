# Malaria-Cell-Detection-Model

Dataset can be found at https://www.kaggle.com/iarunava/cell-images-for-detecting-malaria

<img width="1000" alt="Cells" src="https://github.com/braydonwang/Malaria-Cell-Detection-Model/blob/main/images/malariacells.png">

## How I built it
1. Download the dataset
2. Import the dataset into PyTorch using ImageFolder (resize and crop each image)
```
dataset = ImageFolder(data_dir, tt.Compose([tt.Resize(64), 
                                            tt.RandomCrop(64),
                                            tt.ToTensor()]))
```
3. Split dataset into two groups: training set and validating set
```
train_ds, valid_ds = random_split(dataset, [train_size, val_size])
```
4. Prepare the set for training (using DataLoader and make_grid)
5. Move the dataset to the GPU
6. Define a neural network (ResNet9)
7. Train the model
8. Plot losses against epochs
9. Test model and record the results
