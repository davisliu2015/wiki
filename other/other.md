# other

### 在iOS中使用Live2D

##### 这里以iOS空项目为例
* iOS的项目名称为iOSLive2D

1. 下载Live2D SDK 下载地址：https://www.live2d.com/zh-CHS/download/cubism-sdk/
2. 将下载文件保存在 xcodeproj 同级目录
3. 解压，并将文件夹名称更改为CubismSdkForNative
4. 创建Target 名称为 CubismNativeFramework Target类型为 Static Library
5. 添加 CubismSdkForNative文件夹到项目中，Added folders选择Create groups，Add to targets 取消所有勾选
6. TARGETS - CubismNativeFramework - Build Phases - Compile Sources 添加编译文件（只需要添加cpp文件）一共37个
7. TARGETS - CubismNativeFramework - Build Settings 
	+ Search Paths - Header Search Paths 配置 $(SRCROOT)/CubismSdkForNative/Core/include （非递归）$(SRCROOT)/CubismSdkForNative/Framework/src （非递归）
	+ Apple Clang Preprocessing - Preprocessor Macros 配置 CSM_TARGET_IPHONE_ES2 GLES_SILENCE_DEPRECATION=1
8. TARGETS - iOSLive2D - General 
	+ Frameworks,Libraries,and Embedded Content 添加 libCubismNativeFramework.a
9. TARGETS - Build Setting
 	+ Linking - Other Linker Flags 配置 -lLive2DCubismCore
 	+ Search Paths - Library Search Paths 配置 "$(SRCROOT)/CubismSdkForNative/Core/lib/ios/$(CONFIGURATION)-$(PLATFORM_NAME)" （debug/release分别配置）
 	+ Search Paths - User Header Search Paths 配置 "$(SRCROOT)/CubismSdkForNative/Core/include" （递归）$(SRCROOT)/CubismSdkForNative/Framework/src （非递归）
 	+ Apple Clang Preprocessing - Preprocessor Macros 配置 L2D_TARGET_IPHONE_ES2 GLES_SILENCE_DEPRECATION=1
 10. 可以尝试在ViewController添加头文件编译，需要将.m更改为.mm
 	





