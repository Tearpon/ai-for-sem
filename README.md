# Xception-MicroNet-MultiScale-CBAM 近红外SEM图像EQE预测推理代码
## Dependencies
torch, torchvision, pandas, numpy, matplotlib, tqdm, scikit-learn, pillow

## Usage
1. Modify three absolute paths in script: model weight, test image folder, test csv label file
2. Run script, auto inference, sort samples by absolute error, save csv results and visualization
3. Terminal only output the save path of visualization figure

## Output Files
1. paper_test_full.csv: all prediction data with absolute & relative error
2. paper_test_simple.csv: only image name + predicted EQE
3. top20_min_error.png: visualization of top20 samples with smallest prediction error
