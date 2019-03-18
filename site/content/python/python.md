+++
title = "Python Basics"
date = 2019-02-26T13:03:26-05:00
weight = 2
enableEmoji = true
+++

## 

#PYTHON

### check if var in var (python)
```python 
{x for x in a if x==x}
```
### to save csv without index column
```python 
df.to_csv('/path/to/csv/file',index=False)
```

### when making an env and you want a specific list of stuff installed
```python 
pip install -r requirements.txt
```
### change column in dataframe from string to integer (python)
```python 
df.loc[:,'gender'] = df.gender.astype(int)
```
### these are notes i took to remind me how to flip my fmri volumes which were ordered A-P,P-A,A-P,P-A,etc
### load an MRI with nibabel (python)
```python 
vol = nibabel.load('P0342_000_01_(opt)_fMRI_MANUAL_PRESCAN_20100731152203_10.nii.gz')
```

### extract image data
```python 
data = vol.get_data()
```

### flip every other volume (1::2 means from vol 1 to end, and every 2nd vol)
```python 
data[...,1::2] = (data[...,1::2])[:,::-1]
```
### make new image from data
```python 
img = nibabel.Nifti1Image(data, vol.affine, header=vol.header)
```
### save new image
```python 
nibabel.save(img,'test2.nii.gz')
```