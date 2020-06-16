It is an easy procedure to add OpenGL in CodeBlocks and prepare your Windows PC for OpenGL Coding.
By the way, those who are thinking OpenGL is a kind of Programming Language, you are wrong. OpenGL is a Graphics Library. It will give you scope to design graphical interfaces with a bunch of code.
Lets see, How to add it in CodeBlocks. 
I hope you have already installed CodeBlocks in your PC.

1. Download GLUT (OpenGL Utility Tool) from here.
2. Unzip the .zip file. There you will find 5 files:
glut32.dll\\
glut32.lib\\
glut.h\\
glut.def\\
README-win32.txt\\
Now you have to do some Copy-Paste works 🙂 .

3. Go to Windows > system in your System Drive. Usually its C:\Windows\system. Now copy the glut32.dll file there.
4. Go to C:\Program Files directory. Create a new folder and give it a suitable name. I named it “OpenGL Lib“.
5. Create 2 folders in C:\Program Files\OpenGL Lib called include & lib.
Copy glut32.lib in the lib folder.
Create a folder called GL in the include folder and copy glut.h in it.
You Are Almost Done 🙂
Now Open CODEBLOCKS. I am giving some Screenshots to help you.
6.  Create a New Project in CodeBlocks. It should be a Glut Project. Then Click Next.
![New Glut project](/assets/post_related/opengl/1.jpg)
![New Glut project](/assets/post_related/opengl/2.jpg)
7. Give a Name to your Project. I named it Test Project.
![New Glut project](/assets/post_related/opengl/3.jpg)
8. Select the Location of the Glut from Program Files Directory. Click Next.
![New Glut project](/assets/post_related/opengl/4.jpg)
9. Then this screen will appear. Don’t change anything here. Click Finish.
![New Glut project](/assets/post_related/opengl/5.jpg)
10. Open Management Bar (Shift + F2). Select Project tab. Open main.cpp. It is a sample code provided there.
![New Glut project](/assets/post_related/opengl/6.jpg)
11.  Write #include\<windows.h\> in Line 14. Go to Project> Build Options.
![New Glut project](/assets/post_related/opengl/7.jpg)
12. Go to Linker Settings tab and Click Add.
A Little Window will Appear saying “Keep this as relative path?”. Select No and press OK. 
![New Glut project](/assets/post_related/opengl/8.jpg)

13. Build the project and Run.
![New Glut project](/assets/post_related/opengl/9.jpg)

If you have done everything correctly you will see this.



 

That’s all.