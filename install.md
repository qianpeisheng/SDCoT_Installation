# SDCoT Installation (CUDA 10.2 Python 3.8)

1. Clone the repository, `git clone https://github.com/Na-Z/SDCoT.git`.
2. Go to the SDCoT folder, `cd SDCoT`.
3. Replace the following in the `pointnet2` folder to use with CUDA 10.2, Pytorch 1.9.1 or higher. You can use the search tab on the right of VSCode for searching and replacing.
 - `AT_CHECK` -> `TORCH_CHECK`.
 - `type.is_cuda()` -> `is_cuda()`.
 - `.data<float>()` -> `.data_ptr<float>()`, and `.data<int>()` -> `.data_ptr<int>()`. Beware of the `.` at front.
4. Create the virtual environment, `python3 -m venv venv`.
5. Activate the virtual environment, `source venv/bin/activate`.
6. Update packages, `pip3 install --upgrade pip setuptools wheel`
7. Install PyTorch, `pip3 install torch==1.9.1+cu102 torchvision==0.10.1+cu102 torchaudio==0.9.1 -f https://download.pytorch.org/whl/torch_stable.html`
8. Install Pointnet2, `cd pointnet2/` and `python3 setup.py install`.
9. Install other packages, `pip3 install -r requirements_2.txt`, which removes package versions and correct the name for `scikit-learn`.
10. Debug `setuptools` version, `pip3 uninstall setuptools` and `pip3 install setuptools==59.5.0`. Referring to [link](https://github.com/pytorch/pytorch/issues/69894#issuecomment-1080635462).






