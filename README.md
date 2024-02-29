1.首先搭建片段推荐系统的环境
确保已经安装了anaconda或者miniconda
（1）python版本3.7
conda create -n  NLSExplorer-pyto python==3.7
安装pytorch 以及支持pytorch进行gpu计算的包 可以尝试直接输入以下命令
conda install pytorch torchvision torchaudio cudatoolkit -c pytorch -c nvidia
安装依赖项
conda env update -f environment-pyto.yaml
dssp的安装:
conda install -c ostrokach dssp
which mkdssp
vim ~/.bashrc
添加到文件末尾export PATH=$PATH:/home/server/miniconda3/envs/NLSExplorer-pyto/bin/mkdssp
source ~/.bashrc

https://swift.cmbi.umcn.nl/gv/dssp/
If you use DSSP, please quote these two articles:

1) A series of PDB related databases for everyday needs.
Wouter G Touw, Coos Baakman, Jon Black, Tim AH te Beek, E Krieger, Robbie P Joosten, Gert Vriend.
Nucleic Acids Research 2015 January; 43(Database issue): D364-D368.
(PDF).

2) Dictionary of protein secondary structure: pattern recognition of hydrogen-bonded and geometrical features.
Kabsch W, Sander C,
Biopolymers. 1983 22 2577-2637.
PMID: 6667333; UI: 84128824.


（2）
python版本3.9
conda create --name NLSExplorer-pyto2 --clone NLSExplorer-pyto2 
安装对应版本的pytorch
conda install pytorch torchvision torchaudio cudatoolkit -c pytorch -c nvidia

如果你在运行过程中提示缺失了库，则先执行下面的安装
pip install scikit-learn
pip install pandas
pip install tqdm
pip install egnn_pytorch
pip install torch-geometric
pip install --no-index torch-scatter -f https://pytorch-geometric.com/whl/torch-1.13.0+cu117.html
pip install fair-esm==2.0.0