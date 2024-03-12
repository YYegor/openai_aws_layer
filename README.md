_Error: No module named 'pydantic_core._pydantic_core' in AWS Lambda when using openai package.__

When using openai package in AWS lambda, you need to add *openai* package to the function.
This can be done by adding a layer to the function.

There are 2 key points when adding a layer:
1. folder name in the zip of the layer
2. modules' architecture



**Instruction**

1. This zip can be added as a layer for python 3.9, for x86_64. 
Just upload zip to the layer.
2. Do not forget to match the architecture of your layer.
3. Well done!


If you want to prepare your own python layer:

1. run pip, or pip3.x

if you are using **MacOS** witn non-intel cpu (M1, M2, etc) use key "--platform manylinux2014_x86_64" for pip
>pip3.9 install openai --platform manylinux2014_x86_64 -t . --only-binary=:all:

2. copy folders with libs to the path python\lib\python3.9\site-packages\
where 'python' is just a local folder.
3. zip the 'python' folder.
4. do not forget to match the architecture of your layer.
5. Well done! 





more official docs: https://docs.aws.amazon.com/lambda/latest/dg/adding-layers.html
