[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![PyPI version](https://badge.fury.io/py/carveme.svg)](https://badge.fury.io/py/carveme) [![Documentation Status](http://readthedocs.org/projects/carveme/badge/?version=latest)](http://carveme.readthedocs.io/en/latest/?badge=latest)

![CarveMe](logo_300px.png)

## Genome-scale metabolic model reconstruction with CarveMe

CarveMe is a python-based tool for genome-scale metabolic model reconstruction.

### Documentation

For more details please check: http://carveme.readthedocs.io/
 
### Installation

Can be easily installed using **pip**:
```
pip install carveme
```

Additionally, you must install diamond and CPLEX (please check the documentation for details). 

### Credits and License

For citation purposes please refer to our paper:

D. Machado et al, "Fast automated reconstruction of genome-scale metabolic models for microbial species and communities", Nucleic Acids Research, gky537, 2018. 

DOI: https://doi.org/10.1093/nar/gky537

Developed at the European Molecular Biology Laboratory (2017-2018). Released under an Apache License.

### 小修改

小修改一下 以便能用 reframed optlang glpk 代替 framed cplex gurobi

#### Installation

``` shell
conda create -y -n carveme python=3.6.8
conda activate carveme

conda install -c bioconda diamond
conda install optlang

pip install git+https://github.com/xuanyuanXIV/reframed

# 文件太大 下面安装可能失效
pip install git+https://github.com/xuanyuanXIV/carveme
# 用这个替代
git clone git@github.com:xuanyuanXIV/carveme.git
python setup.py sdist bdist_wheel || true
pip install carveme-1.2.3rc0-py2.py3-none-any.whl
```

#### diamond v0.9.29.130

diamond 如果不是这个版本用以下命令重新生成 bigg_proteins.dmnd

``` shell
cd */site-packages/carveme/data/input
diamond makedb --in bigg_proteins.faa -d bigg_proteins
```

#### use

``` shell
carve -v x.faa  --fbc2 --output x.xml
```
