# 服务器安装python

### 服务器安装tensorflow失败，可能是python版本不够
```
pip3 install --upgrade pip
python3 -m pip install --upgrade setuptools
pip3 install --no-cache-dir  --force-reinstall -Iv grpcio==1.23.0
```