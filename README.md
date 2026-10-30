# -
Computer room reservation system
# 机房预约系统

## 1、机房预约系统需求

### 1.1 系统简介

* 学校现有几个规格不同的机房，由于使用时经常出现"撞车"现象,现开发一套机房预约系统，解决这一问题。

![1548682783885](assets/1548682783885.png)

### 1.2 身份简介

分别有三种身份使用该程序

* **学生代表**：申请使用机房
* **教师**：审核学生的预约申请
* **管理员**：给学生、教师创建账号

### 1.3 机房简介

机房总共有3间

* 1号机房   --- 最大容量20人
* 2号机房   --- 最多容量50人
* 3号机房   --- 最多容量100人

### 1.4 申请简介

* 申请的订单每周由管理员负责清空。
* 学生可以预约未来一周内的机房使用，预约的日期为周一至周五，预约时需要选择预约时段（上午、下午）
* 教师来审核预约，依据实际情况审核预约通过或者不通过

### 1.5 系统具体需求

* 首先进入登录界面，可选登录身份有：
  * 学生代表
  * 老师
  * 管理员
  * 退出
* 每个身份都需要进行验证后，进入子菜单
  * 学生需要输入 ：学号、姓名、登录密码
  * 老师需要输入：职工号、姓名、登录密码
  * 管理员需要输入：管理员姓名、登录密码
* 学生具体功能
  * 申请预约    ---   预约机房
  * 查看自身的预约    ---  查看自己的预约状态
  * 查看所有预约   ---   查看全部预约信息以及预约状态
  * 取消预约    ---   取消自身的预约，预约成功或审核中的预约均可取消
  * 注销登录    ---   退出登录
* 教师具体功能
  * 查看所有预约   ---   查看全部预约信息以及预约状态
  * 审核预约    ---   对学生的预约进行审核
  * 注销登录    ---   退出登录
* 管理员具体功能
  * 添加账号    ---   添加学生或教师的账号，需要检测学生编号或教师职工号是否重复
  * 查看账号    ---   可以选择查看学生或教师的全部信息
  * 查看机房    ---   查看所有机房的信息
  * 清空预约    ---   清空所有预约记录
  * 注销登录    ---   退出登录



![1548682206670](assets/1548682206670.png)



## 2、创建项目

创建项目步骤如下：

- 创建新项目
- 添加文件

### 2.1 创建项目

- 打开vs2017后，点击创建新项目，创建新的C++项目

如图：

![1548682413343](assets/1548682413343.png)

* 填写项目名称以及选取项目路径，点击确定生成项目

![1548682522544](assets/1548682522544.png)

### 2.2 添加文件

- 右键源文件，进行添加文件操作

![1548682597721](assets/1548682597721.png)

* 填写文件名称，点击添加

![1548682679989](assets/1548682679989.png)

* 生成文件成功，效果如下图

![1548682733912](assets/1548682733912.png)



## 3、创建主菜单

**功能描述：**

* 设计主菜单，与用户进行交互

### 3.1 菜单实现

* 在主函数main中添加菜单提示，代码如下：

```C++
int main() {

	cout << "======================  欢迎来到传智播客机房预约系统  =====================" 
         << endl;
	cout << endl << "请输入您的身份" << endl;
	cout << "\t\t -------------------------------\n";
	cout << "\t\t|                               |\n";
	cout << "\t\t|          1.学生代表           |\n";
	cout << "\t\t|                               |\n";
	cout << "\t\t|          2.老    师           |\n";
	cout << "\t\t|                               |\n";
	cout << "\t\t|          3.管 理 员           |\n";
	cout << "\t\t|                               |\n";
	cout << "\t\t|          0.退    出           |\n";
	cout << "\t\t|                               |\n";
	cout << "\t\t -------------------------------\n";
	cout << "输入您的选择: ";

	system("pause");

	return 0;
}
```



运行效果如图：

![1548557945611](assets/1548557945611.png)



### 3.2 搭建接口

* 接受用户的选择，搭建接口
* 在main中添加代码

```C++
int main() {

	int select = 0;

	while (true)
	{

		cout << "======================  欢迎来到传智播客机房预约系统  =====================" << endl;
		cout << endl << "请输入您的身份" << endl;
		cout << "\t\t -------------------------------\n";
		cout << "\t\t|                               |\n";
		cout << "\t\t|          1.学生代表           |\n";
		cout << "\t\t|                               |\n";
		cout << "\t\t|          2.老    师           |\n";
		cout << "\t\t|                               |\n";
		cout << "\t\t|          3.管 理 员           |\n";
		cout << "\t\t|                               |\n";
		cout << "\t\t|          0.退    出           |\n";
		cout << "\t\t|                               |\n";
		cout << "\t\t -------------------------------\n";
		cout << "输入您的选择: ";

		cin >> select; //接受用户选择

		switch (select)
		{
		case 1:  //学生身份
			break;
		case 2:  //老师身份
			break;
		case 3:  //管理员身份
			break;
		case 0:  //退出系统
			break;
		default:
             cout << "输入有误，请重新选择！" << endl;
		    system("pause");
			system("cls");
			break;
		}

	}
	system("pause");
	return 0;
}
```

测试，输入0、1、2、3会重新回到界面，输入其他提示输入有误，清屏后重新选择

效果如图：

![1548558694230](assets/1548558694230.png)

至此，界面搭建完毕





## 4、 退出功能实现

### 4.1 退出功能实现

在main函数分支 0 选项中，添加退出程序的代码：

```C++
	cout << "欢迎下一次使用"<<endl;
	system("pause");
	return 0;
```



![1548558992754](assets/1548558992754.png)



### 4.2 测试退出功能

运行程序，效果如图：

![1548559026436](assets/1548559026436.png)

至此，退出程序功能实现





## 5、 创建身份类

### 5.1 身份的基类

* 在整个系统中，有三种身份，分别为：学生代表、老师以及管理员
* 三种身份有其共性也有其特性，因此我们可以将三种身份抽象出一个身份基类**identity**
* 在头文件下创建Identity.h文件



Identity.h中添加如下代码：

```C++
#pragma once
#include<iostream>
using namespace std;

//身份抽象类
class Identity
{
public:

	//操作菜单
	virtual void operMenu() = 0;

	string m_Name; //用户名
	string m_Pwd;  //密码
};
```

效果如图：

![1548573329273](assets/1548573329273.png)







### 5.2 学生类

#### 5.2.1 功能分析

* 学生类主要功能是可以通过类中成员函数，实现预约实验室操作

* 学生类中主要功能有：

  * 显示学生操作的菜单界面
  * 申请预约
  * 查看自身预约
  * 查看所有预约
  * 取消预约

  

#### 5.2.2 类的创建

* 在头文件以及源文件下创建 student.h 和 student.cpp文件



student.h中添加如下代码：

```C++
#pragma once
#include<iostream>
using namespace std;
#include "identity.h"

//学生类
class Student :public Identity
{
public:
	//默认构造
	Student();

	//有参构造(学号、姓名、密码)
	Student(int id, string name, string pwd);

	//菜单界面
	virtual void operMenu(); 

	//申请预约
	void applyOrder(); 

	//查看我的预约
	void showMyOrder(); 

	//查看所有预约
	void showAllOrder(); 

	//取消预约
	void cancelOrder();
	
	//学生学号
	int m_Id;

};
```



student.cpp中添加如下代码：

```C++
#include "student.h"

//默认构造
Student::Student()
{
}

//有参构造(学号、姓名、密码)
Student::Student(int id, string name, string pwd)
{
}

//菜单界面
void Student::operMenu()
{
}

//申请预约
void Student::applyOrder()
{

}

//查看我的预约
void Student::showMyOrder()
{

}

//查看所有预约
void Student::showAllOrder()
{

}

//取消预约
void Student::cancelOrder()
{

}

```





### 5.3 老师类

#### 5.3.1 功能分析

- 教师类主要功能是查看学生的预约，并进行审核

- 教师类中主要功能有：

  - 显示教师操作的菜单界面

  - 查看所有预约

  - 审核预约

    

#### 5.3.2 类的创建

- 在头文件以及源文件下创建 teacher.h 和 teacher.cpp文件

teacher.h中添加如下代码：

```C++
#pragma once
#define _CRT_SECURE_NO_WARNINGS
#include<iostream>
using namespace std;
#include "identity.h"

class Teacher :public Identity
{
public:

	//默认构造
	Teacher();

	//有参构造 (职工编号，姓名，密码)
	Teacher(int empId, string name, string pwd);

	//菜单界面
	virtual void operMenu();

	//查看所有预约
	void showAllOrder(); 

	//审核预约
	void validOrder(); 

	int m_EmpId; //教师编号

};
```



* teacher.cpp中添加如下代码:

```C++
#include"teacher.h"

//默认构造
Teacher::Teacher()
{
}

//有参构造 (职工编号，姓名，密码)
Teacher::Teacher(int empId, string name, string pwd)
{
}

//菜单界面
void Teacher::operMenu()
{
}

//查看所有预约
void Teacher::showAllOrder()
{
}

//审核预约
void Teacher::validOrder()
{
}
```









### 5.4 管理员类

#### 5.4.1 功能分析

- 管理员类主要功能是对学生和老师账户进行管理，查看机房信息以及清空预约记录

- 管理员类中主要功能有：

  - 显示管理员操作的菜单界面

  - 添加账号

  - 查看账号

  - 查看机房信息

  - 清空预约记录

    

#### 5.4.2 类的创建

- 在头文件以及源文件下创建 manager.h 和 manager.cpp文件

manager.h中添加如下代码：

```C++
#pragma once
#include<iostream>
using namespace std;
#include "identity.h"

class Manager :public Identity
{
public:

	//默认构造
	Manager();

	//有参构造  管理员姓名，密码
	Manager(string name, string pwd);

	//选择菜单
	virtual void operMenu();

	//添加账号  
	void addPerson();

	//查看账号
	void showPerson();

	//查看机房信息
	void showComputer();

	//清空预约记录
	void cleanFile();

};
```



* manager.cpp中添加如下代码:

```C++
#include "manager.h"

//默认构造
Manager::Manager()
{
}

//有参构造
Manager::Manager(string name, string pwd)
{
}

//选择菜单
void Manager::operMenu()
{
}

//添加账号  
void Manager::addPerson()
{
}

//查看账号
void Manager::showPerson()
{
}

//查看机房信息
void Manager::showComputer()
{
}

//清空预约记录
void Manager::cleanFile()
{
}
```

至此，所有身份类创建完毕，效果如图：

![1548574390768](assets/1548574390768.png)









## 6、  登录模块

### 6.1 全局文件添加

功能描述：

* 不同的身份可能会用到不同的文件操作，我们可以将所有的文件名定义到一个全局的文件中
* 在头文件中添加 **globalFile.h** 文件
* 并添加如下代码：

```C++
#pragma once 

//管理员文件
#define ADMIN_FILE     "admin.txt"
//学生文件
#define STUDENT_FILE   "student.txt"
//教师文件
#define TEACHER_FILE   "teacher.txt"
//机房信息文件
#define COMPUTER_FILE  "computerRoom.txt"
//订单文件
#define ORDER_FILE     "order.txt"
```



并且在同级目录下，创建这几个文件

![1548575650130](assets/1548575650130.png)



### 6.2  登录函数封装

功能描述：

* 根据用户的选择，进入不同的身份登录

在预约系统的.cpp文件中添加全局函数 `void LoginIn(string fileName, int type)`

参数：

* fileName  --- 操作的文件名
* type      ---  登录的身份  （1代表学生、2代表老师、3代表管理员）



LoginIn中添加如下代码：

```C++
#include "globalFile.h"
#include "identity.h"
#include <fstream>
#include <string>


//登录功能
void LoginIn(string fileName, int type)
{

	Identity * person = NULL;

	ifstream ifs;
	ifs.open(fileName, ios::in);

	//文件不存在情况
	if (!ifs.is_open())
	{
		cout << "文件不存在" << endl;
		ifs.close();
		return;
	}

	int id = 0;
	string name;
	string pwd;

	if (type == 1)	//学生登录
	{
		cout << "请输入你的学号" << endl;
		cin >> id;
	}
	else if (type == 2) //教师登录
	{
		cout << "请输入你的职工号" << endl;
		cin >> id;
	}

	cout << "请输入用户名：" << endl;
	cin >> name;

	cout << "请输入密码： " << endl;
	cin >> pwd;


	if (type == 1)
	{
		//学生登录验证
	}
	else if (type == 2)
	{
		//教师登录验证
	}
	else if(type == 3)
	{
		//管理员登录验证
	}
	
	cout << "验证登录失败!" << endl;

	system("pause");
	system("cls");
	return;
}
```

* 在main函数的不同分支中，填入不同的登录接口

![1548575945985](assets/1548575945985.png)







### 6.3 学生登录实现

在student.txt文件中添加两条学生信息，用于测试

添加信息:   

```c++
1 张三 123
2 李四 123456
```

其中：

* 第一列  代表  **学号**
* 第二列  代表  **学生姓名**
* 第三列  代表  **密码**

效果图：

![1548583693555](assets/1548583693555.png)

在Login函数的学生分支中加入如下代码，验证学生身份

```C++
		//学生登录验证
		int fId;
		string fName;
		string fPwd;
		while (ifs >> fId && ifs >> fName && ifs >> fPwd)
		{
			if (id == fId && name == fName && pwd == fPwd)
			{
				cout << "学生验证登录成功!" << endl;
				system("pause");
				system("cls");
				person = new Student(id, name, pwd);
				
				return;
			}
		}
```

添加代码效果图

![1548583915819](assets/1548583915819.png)

测试：

![1548583950828](assets/1548583950828.png)







### 6.4 教师登录实现

在teacher.txt文件中添加一条老师信息，用于测试

添加信息:   

```c++
1 老王 123
```

其中：

- 第一列  代表  **教师职工编号**
- 第二列  代表  **教师姓名**
- 第三列  代表  **密码**

效果图：

![1548584030522](assets/1548584030522.png)

在Login函数的教师分支中加入如下代码，验证教师身份

```c++
		//教师登录验证
		int fId;
		string fName;
		string fPwd;
		while (ifs >> fId && ifs >> fName && ifs >> fPwd)
		{
			if (id == fId && name == fName && pwd == fPwd)
			{
				cout << "教师验证登录成功!" << endl;
				system("pause");
				system("cls");
				person = new Teacher(id, name, pwd);
				return;
			}
		}
```

添加代码效果图

![1548584158339](assets/1548584158339.png)

测试：

![1548584177003](assets/1548584177003.png)







### 6.5 管理员登录实现

在admin.txt文件中添加一条管理员信息，由于我们只有一条管理员，因此本案例中没有添加管理员的功能

添加信息:   

```C++
admin 123
```

其中：`admin`代表管理员用户名，`123`代表管理员密码

效果图：

![1548577855190](assets/1548577855190.png)

在Login函数的管理员分支中加入如下代码，验证管理员身份

```C++
//管理员登录验证
		string fName;
		string fPwd;
		while (ifs >> fName && ifs >> fPwd)
		{
			if (name == fName && pwd == fPwd)
			{
				cout << "验证登录成功!" << endl;
				//登录成功后，按任意键进入管理员界面
				system("pause");
				system("cls");
				//创建管理员对象
				person = new Manager(name,pwd);
				return;
			}
		}
```

添加效果如图：

![1548588322712](assets/1548588322712.png)

测试效果如图：

![1548583245072](assets/1548583245072.png)



至此，所有身份的登录功能全部实现！







## 7、 管理员模块

### 7.1  管理员登录和注销

#### 7.1.1 构造函数

* 在Manager类的构造函数中，初始化管理员信息，代码如下：

```C++
//有参构造
Manager::Manager(string name, string pwd)
{
	this->m_Name = name;
	this->m_Pwd = pwd;
}
```





#### 7.1.2  管理员子菜单

* 在机房预约系统.cpp中，当用户登录的是管理员，添加管理员菜单接口
* 将不同的分支提供出来
  * 添加账号
  * 查看账号
  * 查看机房
  * 清空预约
  * 注销登录
* 实现注销功能

添加全局函数 `void managerMenu(Identity * &manager)`，代码如下：

```C++
//管理员菜单
void managerMenu(Identity * &manager)
{
	while (true)
	{
		//管理员菜单
		manager->operMenu();

		Manager* man = (Manager*)manager;
		int select = 0;

		cin >> select;
        
		if (select == 1)  //添加账号
		{
			cout << "添加账号" << endl;
			man->addPerson();
		}
		else if (select == 2) //查看账号
		{
			cout << "查看账号" << endl;
			man->showPerson(); 
		}
		else if (select == 3) //查看机房
		{
			cout << "查看机房" << endl;
			man->showComputer();
		}
		else if (select == 4) //清空预约
		{
			cout << "清空预约" << endl;
			man->cleanFile();
		}
		else
		{
			delete manager;
			cout << "注销成功" << endl;
			system("pause");
			system("cls");
			return;
		}
	}
}
```



#### 7.1.3 菜单功能实现

- 在实现成员函数`void Manager::operMenu()` 代码如下：

```c++
//选择菜单
void Manager::operMenu()
{
	cout << "欢迎管理员："<<this->m_Name << "登录！" << endl;
	cout << "\t\t ---------------------------------\n";
	cout << "\t\t|                                |\n";
	cout << "\t\t|          1.添加账号            |\n";
	cout << "\t\t|                                |\n";
	cout << "\t\t|          2.查看账号            |\n";
	cout << "\t\t|                                |\n";
	cout << "\t\t|          3.查看机房            |\n";
	cout << "\t\t|                                |\n";
	cout << "\t\t|          4.清空预约            |\n";
	cout << "\t\t|                                |\n";
	cout << "\t\t|          0.注销登录            |\n";
	cout << "\t\t|                                |\n";
	cout << "\t\t ---------------------------------\n";
	cout << "请选择您的操作： " << endl;
}
```



#### 7.1.4 接口对接

* 管理员成功登录后，调用管理员子菜单界面
* 在管理员登录验证分支中，添加代码：

```C++
				//进入管理员子菜单
				managerMenu(person);
```

添加效果如：

![1548589297779](assets/1548589297779.png)

测试对接，效果如图：

![1548589344206](assets/1548589344206.png)

登录成功

![1548589328710](assets/1548589328710.png)

注销登录：

![1548589416576](assets/1548589416576.png)

至此，管理员身份可以成功登录以及注销



### 7.2 添加账号 

功能描述：

* 给学生或教师添加新的账号

功能要求：

* 添加时学生学号不能重复、教师职工号不能重复



#### 7.2.1 添加功能实现

在Manager的**addPerson**成员函数中，实现添加新账号功能，代码如下：

```C++
//添加账号  
void Manager::addPerson()
{

	cout << "请输入添加账号的类型" << endl;
	cout << "1、添加学生" << endl;
	cout << "2、添加老师" << endl;

	string fileName;
	string tip;
	ofstream ofs;

	int select = 0;
	cin >> select;

	if (select == 1)
	{
		fileName = STUDENT_FILE;
		tip = "请输入学号： ";
	}
	else
	{
		fileName = TEACHER_FILE;
		tip = "请输入职工编号：";
	}

	ofs.open(fileName, ios::out | ios::app);
	int id;
	string name;
	string pwd;
	cout <<tip << endl;
	cin >> id;

	cout << "请输入姓名： " << endl;
	cin >> name;

	cout << "请输入密码： " << endl;
	cin >> pwd;

	ofs << id << " " << name << " " << pwd << " " << endl;
	cout << "添加成功" << endl;

	system("pause");
	system("cls");

	ofs.close();
}
```



测试添加学生：

![1548641024216](assets/1548641024216.png)

成功在学生文件中添加了一条信息

![1548641141027](assets/1548641141027.png)

测试添加教师：

![1548641195834](assets/1548641195834.png)

成功在教师文件中添加了一条信息

![1548641237513](assets/1548641237513.png)



#### 7.2.2 去重操作

功能描述：添加新账号时，如果是重复的学生编号，或是重复的教师职工编号，提示有误

##### 7.2.2.1 读取信息

* 要去除重复的账号，首先要先将学生和教师的账号信息获取到程序中，方可检测
* 在manager.h中，添加两个容器，用于存放学生和教师的信息
* 添加一个新的成员函数  `void initVector()` 初始化容器

```C++
	//初始化容器
	void initVector();

	//学生容器
	vector<Student> vStu;

	//教师容器
	vector<Teacher> vTea;
```

添加位置如图：

![1548644354561](assets/1548644354561.png)

在Manager的有参构造函数中，获取目前的学生和教师信息

代码如下：

```C++
void Manager::initVector()
{
	//读取学生文件中信息
	ifstream ifs;
	ifs.open(STUDENT_FILE, ios::in);
	if (!ifs.is_open())
	{
		cout << "文件读取失败" << endl;
		return;
	}
    
	vStu.clear();
     vTea.clear();
    
	Student s;
	while (ifs >> s.m_Id && ifs >> s.m_Name &&  ifs >> s.m_Pwd)
	{
		vStu.push_back(s);
	}
	cout << "当前学生数量为： " << vStu.size() << endl;
	ifs.close(); //学生初始化

	//读取老师文件信息
	ifs.open(TEACHER_FILE, ios::in);

	Teacher t;
	while (ifs >> t.m_EmpId && ifs >> t.m_Name &&  ifs >> t.m_Pwd)
	{
		vTea.push_back(t);
	}
	cout << "当前教师数量为： " << vTea.size() << endl;

	ifs.close();
}
```



在有参构造函数中，调用初始化容器函数

```C++
//有参构造
Manager::Manager(string name, string pwd)
{
	this->m_Name = name;
	this->m_Pwd = pwd;
    
	//初始化容器
	this->initVector();
}
```





测试，运行代码可以看到测试代码获取当前学生和教师数量

![1548642488049](assets/1548642488049.png)



##### 7.2.2.2 去重函数封装

在manager.h文件中添加成员函数` bool checkRepeat(int id, int type);`

```C++
	//检测重复 参数:(传入id，传入类型) 返回值：(true 代表有重复，false代表没有重复)
	bool checkRepeat(int id, int type);
```



在manager.cpp文件中实现成员函数  ` bool checkRepeat(int id, int type);`

```C++
bool Manager::checkRepeat(int id, int type)
{
	if (type == 1)
	{
		for (vector<Student>::iterator it = vStu.begin(); it != vStu.end(); it++)
		{
			if (id == it->m_Id)
			{
				return true;
			}
		}
	}
	else
	{
		for (vector<Teacher>::iterator it = vTea.begin(); it != vTea.end(); it++)
		{
			if (id == it->m_EmpId)
			{
				return true;
			}
		}
	}
	return false;
}
```



##### 7.2.2.3 添加去重操作

在添加学生编号或者教师职工号时，检测是否有重复，代码如下：

```C++
	string errorTip; //重复错误提示

	if (select == 1)
	{
		fileName = STUDENT_FILE;
		tip = "请输入学号： ";
		errorTip = "学号重复，请重新输入";
	}
	else
	{
		fileName = TEACHER_FILE;
		tip = "请输入职工编号：";
		errorTip = "职工号重复，请重新输入";
	}
	ofs.open(fileName, ios::out | ios::app);
	int id;
	string name;
	string pwd;
	cout <<tip << endl;

	while (true)
	{
		cin >> id;

		bool ret = this->checkRepeat(id, 1);

		if (ret) //有重复
		{
			cout << errorTip << endl;
		}
		else
		{
			break;
		}
	}
```

代码位置如图：

![1548643909979](assets/1548643909979.png)



检测效果：



![1548644151974](assets/1548644151974.png)



##### 7.2.2.4 bug解决

bug描述：

* 虽然可以检测重复的账号，但是刚添加的账号由于没有更新到容器中，因此不会做检测
* 导致刚加入的账号的学生号或者职工编号，再次添加时依然可以重复

解决方案：

* 在每次添加新账号时，重新初始化容器

在添加完毕后，加入代码：

```C++
	//初始化容器
	this->initVector();
```

位置如图：

![1548644779578](assets/1548644779578.png)

再次测试，刚加入的账号不会重复添加了！





### 7.3  显示账号

功能描述：显示学生信息或教师信息



#### 7.3.1 显示功能实现

在Manager的**showPerson**成员函数中，实现显示账号功能，代码如下：

```C++
void printStudent(Student & s)
{
	cout << "学号： " << s.m_Id << " 姓名： " << s.m_Name << " 密码：" << s.m_Pwd << endl;
}
void printTeacher(Teacher & t)
{
	cout << "职工号： " << t.m_EmpId << " 姓名： " << t.m_Name << " 密码：" << t.m_Pwd << endl;
}

void Manager::showPerson()
{
	cout << "请选择查看内容：" << endl;
	cout << "1、查看所有学生" << endl;
	cout << "2、查看所有老师" << endl;

	int select = 0;

	cin >> select;
    
	if (select == 1)
	{
		cout << "所有学生信息如下： " << endl;
		for_each(vStu.begin(), vStu.end(), printStudent);
	}
	else
	{
		cout << "所有老师信息如下： " << endl;
		for_each(vTea.begin(), vTea.end(), printTeacher);
	}
	system("pause");
	system("cls");
}
```



#### 7.3.2 测试

测试查看学生效果

![1548646791248](assets/1548646791248.png)



测试查看教师效果

![1548646833665](assets/1548646833665.png)

至此，显示账号功能实现完毕





### 7.4 查看机房

#### 7.4.1 添加机房信息

案例需求中，机房一共有三个，其中1号机房容量20台机器，2号50台，3号100台

我们可以将信息录入到computerRoom.txt中

![1548647538570](assets/1548647538570.png)



#### 7.4.2 机房类创建

在头文件下，创建新的文件 computerRoom.h

并添加如下代码：

```C++
#pragma once
#include<iostream>
using namespace std;
//机房类
class ComputerRoom
{
public:

	int m_ComId; //机房id号

	int m_MaxNum; //机房最大容量
};
```





#### 7.4.3 初始化机房信息

在Manager管理员类下，添加机房的容器,用于保存机房信息

```C++
	//机房容器
	vector<ComputerRoom> vCom;
```

在Manager有参构造函数中，追加如下代码，初始化机房信息

```C++
	//获取机房信息
	ifstream ifs;

	ifs.open(COMPUTER_FILE, ios::in);

	ComputerRoom c;
	while (ifs >> c.m_ComId && ifs >> c.m_MaxNum)
	{
		vCom.push_back(c);
	}
	cout << "当前机房数量为： " << vCom.size() << endl;

	ifs.close();
```

位置如图：

![1548647976462](assets/1548647976462.png)

因为机房信息目前版本不会有所改动，如果后期有修改功能，最好封装到一个函数中，方便维护



#### 7.4.4 显示机房信息

在Manager类的showComputer成员函数中添加如下代码：

```C++
//查看机房信息
void Manager::showComputer()
{
	cout << "机房信息如下： " << endl;
	for (vector<ComputerRoom>::iterator it = vCom.begin(); it != vCom.end(); it++)
	{
		cout << "机房编号： " << it->m_ComId << " 机房最大容量： " << it->m_MaxNum << endl;
	}
	system("pause");
	system("cls");
}
```

测试显示机房信息功能：

![1548648276929](assets/1548648276929.png)





### 7.5 清空预约

功能描述：

清空生成的`order.txt`预约文件

#### 7.5.1 清空功能实现

在Manager的cleanFile成员函数中添加如下代码：

```C++
//清空预约记录
void Manager::cleanFile()
{
	ofstream ofs(ORDER_FILE, ios::trunc);
	ofs.close();

	cout << "清空成功！" << endl;
	system("pause");
	system("cls");
}
```

测试清空，可以随意写入一些信息在order.txt中，然后调用cleanFile清空文件接口，查看是否清空干净







## 8、 学生模块

### 8.1 学生登录和注销

#### 8.1.1 构造函数

- 在Student类的构造函数中，初始化学生信息，代码如下：

```c++
//有参构造(学号、姓名、密码)
Student::Student(int id, string name, string pwd)
{
	//初始化属性
	this->m_Id = id;
	this->m_Name = name;
	this->m_Pwd = pwd;
}
```



#### 8.1.2  管理员子菜单

- 在机房预约系统.cpp中，当用户登录的是学生，添加学生菜单接口
- 将不同的分支提供出来
  - 申请预约
  - 查看我的预约
  - 查看所有预约
  - 取消预约
  - 注销登录
- 实现注销功能

添加全局函数 `void studentMenu(Identity * &manager)` 代码如下：

```C++
//学生菜单
void studentMenu(Identity * &student)
{
	while (true)
	{
		//学生菜单
		student->operMenu();

		Student* stu = (Student*)student;
		int select = 0;

		cin >> select;

		if (select == 1) //申请预约
		{
			stu->applyOrder();
		}
		else if (select == 2) //查看自身预约
		{
			stu->showMyOrder();
		}
		else if (select == 3) //查看所有预约
		{
			stu->showAllOrder();
		}
		else if (select == 4) //取消预约
		{
			stu->cancelOrder();
		}
		else
		{
			delete student;
			cout << "注销成功" << endl;
			system("pause");
			system("cls");
			return;
		}
	}
}
```



#### 8.1.3 菜单功能实现

- 在实现成员函数`void Student::operMenu()` 代码如下：

```c++
//菜单界面
void Student::operMenu()
{
	cout << "欢迎学生代表：" << this->m_Name << "登录！" << endl;
	cout << "\t\t ----------------------------------\n";
	cout << "\t\t|                                 |\n";
	cout << "\t\t|          1.申请预约              |\n";
	cout << "\t\t|                                 |\n";
	cout << "\t\t|          2.查看我的预约          |\n";
	cout << "\t\t|                                 |\n";
	cout << "\t\t|          3.查看所有预约          |\n";
	cout << "\t\t|                                 |\n";
	cout << "\t\t|          4.取消预约              |\n";
	cout << "\t\t|                                 |\n";
	cout << "\t\t|          0.注销登录              |\n";
	cout << "\t\t|                                 |\n";
	cout << "\t\t ----------------------------------\n";
	cout << "请选择您的操作： " << endl;
}
```



#### 8.1.4 接口对接

- 学生成功登录后，调用学生的子菜单界面
- 在学生登录分支中，添加代码：

```c++
				//进入学生子菜单
				studentMenu(person);
```

添加效果如图：

![1548659552298](assets/1548659552298.png)

测试对接，效果如图：

登录验证通过：

![1548659590221](assets/1548659590221.png)

学生子菜单：

![1548659670651](assets/1548659670651.png)

注销登录：

![1548659682402](assets/1548659682402.png)



### 8.2 申请预约

#### 8.2.1 获取机房信息

* 在申请预约时，学生可以看到机房的信息，因此我们需要让学生获取到机房的信息

在student.h中添加新的成员函数如下：

```C++
	//机房容器
	vector<ComputerRoom> vCom;
```

在学生的有参构造函数中追加如下代码：

```C++
	//获取机房信息
	ifstream ifs;
	ifs.open(COMPUTER_FILE, ios::in);

	ComputerRoom c;
	while (ifs >> c.m_ComId && ifs >> c.m_MaxNum)
	{
		vCom.push_back(c);
	}

	ifs.close();
```

追加位置如图：

![1548661562158](assets/1548661562158.png)

至此，vCom容器中保存了所有机房的信息



#### 8.2.2 预约功能实现

在student.cpp中实现成员函数 `void Student::applyOrder()`

```C++
//申请预约
void Student::applyOrder()
{
	cout << "机房开放时间为周一至周五！" << endl;
	cout << "请输入申请预约的时间：" << endl;
	cout << "1、周一" << endl;
	cout << "2、周二" << endl;
	cout << "3、周三" << endl;
	cout << "4、周四" << endl;
	cout << "5、周五" << endl;
	int date = 0;
	int interval = 0;
	int room = 0;

	while (true)
	{
		cin >> date;
		if (date >= 1 && date <= 5)
		{
			break;
		}
		cout << "输入有误，请重新输入" << endl;
	}


	cout << "请输入申请预约的时间段：" << endl;
	cout << "1、上午" << endl;
	cout << "2、下午" << endl;

	while (true)
	{
		cin >> interval;
		if (interval >= 1 && interval <= 2)
		{
			break;
		}
		cout << "输入有误，请重新输入" << endl;
	}

	cout << "请选择机房：" << endl;
	cout << "1号机房容量：" << vCom[0].m_MaxNum << endl;
	cout << "2号机房容量：" << vCom[1].m_MaxNum << endl;
	cout << "3号机房容量：" << vCom[2].m_MaxNum << endl;

	while (true)
	{
		cin >> room;
		if (room >= 1 && room <= 3)
		{
			break;
		}
		cout << "输入有误，请重新输入" << endl;
	}

	cout << "预约成功！审核中" << endl;

	ofstream ofs(ORDER_FILE, ios::app);
	ofs << "date:" << date << " ";
	ofs << "interval:" << interval << " ";
	ofs << "stuId:" << this->m_Id << " ";
	ofs << "stuName:" << this->m_Name << " ";
	ofs << "roomId:" << room << " ";
	ofs << "status:" << 1 << endl;

	ofs.close();

	system("pause");
	system("cls");
}
```



运行程序，测试代码:

![1548728936052](assets/1548728936052.png)

在order.txt文件中生成如下内容：

![1548662281801](assets/1548662281801.png)





### 8.3 显示预约

#### 8.3.1 创建预约类

功能描述：显示预约记录时，需要从文件中获取到所有记录，用来显示，创建预约的类来管理记录以及更新

在头文件以及源文件下分别创建**orderFile.h** 和 **orderFile.cpp**文件

orderFile.h中添加如下代码：

```C++
#pragma once
#include<iostream>
using namespace std;
#include <map>
#include "globalFile.h"

class OrderFile
{
public:

	//构造函数
	OrderFile();

	//更新预约记录
	void updateOrder();

	//记录的容器  key --- 记录的条数  value --- 具体记录的键值对信息
	map<int, map<string, string>> m_orderData;

	//预约记录条数
	int m_Size;
};
```



**构造函数**中获取所有信息，并存放在容器中，添加如下代码：

```C++
OrderFile::OrderFile()
{
	ifstream ifs;
	ifs.open(ORDER_FILE, ios::in);

	string date;      //日期
	string interval;  //时间段
	string stuId;     //学生编号
	string stuName;   //学生姓名
	string roomId;    //机房编号
	string status;    //预约状态


	this->m_Size = 0; //预约记录个数

	while (ifs >> date && ifs >> interval && ifs >> stuId && ifs >> stuName && ifs >> roomId &&  ifs >> status)
	{
		//测试代码
		/*
		cout << date << endl;
		cout << interval << endl;
		cout << stuId << endl;
		cout << stuName << endl;
		cout << roomId << endl;
		cout << status << endl;
		*/

		string key;
		string value;
		map<string, string> m;

		int pos = date.find(":");
		if (pos != -1)
		{
			key = date.substr(0, pos);
			value = date.substr(pos + 1, date.size() - pos -1);
			m.insert(make_pair(key, value));
		}

		pos = interval.find(":");
		if (pos != -1)
		{
			key = interval.substr(0, pos);
			value = interval.substr(pos + 1, interval.size() - pos -1 );
			m.insert(make_pair(key, value));
		}

		pos = stuId.find(":");
		if (pos != -1)
		{
			key = stuId.substr(0, pos);
			value = stuId.substr(pos + 1, stuId.size() - pos -1 );
			m.insert(make_pair(key, value));
		}

		pos = stuName.find(":");
		if (pos != -1)
		{
			key = stuName.substr(0, pos);
			value = stuName.substr(pos + 1, stuName.size() - pos -1);
			m.insert(make_pair(key, value));
		}

		pos = roomId.find(":");
		if (pos != -1)
		{
			key = roomId.substr(0, pos);
			value = roomId.substr(pos + 1, roomId.size() - pos -1 );
			m.insert(make_pair(key, value));
		}

		pos = status.find(":");
		if (pos != -1)
		{
			key = status.substr(0, pos);
			value = status.substr(pos + 1, status.size() - pos -1);
			m.insert(make_pair(key, value));
		}


		this->m_orderData.insert(make_pair(this->m_Size, m));
		this->m_Size++;
	}

	//测试代码
	//for (map<int, map<string, string>>::iterator it = m_orderData.begin(); it != m_orderData.end();it++)
	//{
	//	cout << "key = " << it->first << " value = " << endl;
	//	for (map<string, string>::iterator mit = it->second.begin(); mit != it->second.end(); mit++)
	//	{
	//		cout << mit->first << " " << mit->second << " ";
	//	}
	//	cout << endl;
	//}
    
    ifs.close();
}

```



更新预约记录的成员函数updateOrder代码如下：

```C++
void OrderFile::updateOrder()
{
	if (this->m_Size == 0)
	{
		return;
	}

	ofstream ofs(ORDER_FILE, ios::out | ios::trunc);
	for (int i = 0; i < m_Size;i++)
	{
		ofs << "date:" << this->m_orderData[i]["date"] << " ";
		ofs << "interval:" << this->m_orderData[i]["interval"] << " ";
		ofs << "stuId:" << this->m_orderData[i]["stuId"] << " ";
		ofs << "stuName:" << this->m_orderData[i]["stuName"] << " ";
		ofs << "roomId:" << this->m_orderData[i]["roomId"] << " ";
		ofs << "status:" << this->m_orderData[i]["status"] << endl;
	}
    ofs.close();
}
```



#### 8.3.2 显示自身预约

首先我们先添加几条预约记录，可以用程序添加或者直接修改order.txt文件

order.txt文件内容如下： 比如我们有三名同学分别产生了3条预约记录

![1548667534747](assets/1548667534747.png)

在Student类的`void Student::showMyOrder()`成员函数中，添加如下代码

```C++
//查看我的预约
void Student::showMyOrder()
{
	OrderFile of;
	if (of.m_Size == 0)
	{
		cout << "无预约记录" << endl;
		system("pause");
		system("cls");
		return;
	}
	for (int i = 0; i < of.m_Size; i++)
	{
		if (atoi(of.m_orderData[i]["stuId"].c_str()) == this->m_Id)
		{
			cout << "预约日期： 周" << of.m_orderData[i]["date"];
			cout << " 时段：" << (of.m_orderData[i]["interval"] == "1" ? "上午" : "下午");
			cout << " 机房：" << of.m_orderData[i]["roomId"];
			string status = " 状态： ";  // 0 取消的预约   1 审核中   2 已预约 -1 预约失败
			if (of.m_orderData[i]["status"] == "1")
			{
				status += "审核中";
			}
			else if (of.m_orderData[i]["status"] == "2")
			{
				status += "预约成功";
			}
			else if (of.m_orderData[i]["status"] == "-1")
			{
				status += "审核未通过，预约失败";
			}
			else
			{
				status += "预约已取消";
			}
			cout << status << endl;

		}
	}

	system("pause");
	system("cls");
}
```

测试效果如图：

![1548667252474](assets/1548667252474.png)



#### 8.3.3 显示所有预约

在Student类的`void Student::showAllOrder()`成员函数中，添加如下代码

```C++
//查看所有预约
void Student::showAllOrder()
{
	OrderFile of;
	if (of.m_Size == 0)
	{
		cout << "无预约记录" << endl;
		system("pause");
		system("cls");
		return;
	}

	for (int i = 0; i < of.m_Size; i++)
	{
		cout << i + 1 << "、 ";

		cout << "预约日期： 周" << of.m_orderData[i]["date"];
		cout << " 时段：" << (of.m_orderData[i]["interval"] == "1" ? "上午" : "下午");
		cout << " 学号：" << of.m_orderData[i]["stuId"];
		cout << " 姓名：" << of.m_orderData[i]["stuName"];
		cout << " 机房：" << of.m_orderData[i]["roomId"];
		string status = " 状态： ";  // 0 取消的预约   1 审核中   2 已预约 -1 预约失败
		if (of.m_orderData[i]["status"] == "1")
		{
			status += "审核中";
		}
		else if (of.m_orderData[i]["status"] == "2")
		{
			status += "预约成功";
		}
		else if (of.m_orderData[i]["status"] == "-1")
		{
			status += "审核未通过，预约失败";
		}
		else
		{
			status += "预约已取消";
		}
		cout << status << endl;
	}

	system("pause");
	system("cls");
}
```

测试效果如图：

![1548667591734](assets/1548667591734.png)



### 8.4 取消预约

在Student类的`void Student::cancelOrder()`成员函数中，添加如下代码

```C++
//取消预约
void Student::cancelOrder()
{
	OrderFile of;
	if (of.m_Size == 0)
	{
		cout << "无预约记录" << endl;
		system("pause");
		system("cls");
		return;
	}
	cout << "审核中或预约成功的记录可以取消，请输入取消的记录" << endl;

	vector<int>v;
	int index = 1;
	for (int i = 0; i < of.m_Size; i++)
	{
		if (atoi(of.m_orderData[i]["stuId"].c_str()) == this->m_Id)
		{
			if (of.m_orderData[i]["status"] == "1" || of.m_orderData[i]["status"] == "2")
			{
				v.push_back(i);
				cout <<  index ++  << "、 ";
				cout << "预约日期： 周" << of.m_orderData[i]["date"];
				cout << " 时段：" << (of.m_orderData[i]["interval"] == "1" ? "上午" : "下午");
				cout << " 机房：" << of.m_orderData[i]["roomId"];
				string status = " 状态： ";  // 0 取消的预约   1 审核中   2 已预约  -1 预约失败
				if (of.m_orderData[i]["status"] == "1")
				{
					status += "审核中";
				}
				else if (of.m_orderData[i]["status"] == "2")
				{
					status += "预约成功";
				}
				cout << status << endl;

			}
		}
	}

	cout << "请输入取消的记录,0代表返回" << endl;
	int select = 0;
	while (true)
	{
		cin >> select;
		if (select >= 0 && select <= v.size())
		{
			if (select == 0)
			{
				break;
			}
			else
			{
				//	cout << "记录所在位置： " << v[select - 1] << endl;
				of.m_orderData[v[select - 1]]["status"] = "0";
				of.updateOrder();
				cout << "已取消预约" << endl;
				break;
			}

		}
		cout << "输入有误，请重新输入" << endl;
	}

	system("pause");
	system("cls");
}

```

测试取消预约：

![1548669551036](assets/1548669551036.png)

再次查看个人预约记录：

![1548669728023](assets/1548669728023.png)

查看所有预约

![1548669753496](assets/1548669753496.png)

查看order.txt预约文件

![1548669798037](assets/1548669798037.png)

至此，学生模块功能全部实现





## 9、 教师模块

### 9.1 教师登录和注销

#### 9.1.1 构造函数

- 在Teacher类的构造函数中，初始化教师信息，代码如下：

```c++
//有参构造 (职工编号，姓名，密码)
Teacher::Teacher(int empId, string name, string pwd)
{
	//初始化属性
	this->m_EmpId = empId;
	this->m_Name = name;
	this->m_Pwd = pwd;
}
```

#### 9.1.2  教师子菜单

- 在机房预约系统.cpp中，当用户登录的是教师，添加教师菜单接口
- 将不同的分支提供出来
  - 查看所有预约
  - 审核预约
  - 注销登录
- 实现注销功能

添加全局函数 `void TeacherMenu(Person * &manager)` 代码如下：

```c++
//教师菜单
void TeacherMenu(Identity * &teacher)
{
	while (true)
	{
		//教师菜单
		teacher->operMenu();

		Teacher* tea = (Teacher*)teacher;
		int select = 0;

		cin >> select;

		if (select == 1)
		{
			//查看所有预约
			tea->showAllOrder();
		}
		else if (select == 2)
		{
			//审核预约
			tea->validOrder();
		}
		else
		{
			delete teacher;
			cout << "注销成功" << endl;
			system("pause");
			system("cls");
			return;
		}

	}
}
```



#### 9.1.3 菜单功能实现

- 在实现成员函数`void Teacher::operMenu()` 代码如下：

```c++
//教师菜单界面
void Teacher::operMenu()
{
	cout << "欢迎教师：" << this->m_Name << "登录！" << endl;
	cout << "\t\t ----------------------------------\n";
	cout << "\t\t|                                  |\n";
	cout << "\t\t|          1.查看所有预约          |\n";
	cout << "\t\t|                                  |\n";
	cout << "\t\t|          2.审核预约              |\n";
	cout << "\t\t|                                  |\n";
	cout << "\t\t|          0.注销登录              |\n";
	cout << "\t\t|                                  |\n";
	cout << "\t\t ----------------------------------\n";
	cout << "请选择您的操作： " << endl;
}
```



#### 9.1.4 接口对接

- 教师成功登录后，调用教师的子菜单界面
- 在教师登录分支中，添加代码：

```c++
				//进入教师子菜单
				TeacherMenu(person);
```

添加效果如图：

![1548670866708](assets/1548670866708.png)

测试对接，效果如图：

登录验证通过：

![1548670949885](assets/1548670949885.png)

教师子菜单：

![1548670958602](assets/1548670958602.png)

注销登录：

![1548670966988](assets/1548670966988.png)









### 9.2 查看所有预约

#### 9.2.1 所有预约功能实现

该功能与学生身份的查看所有预约功能相似，用于显示所有预约记录

在Teacher.cpp中实现成员函数 `void Teacher::showAllOrder()`

```C++
void Teacher::showAllOrder()
{
	OrderFile of;
	if (of.m_Size == 0)
	{
		cout << "无预约记录" << endl;
		system("pause");
		system("cls");
		return;
	}
	for (int i = 0; i < of.m_Size; i++)
	{
		cout << i + 1 << "、 ";

		cout << "预约日期： 周" << of.m_orderData[i]["date"];
		cout << " 时段：" << (of.m_orderData[i]["interval"] == "1" ? "上午" : "下午");
		cout << " 学号：" << of.m_orderData[i]["stuId"];
		cout << " 姓名：" << of.m_orderData[i]["stuName"];
		cout << " 机房：" << of.m_orderData[i]["roomId"];
		string status = " 状态： ";  // 0 取消的预约   1 审核中   2 已预约 -1 预约失败
		if (of.m_orderData[i]["status"] == "1")
		{
			status += "审核中";
		}
		else if (of.m_orderData[i]["status"] == "2")
		{
			status += "预约成功";
		}
		else if (of.m_orderData[i]["status"] == "-1")
		{
			status += "审核未通过，预约失败";
		}
		else
		{
			status += "预约已取消";
		}
		cout << status << endl;
	}

	system("pause");
	system("cls");
}
```



#### 9.2.2 测试功能

运行测试教师身份的查看所有预约功能

测试效果如图：

![1548676922678](assets/1548676922678.png)





### 9.3 审核预约

#### 9.3.1 审核功能实现

功能描述：教师审核学生的预约，依据实际情况审核预约

在Teacher.cpp中实现成员函数 `void Teacher::validOrder()`

代码如下：

```C++
//审核预约
void Teacher::validOrder()
{
	OrderFile of;
	if (of.m_Size == 0)
	{
		cout << "无预约记录" << endl;
		system("pause");
		system("cls");
		return;
	}
	cout << "待审核的预约记录如下：" << endl;

	vector<int>v;
	int index = 0;
	for (int i = 0; i < of.m_Size; i++)
	{
		if (of.m_orderData[i]["status"] == "1")
		{
			v.push_back(i);
			cout << ++index << "、 ";
			cout << "预约日期： 周" << of.m_orderData[i]["date"];
			cout << " 时段：" << (of.m_orderData[i]["interval"] == "1" ? "上午" : "下午");
			cout << " 机房：" << of.m_orderData[i]["roomId"];
			string status = " 状态： ";  // 0取消的预约   1 审核中   2 已预约  -1 预约失败
			if (of.m_orderData[i]["status"] == "1")
			{
				status += "审核中";
			}
			cout << status << endl;
		}
	}
	cout << "请输入审核的预约记录,0代表返回" << endl;
	int select = 0;
	int ret = 0;
	while (true)
	{
		cin >> select;
		if (select >= 0 && select <= v.size())
		{
			if (select == 0)
			{
				break;
			}
			else
			{
				cout << "请输入审核结果" << endl;
				cout << "1、通过" << endl;
				cout << "2、不通过" << endl;
				cin >> ret;

				if (ret == 1)
				{
					of.m_orderData[v[select - 1]]["status"] = "2";
				}
				else
				{
					of.m_orderData[v[select - 1]]["status"] = "-1";
				}
				of.updateOrder();
				cout << "审核完毕！" << endl;
				break;
			}
		}
		cout << "输入有误，请重新输入" << endl;
	}

	system("pause");
	system("cls");
}
```

#### 9.3.2 测试审核预约

测试 - 审核通过

![1548677286679](assets/1548677286679.png)

审核通过情况

![1548677383681](assets/1548677383681.png)

测试-审核未通过

![1548677402705](assets/1548677402705.png)

审核未通过情况：

![1548677632792](assets/1548677632792.png)

学生身份下查看记录：

![1548677798815](assets/1548677798815.png)

审核预约成功！

# 机房预约系统代码审查与重构计划

## 1. 项目与审查范围

- 审查人：jingquan
- 审查日期：2026-10-30
- 原始仓库：https://github.com/Guoyanzeng/Computer-room-reservation-system
- 审查基线：b04e5a1eff7c0d19805008d224638101b62c2668
- 审查范围：登录、角色菜单、账号管理、机房信息、预约申请、查询、取消、审核及文件持久化。

本文记录静态代码审查结论和重构实施计划。目前不将计划中的修改记为已完成，VS 生成、功能验证和 Git 提交结果均按实际操作补充。

## 2. 开发环境与运行方法

1. 操作系统：Windows。
2. 开发工具：Visual Studio 2022。
3. 安装“使用 C++ 的桌面开发”及 Windows SDK。
4. 打开“机房预约系统.sln”。
5. 原工程使用 v142 工具集，已安装时可以保留；也可以明确重定向为本机已安装的 v143。
6. 选择 Debug / x64，在项目属性中选择已安装的 Windows SDK。
7. 将“配置属性 → 调试 → 工作目录”设置为 `$(ProjectDir)`。
8. 确保项目目录中存在以下数据文件：
   - admin.txt
   - student.txt
   - teacher.txt
   - computerRoom.txt
   - order.txt
9. 按 Ctrl+Shift+B 生成解决方案，成功后按 Ctrl+F5 启动。
10. 原始演示数据的管理员账号为 admin，密码为 123，仅用于本地作业验证。

原始 C++ 源文件主要采用 GBK/代码页936。编码转换应同时处理源文件、编译选项、控制台和数据文件，避免只添加 `/utf-8`。

## 3. 审查依据与严重程度

题目未提供具体企业编码规范，因此本次采用以下资料及通用工程约定作为参考，不虚构企业规范条款：

- C++ Core Guidelines。
- OWASP 密码存储与敏感信息处理实践。
- 输入校验、文件错误处理、资源管理、单一职责及重复代码治理等工程约定。

| 严重程度 | 本次定义 | 数量 |
|---|---|---:|
| 致命 | 可能导致未定义行为、修改错误记录或破坏关键数据 | 4 |
| 严重 | 影响安全、健壮性、持久化可靠性或核心结构维护 | 8 |
| 建议 | 重复、耦合、封装与规范问题，建议逐步改进 | 7 |

以下问题按严重程度排序。代码位置均对应上述原始审查基线，修改后应重新核对行号。

正确性修复、安全改造与结构重构分别记录，避免将修正错误行为或修改数据格式描述为完全不改变行为的重构。

## 4. 问题清单及修改方案

### 4.1 致命问题

| 编号 | 问题及位置 | 影响 | 修改手法与目标 |
|---|---|---|---|
| R01 | 预约数量未初始化。orderFile.h:22；OrderFile::OrderFile | m_Size 未初始化便用于索引和自增，读取未初始化整数属于未定义行为，可能引发错误查询和保存。 | 初始化成员，先改为 `int m_Size = 0`。后续使用 `vector<Order>` 保存记录，移除独立计数，统一通过 `size()` 获取数量。 |
| R02 | 基类缺少虚析构。Identity.h；systemclt.cpp 各注销分支 | 通过 Identity* 删除派生对象，但 Identity 没有虚析构，属于未定义行为。 | 添加 `virtual ~Identity() = default`。后续使用 `std::unique_ptr<Identity>` 管理会话对象，移除手动 delete。 |
| R03 | 教师审核序号错位。teacher.cpp:78—112 | 映射键从0开始，界面序号从1开始，却直接用输入值查询映射，可能审核错误记录；缺失键还会被 map[] 插入为默认值。 | 用候选记录索引列表替换临时映射。验证输入范围后，通过 `select - 1` 获取记录，更新前再次确认待审核状态；审核结果仅接受1或2。 |
| R04 | 取消预约范围错误。student.cpp:183—215 | 实际候选数为 index-1，代码却允许输入 index。缺失键默认映射到记录0，可能修改错误记录，甚至影响其他学生。 | 用候选列表统一选择逻辑。无候选时返回，只接受合法序号或0返回；更新前再次校验预约归属和可取消状态。 |

### 4.2 严重问题

| 编号 | 问题及位置 | 影响 | 修改手法与目标 |
|---|---|---|---|
| R05 | 清空预约确认不严格。manager.cpp:148—159 | 代码仅排除输入1，输入3、负数等其他值也会清空文件。 | 使用正向确认和卫语句，仅明确输入2才清空；1返回，其他输入重新提示。执行成功后才报告清空成功。 |
| R06 | 输入失败未处理。主菜单、登录及各角色输入循环 | 输入字母后 cin 进入失败状态，后续读取可能持续失败；EOF 未处理。 | 提取统一输入函数，使用 getline 读取整行并严格解析整数，集中处理空输入、非法字符、数值范围和 EOF。 |
| R07 | 未检查保存结果就报告成功。Student::ApplyOrder、Manager::AddPerson、OrderFile::UpdateOrder | 打开或写入失败时，程序仍可能提示成功，导致界面状态与实际数据不一致。 | 持久化接口返回明确结果，检查打开、写入、刷新和关闭状态，确认保存成功后再显示成功信息。 |
| R08 | 直接截断原文件后重写。orderFile.cpp:75—90 | 写入中断或程序异常可能导致原预约文件为空或只保存部分记录。 | 先在同目录写临时文件，确认写入和关闭成功后，再使用经过验证的 Windows 文件替换机制更新目标；失败时保留原文件或可恢复备份。 |
| R09 | 密码明文存储。Identity.h、systemclt.cpp、manager.cpp 及账号文本文件 | 读取账号文件即可获得密码，身份对象还长期保存明文密码。 | 提取认证服务，使用成熟库提供的 Argon2id 等专用密码哈希方案和独立随机盐；设计旧数据迁移、重置与回滚流程，不使用 std::hash 代替密码哈希。 |
| R10 | 查询账号时显示密码。manager.cpp:103—108 | 密码可能泄露到屏幕、截图和终端记录。 | 删除密码输出，账号列表仅显示编号、姓名等必要字段；调试信息和日志同样禁止输出密码。 |
| R11 | 使用嵌套字符串 map 表达预约。orderFile.h:18 及学生、教师预约操作 | 字段拼写错误难以在编译期发现，map[] 会插入空值，atoi 不能明确报告非法数字。 | 用 Order 结构和 OrderStatus、TimeSlot 枚举替换字符串数据团，集中解析、校验和序列化，保留旧文本格式兼容能力。 |
| R12 | 角色类职责过多。student.cpp、teacher.cpp、manager.cpp | 同一函数混合界面、输入、业务规则和文件访问，修改牵连范围大，难以独立验证。 | 提取控制台交互层、业务服务层和数据仓储层。先提供兼容接口，再逐个调用点迁移。 |

### 4.3 建议问题

| 编号 | 问题及位置 | 影响 | 重构手法与目标 |
|---|---|---|---|
| R13 | 预约展示代码重复。Student::ShowMyOrder、ShowAllOrder；Teacher::ShowAllOrder | 日期、时段、机房和状态展示重复，修改时容易遗漏。 | 提取 StatusText 和预约展示函数，按场景控制学号、姓名等字段，筛选逻辑与展示逻辑分离。 |
| R14 | 机房读取代码重复。学生和管理员的 initComputerRoom | 相同文件存在多套解析和错误处理逻辑。 | 提取 ComputerRoomRepository::Load，统一解析和校验；加载结果替换旧集合，避免重复初始化累积数据。 |
| R15 | 整数角色标识与向下转型耦合。SystemCtl::LoginIn 及各角色菜单 | 菜单接收基类指针后再转回派生类，存在错误类型传入和转换失败风险。 | 使用 Role 枚举，菜单接收具体类型引用或统一会话接口，减少不必要的向下转型。 |
| R16 | 数据成员公开。Identity.h、student.h、manager.h、orderFile.h | 外部可以绕过规则修改身份和预约数据，使集合与计数不一致。 | 先提供访问接口，再逐步将成员私有化；查询提供只读访问，状态变化通过受控业务方法完成。 |
| R17 | 头文件污染命名空间并依赖间接包含。多个头文件 | using namespace std 影响所有包含者，部分类型声明依赖其他头文件间接引入。 | 在头文件使用 std:: 限定名称，直接包含自身所需头文件，并统一 identity.h 与实际 Identity.h 的大小写。 |
| R18 | 机房编号写死为1至3。student.cpp:72—79 | 界面按文件展示机房，但输入校验使用固定范围，数据变化后可能不一致。 | 根据实际机房集合查找编号，允许非连续编号；无可用机房时提示并返回。 |
| R19 | 暂停和清屏调用分散。多个 cpp 文件 | system("pause")、system("cls") 与业务混合，平台依赖分散，不利于验证。 | 提取统一控制台接口，业务服务不直接暂停或清屏，验证时可替换交互实现。 |

## 5. 总体重构思路

目标结构：

```text
控制台交互层
负责菜单、输入、结果展示
        ↓
业务服务层
负责认证、账号管理、预约申请、取消、审核及状态规则
        ↓
数据仓储层
负责账号、机房和预约的加载、校验、保存及错误返回

领域模型：
User、Order、ComputerRoom、Role、OrderStatus、TimeSlot
```

迁移原则：

1. 先修复未定义行为和错误更新，再调整结构。
2. 每次只修改一组相关内容，避免同时重写全部角色。
3. 新增模型或服务时保留兼容适配，逐个调用点迁移后再删除旧实现。
4. 封装成员前先提供访问接口，避免一次性造成大量编译错误。
5. 预约模型调整时先保留现有文本格式兼容能力。
6. 密码格式迁移前备份数据，确认新格式可用后再切换。
7. 新增依赖和源文件后同步更新 VS 工程配置。

业务边界：

- 学生只能取消本人待审核或预约成功的记录。
- 教师只能审核待审核记录。
- 清空预约必须明确确认。
- 保存失败不得提示成功。
- 合法机房编号以实际加载的数据为准。
- 新增时段冲突或容量限制前，先明确需求，不将新增业务规则混入纯结构重构。

## 6. 分步实施计划与 commit message

以下均为计划，不代表已经完成相应修改或产生相应提交。

| 步骤 | 内容 | 对应问题 | 计划 commit message | 本步验证 |
|---|---|---|---|---|
| S00 | 记录环境、原始版本与审查计划 | 全部 | docs: document build baseline and code review plan | 记录实际 VS、工具集、SDK 和运行结果 |
| S01 | 初始化成员并补充虚析构 | R01、R02 | fix: initialize model state and add virtual destructor | 空文件、多条记录读取，三角色登录注销 |
| S02 | 修复审核和取消预约的序号映射 | R03、R04 | fix: correct reservation selection mapping | 首项、末项、越界、无候选及他人记录 |
| S03 | 统一输入处理并修复清空确认 | R05、R06 | fix: validate input and reservation clearing confirmation | 非法字符、空行、边界、EOF 和清空确认 |
| S04 | 完善文件操作错误检查 | R07 | fix: report persistence failures accurately | 写入失败不误报成功，保存后重读一致 |
| S05 | 实现可恢复的覆盖保存 | R08 | fix: preserve reservation data on save failure | 临时文件写入和替换失败时原数据可恢复 |
| S06 | 删除密码展示 | R10 | security: remove password disclosure from account views | 学生和教师账号列表不显示密码 |
| S07 | 引入强类型预约模型 | R11、R16 | refactor: introduce typed reservation model | 旧数据兼容、字段校验和往返转换 |
| S08 | 拆分业务服务和数据仓储 | R12、R14、R16、R18 | refactor: extract services and repositories | 三角色核心流程、非连续机房编号、重复加载 |
| S09 | 统一会话所有权和角色接口 | R02、R15 | refactor: manage sessions with explicit types and ownership | 三角色反复登录注销，移除手动释放 |
| S10 | 合并展示逻辑并整理头文件 | R13、R17、R19 | refactor: consolidate presentation and header dependencies | 四种状态展示、控制台交互及头文件自包含 |
| S11 | 迁移密码安全存储 | R09 | security: migrate credentials to password hashes | 旧账号迁移、新账号登录、错误密码拒绝 |
| S12 | 完成回归验证和交付文档 | 全部 | docs: record regression results and review deliverables | Debug/Release x64 生成和完整业务验证 |

S07、S08 等较大步骤应按类或调用点继续拆分，每个子提交都保持可编译、可运行。

每次提交遵循：

```text
小范围修改
→ VS 生成
→ 本步相关验证
→ 检查 git diff
→ git add 指定文件
→ git commit
```

如果生成或验证失败，先修复或回退本步，不将失败状态作为阶段成果提交。完成结构调整的步骤应保持此前已通过的功能继续通过。

## 7. 验证用例与验收标准

所有破坏性测试在数据副本上执行。运行前备份账号、机房及预约文件。

| 用例 | 操作与预期 | 实际结果 |
|---|---|---|
| T01 生成与启动 | Debug/Release x64 均可生成，程序显示主菜单并正常退出 | 待验证 |
| T02 身份与账号 | 三角色正确登录，错误密码拒绝，重复编号拒绝，反复注销正常 | 待验证 |
| T03 申请与查询 | 新申请保存后重新读取可见，本人查询只返回本人预约 | 待验证 |
| T04 教师审核 | 至少两条候选，首项和末项选择准确，已处理记录不能再次审核 | 待验证 |
| T05 学生取消 | 只修改本人可取消记录，无候选、越界及返回不改变数据 | 待验证 |
| T06 输入边界 | 字母、空行、12abc、超大数、越界值和 EOF 可恢复或正常返回 | 待验证 |
| T07 清空确认 | 只有明确确认才清空，其他输入不改变数据 | 待验证 |
| T08 文件异常 | 文件缺失、格式错误和写入失败有明确提示，覆盖失败可恢复原数据 | 待验证 |
| T09 机房数据 | 非连续编号按真实集合校验，重复加载不累加，空集合可返回 | 待验证 |
| T10 安全与兼容 | 不输出密码，迁移后账号按策略可用，旧预约文件兼容 | 待验证 |

生成成功只证明编译和链接通过，主菜单可见只证明启动成功。完整验收需要继续通过相关业务验证。

## 8. Excel 审查表与证据管理

审查表文件：jingquan.xlsx。

前七列保留参考格式：

1. 时间
2. 提出人/审查人
3. 问题分类
4. 问题描述
5. 截图1
6. 截图2
7. 解决办法

右侧补充严重程度、问题编号、文件与函数及原始行号、审查依据、验证方法、处理状态、计划步骤和实际修复 commit。

记录规则：

- 全部19项问题当前状态为“待处理”。
- 截图1留空，后续填写原始问题代码证据。
- 截图2留空，后续填写修复或验证证据。
- 实际修复 commit 留空，完成提交后填写真实提交号。
- 完成修改后更新为“已修复待验证”，验证通过后更新为“已验证”。
- 计划中的 commit message 不能作为实际修复完成的证据。

VS 生成、程序运行和 Git 上传结果均待实际操作确认。

提交内容包括源码、工程配置、README 和 Excel 审查表。不提交 .vs、obj、pdb 等生成文件。

## 9. 参考资料

- C++ Core Guidelines：
  https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines

- OWASP Password Storage Cheat Sheet：
  https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html

- OWASP Logging Cheat Sheet：
  https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html


至此本案例制作完毕！  `^_^`



