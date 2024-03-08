# pybind11用テンプレート  

ほぼ公式が出しているcmakeのパクリです。  
参考:https://github.com/pybind/cmake_example  

これを使うと、PythonからC++のソースコードを呼び出すことができる。  

ビルド  
成功すれば、buildディレクトリの中に.soファイルが作られる
```
python setup.py build
```

pip install
```
pip install .
```

# 例
```
git clone  --recursive git@github.com:yudai0804/cmake_example.git
cd cmake_example
pip install .
python src/test.py
```

# 注意
setup.pyの内容は使うときに必ず書き換えること。  
参考(公式の出しているcmake_exampleのsetup.pyより)
```
setup(
    name="cmake_example",
    version="0.0.1",
    author="Dean Moldovan",
    author_email="dean0x7d@gmail.com",
    description="A test project using pybind11 and CMake",
    long_description="",
    ext_modules=[CMakeExtension("cmake_example")],
    cmdclass={"build_ext": CMakeBuild},
    zip_safe=False,
    extras_require={"test": ["pytest>=6.0"]},
    python_requires=">=3.7",
)
```

setup.pyはかなり賢いのでいろいろやってくれます。