# wenjian
Just another repository
student={"stuid":"001","stuname":"zhangsan","stusex":"male"}
college=[]
def menu():
   print('输入1添加学生')
   print('输入2删除学生')
   print('输入3修改学生')
   print('输入4查找学生')
   print('输入5打印学生')
   enterselect=eval(input("请输入你的选择:"))
   return  enterselect

def addstudent():
    stu_id=input("student ID")
    stu_name=input("student Name")
    stu_sex=input("student Sex")
    newstudent=student.copy()
    print(newstudent)
    newstudent["stuid"]=stu_id
    newstudent["stuname"]=stu_name
    newstudent["stusex"]=stu_sex
    college.append(newstudent)
    print(college)
   
def findstu():
    stu_id=input("请输入学生学号：")
    return findstudent(stu_id)
def findstudent(stu_id):
    for i in range(len(college)):
        if college[i]["stuid"]==stu_id:
            return i 
    return -1

def deletestudent():
    stu_index=findstu()
    if stu_index==-1:
        print("没有此学生,删除失败")
    else:
        print("删除成功!") 
def editstudent():
    stu_index=findstu()
    if stu_index==-1:
        print("该学生不存在")
    else:
        stu_id=input("请输入修改后的学号:")
        stu_name=input("请输入修改后的姓名:")
        stu_sex=input("请输入修改后的性别")
        newstudent=student.copy()
        newstudent["stuid"]=stu_id
        newstudent["stuname"]=stu_name
        newstudent["stusex"]=stu_sex
        college.append(newstudent)
        print(newstudent)
def printstudent(college):
   print("所有学生如下：")
   for i in range(0,len(college)):
       print("|{:6}|{:12}|{:6}".format(student["stuid"],student["stuname"],student["stusex"]))     
 
while True:
    i=menu()
    if i==1:
        addstudent()
    elif i==2:
        deletestudent()     
    elif i==3:
        editstudent()
    elif i==4:      
        findstu()
        print(college)
    elif i==5:      
        printstudent(college)
