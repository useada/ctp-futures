### 封装ctp 期货api接口
* ctp version 6.3 看穿式
* 使用rust-bindgen先生成主要代码，然后使用clang解析cpp头文件，生成spi的代码(因为目前rust-bindgen不会生成pure virtual class function)
* ctp_autu_test用于看穿式验证申请，只需要修改build.rs里的链接目录即可
* 引入derive bincode::Encode, bincode::Decode, 方便进行简单的序列化


### macos

```shell
cd thostmduserapi_se.framework
rm -rf Headers           Resources thostmduserapi_se
ln -s Versions/A/Headers Headers
ln -s Versions/A/Resources Resources
ln -s Versions/A/thostmduserapi_se thostmduserapi_se

cd thosttraderapi_se.framework
rm -rf Headers           Resources thosttraderapi_se
ln -s Versions/A/Headers Headers
ln -s Versions/A/Resources Resources
ln -s Versions/A/thosttraderapi_se thosttraderapi_se


sudo cp -r thostmduserapi_se.framework thosttraderapi_se.framework /Library/Frameworks
```