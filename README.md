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
4. 网络处理层: 仍然基于IOCP来做，不过要优化原有的设计
5. 数据处理层：原来是通过C++ Builder 6.0的zeoslib来访问MySQL，现在要切换到MySQL connector C++,需要重新设计相关类，尽量使API与原来相似
6. 其他代码优化，包括C++实践和面向对象设计的优化

主要的类：
Simulator:

DBConnector：
ExecSQL();
Add();
Clear();
resultSet;

Network:

NE(Network Element,网络设备)：

NEManager:
private:
+initNEDB
+initNEMem
+initNENetwork= addIP + initNESocket
+queryNE
+queryAllNE
public:
+addNE = (initNEDB + initNEMem + initNENetwork)
+loadNE = (queryNEDB + initNEMem + initNENetwork)
+loadAllNE = (queryAllNE + foreach(loadNE))
新增部分用DTO和DAO

DTO:
NEInfoDTO
DAO:
NEInfoDAO

NESimulator：
NEList
DB driver
Http
Workthread

IOCP如何处理：



进度
1.初步完成了一个简单

的DBConnector，API与zeoslib尽量一直(Done)
2.改造NE（网络设备）类，移除原来C++ Builder相关的API，用std里相关的API代替(Done)
3.新增NEManager类，整合梳理原来NE相关的API

