## Dependency
GCC 11.4.0, CUDA toolkits 12, conda  2020.07


## Installation

- clone this repo
- create the env and install the requirements
  
  ```bash
  $ conda create --name pace python=3.8
  $ conda activate pace
  $ conda install pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch
  $ conda install pyg -c pyg
  $ pip install e3nn
  $ pip install torch-ema
  $ pip install prettytable
  $ pip install ase==3.22.1
  ```

## Data
The raw data in xyz format is provided in `AIRS/OpenMol/PACE/dataset`. The rMD17 data is downloaded from its [official source](https://figshare.com/articles/dataset/Revised_MD17_dataset_rMD17_/12672038). 3BPA and AcAc datasets are from [BOTNet-datasets](https://github.com/davkovacs/BOTNet-datasets).

## 

```bash
python main_rmd17.py --device $DEVICE --task task_name --output_dir ./results/pace/aspirin --num_bessel 6
```
task_name为任务名，即example文件夹下对应的各文件夹名，例如aspirin,aspirin_dft,Azobenzene,Benzene...
此外,还需要更改./PACE/dataset/PygMD17.py文件的raw_file_names函数(~40行)，其输出为对应输入文件路径；
main_rmd17~.py文件的train_dataset/valid_dataset/test_dataset的root为存放或加载数据文件的路径。



## Citation

Please cite our paper if you find our paper useful.
```
@article{
    xu2024equivariant,
    title={Equivariant Graph Network Approximations of High-Degree Polynomials for Force Field Prediction},
    author={Zhao Xu and Haiyang Yu and Montgomery Bohde and Shuiwang Ji},
    journal={Transactions on Machine Learning Research},
    issn={2835-8856},
    year={2024},
    url={https://openreview.net/forum?id=7DAFwp0Vne},
    note={Featured Certification}
}
```

## Acknowledgments

This work was supported in part by National Science Foundation grant IIS-2243850 and National Institutes of Health grant U01AG070112.
