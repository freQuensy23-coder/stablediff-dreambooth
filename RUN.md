1. В отдельном conda env запустите ipynb файл. Выполняя первые ячейки необходимые библиотеки были загружены. Выполнение производилось на Nvidia A100, можно понизить разрешение картинок и batch_size, если при запуске ноутбука происходит RuntimeError: CUDA out of memory.
2. conda.env наслучай конфликтов библиотек
```
   # Name                    Version                   Build  Channel
_libgcc_mutex             0.1                        main
_openmp_mutex             5.1                       1_gnu
abseil-cpp                20211102.0           hd4dd3e8_0
absl-py                   1.4.0           py311h06a4308_0
accelerate                0.22.0                   pypi_0    pypi
aiofiles                  23.2.1                   pypi_0    pypi
aiohttp                   3.8.3           py311h5eee18b_0
aiosignal                 1.2.0              pyhd3eb1b0_0
altair                    5.0.1                    pypi_0    pypi
annotated-types           0.5.0                    pypi_0    pypi
anyio                     3.7.1                    pypi_0    pypi
asttokens                 2.0.5              pyhd3eb1b0_0
async-timeout             4.0.2           py311h06a4308_0
attrs                     23.1.0                   pypi_0    pypi
backcall                  0.2.0              pyhd3eb1b0_0
bitsandbytes              0.41.1                   pypi_0    pypi
bitsandbytes-cuda117      0.26.0.post2             pypi_0    pypi
blas                      1.0                         mkl
blinker                   1.4             py311h06a4308_0
brotlipy                  0.7.0           py311h5eee18b_1002
bzip2                     1.0.8                h7b6447c_0
c-ares                    1.19.0               h5eee18b_0
ca-certificates           2023.05.30           h06a4308_0
cachetools                4.2.2              pyhd3eb1b0_0
certifi                   2023.7.22       py311h06a4308_0
cffi                      1.15.1          py311h5eee18b_3
charset-normalizer        2.0.4              pyhd3eb1b0_0
click                     8.1.7                    pypi_0    pypi
cmake                     3.27.2                   pypi_0    pypi
comm                      0.1.2           py311h06a4308_0
contourpy                 1.1.0                    pypi_0    pypi
cryptography              41.0.2          py311h22a60cf_0
cuda-cudart               11.7.99                       0    nvidia
cuda-cupti                11.7.101                      0    nvidia
cuda-libraries            11.7.1                        0    nvidia
cuda-nvrtc                11.7.99                       0    nvidia
cuda-nvtx                 11.7.91                       0    nvidia
cuda-runtime              11.7.1                        0    nvidia
cycler                    0.11.0                   pypi_0    pypi
debugpy                   1.6.7           py311h6a678d5_0
decorator                 5.1.1              pyhd3eb1b0_0
diffusers                 0.15.0.dev0              pypi_0    pypi
executing                 0.8.3              pyhd3eb1b0_0
fastapi                   0.103.0                  pypi_0    pypi
ffmpeg                    4.3                  hf484d3e_0    pytorch
ffmpy                     0.3.1                    pypi_0    pypi
filelock                  3.9.0           py311h06a4308_0
fonttools                 4.42.1                   pypi_0    pypi
freetype                  2.12.1               h4a9f257_0
frozenlist                1.3.3           py311h5eee18b_0
fsspec                    2023.6.0                 pypi_0    pypi
ftfy                      6.1.1                    pypi_0    pypi
giflib                    5.2.1                h5eee18b_3
gmp                       6.2.1                h295c915_3
gmpy2                     2.1.2           py311hc9b5ff0_0
gnutls                    3.6.15               he1e5248_0
google-auth               2.6.0              pyhd3eb1b0_0
google-auth-oauthlib      0.5.2           py311h06a4308_0
gradio                    3.41.2                   pypi_0    pypi
gradio-client             0.5.0                    pypi_0    pypi
grpc-cpp                  1.48.2               he1ff14a_1
grpcio                    1.48.2          py311he1ff14a_1
h11                       0.14.0                   pypi_0    pypi
httpcore                  0.17.3                   pypi_0    pypi
httpx                     0.24.1                   pypi_0    pypi
huggingface-hub           0.16.4                   pypi_0    pypi
idna                      3.4             py311h06a4308_0
imageio                   2.31.2                   pypi_0    pypi
importlib-metadata        6.8.0                    pypi_0    pypi
importlib-resources       6.0.1                    pypi_0    pypi
intel-openmp              2023.1.0         hdb19cb5_46305
ipykernel                 6.25.0          py311h92b7b1e_0
ipython                   8.12.2          py311h06a4308_0
jedi                      0.18.1          py311h06a4308_1
jinja2                    3.1.2           py311h06a4308_0
jpeg                      9e                   h5eee18b_1
jsonschema                4.19.0                   pypi_0    pypi
jsonschema-specifications 2023.7.1                 pypi_0    pypi
jupyter_client            8.1.0           py311h06a4308_0
jupyter_core              5.3.0           py311h06a4308_0
kiwisolver                1.4.5                    pypi_0    pypi
lame                      3.100                h7b6447c_0
lcms2                     2.12                 h3be6417_0
ld_impl_linux-64          2.38                 h1181459_1
lerc                      3.0                  h295c915_0
libcublas                 11.10.3.66                    0    nvidia
libcufft                  10.7.2.124           h4fbf590_0    nvidia
libcufile                 1.7.1.12                      0    nvidia
libcurand                 10.3.3.129                    0    nvidia
libcusolver               11.4.0.1                      0    nvidia
libcusparse               11.7.4.91                     0    nvidia
libdeflate                1.17                 h5eee18b_0
libffi                    3.4.4                h6a678d5_0
libgcc-ng                 11.2.0               h1234567_1
libgomp                   11.2.0               h1234567_1
libiconv                  1.16                 h7f8727e_2
libidn2                   2.3.4                h5eee18b_0
libnpp                    11.7.4.75                     0    nvidia
libnvjpeg                 11.8.0.2                      0    nvidia
libpng                    1.6.39               h5eee18b_0
libprotobuf               3.20.3               he621ea3_0
libsodium                 1.0.18               h7b6447c_0
libstdcxx-ng              11.2.0               h1234567_1
libtasn1                  4.19.0               h5eee18b_0
libtiff                   4.5.0                h6a678d5_2
libunistring              0.9.10               h27cfd23_0
libuuid                   1.41.5               h5eee18b_0
libwebp                   1.2.4                h11a3e52_1
libwebp-base              1.2.4                h5eee18b_1
lit                       17.0.0rc3                pypi_0    pypi
lz4-c                     1.9.4                h6a678d5_0
markdown                  3.4.1           py311h06a4308_0
markupsafe                2.1.1           py311h5eee18b_0
matplotlib                3.7.2                    pypi_0    pypi
matplotlib-inline         0.1.6           py311h06a4308_0
mkl                       2023.1.0         h213fc3f_46343
mkl-service               2.4.0           py311h5eee18b_1
mkl_fft                   1.3.6           py311ha02d727_1
mkl_random                1.2.2           py311ha02d727_1
mpc                       1.1.0                h10f8cd9_1
mpfr                      4.0.2                hb69a4c5_1
mpmath                    1.3.0           py311h06a4308_0
multidict                 6.0.2           py311h5eee18b_0
natsort                   8.4.0                    pypi_0    pypi
ncurses                   6.4                  h6a678d5_0
nest-asyncio              1.5.6           py311h06a4308_0
nettle                    3.7.3                hbbd107a_1
networkx                  3.1             py311h06a4308_0
numpy                     1.25.2          py311h08b1b3b_0
numpy-base                1.25.2          py311hf175353_0
oauthlib                  3.2.2           py311h06a4308_0
openh264                  2.1.1                h4ff587b_0
openssl                   3.0.10               h7f8727e_2
orjson                    3.9.5                    pypi_0    pypi
packaging                 23.0            py311h06a4308_0
pandas                    2.0.3                    pypi_0    pypi
parso                     0.8.3              pyhd3eb1b0_0
pexpect                   4.8.0              pyhd3eb1b0_3
pickleshare               0.7.5           pyhd3eb1b0_1003
pillow                    10.0.0                   pypi_0    pypi
pip                       23.2.1          py311h06a4308_0
platformdirs              3.10.0          py311h06a4308_0
prompt-toolkit            3.0.36          py311h06a4308_0
protobuf                  3.20.3          py311h6a678d5_0
psutil                    5.9.0           py311h5eee18b_0
ptyprocess                0.7.0              pyhd3eb1b0_2
pure_eval                 0.2.2              pyhd3eb1b0_0
pyasn1                    0.4.8              pyhd3eb1b0_0
pyasn1-modules            0.2.8                      py_0
pycparser                 2.21               pyhd3eb1b0_0
pydantic                  2.3.0                    pypi_0    pypi
pydantic-core             2.6.3                    pypi_0    pypi
pydub                     0.25.1                   pypi_0    pypi
pygments                  2.15.1          py311h06a4308_1
pyjwt                     2.4.0           py311h06a4308_0
pyopenssl                 23.2.0          py311h06a4308_0
pyparsing                 3.0.9                    pypi_0    pypi
pysocks                   1.7.1           py311h06a4308_0
python                    3.11.4               h955ad1f_0
python-dateutil           2.8.2              pyhd3eb1b0_0
python-multipart          0.0.6                    pypi_0    pypi
pytorch                   2.0.1           py3.11_cuda11.7_cudnn8.5.0_0    pytorch
pytorch-cuda              11.7                 h778d358_5    pytorch
pytorch-mutex             1.0                        cuda    pytorch
pytz                      2023.3                   pypi_0    pypi
pyyaml                    6.0.1                    pypi_0    pypi
pyzmq                     25.1.0          py311h6a678d5_0
re2                       2022.04.01           h295c915_0
readline                  8.2                  h5eee18b_0
referencing               0.30.2                   pypi_0    pypi
regex                     2023.8.8                 pypi_0    pypi
requests                  2.31.0          py311h06a4308_0
requests-oauthlib         1.3.0                      py_0
rpds-py                   0.9.2                    pypi_0    pypi
rsa                       4.7.2              pyhd3eb1b0_1
safetensors               0.3.3                    pypi_0    pypi
scipy                     1.11.2                   pypi_0    pypi
semantic-version          2.10.0                   pypi_0    pypi
setuptools                68.0.0          py311h06a4308_0
six                       1.16.0             pyhd3eb1b0_1
sniffio                   1.3.0                    pypi_0    pypi
sqlite                    3.41.2               h5eee18b_0
stack_data                0.2.0              pyhd3eb1b0_0
starlette                 0.27.0                   pypi_0    pypi
sympy                     1.11.1          py311h06a4308_0
tbb                       2021.8.0             hdb19cb5_0
tensorboard               2.12.1          py311h06a4308_0
tensorboard-data-server   0.7.0           py311h52d8a92_0
tensorboard-plugin-wit    1.6.0                      py_0
tk                        8.6.12               h1ccaba5_0
tokenizers                0.13.3                   pypi_0    pypi
toolz                     0.12.0                   pypi_0    pypi
torchaudio                2.0.2               py311_cu117    pytorch
torchvision               0.15.2              py311_cu117    pytorch
tornado                   6.3.2           py311h5eee18b_0
tqdm                      4.66.1                   pypi_0    pypi
traitlets                 5.7.1           py311h06a4308_0
transformers              4.32.0                   pypi_0    pypi
triton                    2.0.0.post1              pypi_0    pypi
typing_extensions         4.7.1           py311h06a4308_0
tzdata                    2023.3                   pypi_0    pypi
urllib3                   1.26.16         py311h06a4308_0
uvicorn                   0.23.2                   pypi_0    pypi
wcwidth                   0.2.5              pyhd3eb1b0_0
websockets                11.0.3                   pypi_0    pypi
werkzeug                  2.2.3           py311h06a4308_0
wheel                     0.38.4          py311h06a4308_0
xformers                  0.0.21                   pypi_0    pypi
xz                        5.4.2                h5eee18b_0
yarl                      1.8.1           py311h5eee18b_0
zeromq                    4.3.4                h2531618_0
zipp                      3.16.2                   pypi_0    pypi
zlib                      1.2.13               h5eee18b_0
zstd                      1.5.5                hc292b87_0
```
