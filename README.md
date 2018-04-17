# Simulator
Simulator Server

思路
1. web界面层：通过Vue.js来做，是否需要electron来打包待定
2. http服务层：有两种做法，通过node.js来做http server，然后node.js与C++ server交互，或者直接在C++ server里提供http服务
3. 网络处理层：基于原有的IOCP来做，进行优化
4. 数据处理层：基于MySQL connector C++来做
5. 设备模拟层：原有代码不用动

实践
1. 开发平台升级：C++ Builder 6.0切换到VS 2017
2. web界面层：原来是基于C++ Builder 6.0的界面控件，现在要切换到web
3. http服务层：如果是C++里提供http，可以考虑mongoose
4. 数据处理层：原来是通过C++ Builder 6.0的zeoslib来访问MySQL，现在要切换到MySQL connector C++
5. 其他代码优化，包括C++实践和面向对象设计的优化

进度
