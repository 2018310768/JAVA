# JAVA
学生选课
## 实验目的
初步了解分析系统需求，从学生选课角度了解系统中的实体及其关系，学会定义类中的属性以及方法；
掌握面向对象的类设计方法（属性、方法）；
掌握类的继承用法，通过构造方法实例化对象；
学会使用super()，用于实例化子类；
掌握使用对象根类的toString（）方法，应用在相关对象的信息输出中。
## 业务要求
说明：学校有“人员”，分为“教师”和“学生”，教师教授“课程”，学生选择“课程”。从简化系统考虑，每名教师仅教授一门课程，每门课程的授课教师也仅有一位，每名学生选仅选一门课程。
对象示例：	人员（编号、姓名、性别……）
教师（编号、姓名、性别、所授课程、……）
			学生（编号、姓名、性别、所选课程、……）
			课程（编号、课程名称、上课地点、时间、授课教师、……）
以上属性仅为示例，同学们可以自行扩展（黄色背景的文字，不能原篇出现在实验报告中，需要进一步明确所有的属性）。
## 实验要求
1.编写上述实体类以及测试主类（注意类之间继承关系的适用）
2.在测试主类中，实例化多个类实体，模拟学生选课操作、打印课程信息（信息包括：编号、课程名称、上课地点、时间、授课教师 等）；模拟学生退课操作，再打印课程信息。
## 流程图
![流程图](https://github.com/2018310768/JAVA/blob/main/004.JPG)
## 核心代码
定义父类的属性


	public People(String id,String name,String sex) {
		this.id=id;
		this.name=name;
		this.sex=sex;
	}
学生信息的属性


	public Students(String id, String name, String sex,Subject choicesub,String score) {
		super(id, name, sex);
		this.choicesub=choicesub;
		this.score=score;
		}
	public String toString() {
		return "学生信息：	学号："+id+" ，姓名： "+name+" ，性别："+sex+"；"+choicesub;
	}  
选课信息的属性


	public Subject(String num,String subname,String place,String time,Teacher teaname) {
		this.num=num;
		this.subname=subname;
		this.place=place;
		this.time=time;
		this.teaname=teaname;
	}
	public String toString() {
		return "\n"+"所选课程：	课程号："+num+" ，课程名称："+subname+" ，课程地点："+place+" ，课程时间："+time+"；"+teaname;
	}
授课教师的属性


	public Teacher(String id, String name, String sex,String teachsub) {
		super(id, name, sex);
		this.teachsub=teachsub;
	}
	public String toString() {
		return "\n"+"授课教师：	工号："+id+" ,姓名："+name+" ,性别："+sex;
	}
导入 java.util 包下的 Scanner 类


    import java.util.Scanner;
选择要操作的课程


		Scanner input=new Scanner(System.in);
		int i=input.nextInt();
		switch(i) {
		case 1:
			subject=subone;
			break;
		case 2:
			subject=subtwo;
			break;
		case 3:
			subject=subthree;
			break;
		case 4:
			subject=subfour;
			break;
		case 5:
			subject=subfive;
			break;
		default :
			System.out.println("没有开设该课程！");
		}
选择是否退课


		System.out.println("您的选课信息为：");
		Students stuone=new Students("2018310768", "付焦兴", "男",subject,"2");
		System.out.println(stuone);
		System.out.println("是否退课？（是：1  否：0）");
		Scanner input1=new Scanner(System.in);
		int j=input1.nextInt();
		if(j==1) {
			subject=null;
			Students stuone1=new Students("2018310768", "付焦兴", "男",subject,"2");
			System.out.println("退课成功！"+"\n"+" "+stuone1+"\n"+"选课、退课操作结束！");
		}
		else {
			System.out.println("选课、退课操作结束！");
		}
## 运行结果
![流程图](https://github.com/2018310768/JAVA/blob/main/001.JPG)
## 实验感想
这次实验让我对类的对象和方法的定义有了更深刻的理解，掌握了继承和super()的用法。
在写代码的时候经常会出现小细节的错误，这提醒了我在以后的学习中要更加认真仔细，对每一行代码都要认真的阅读，进行检查和完善。
