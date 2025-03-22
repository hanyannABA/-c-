## 邻接矩阵
邻接矩阵通过记录顶点之间相邻关系存图

比如：


![屏幕截图 2025-03-22 112758](https://github.com/user-attachments/assets/4d48dfc3-dc46-4067-8d78-c956011c8eb8)


上面的图是一个有向图，这种图就能很好的用邻接矩阵存储。


我们先创建一个 5X5 的邻接矩阵：

![image](https://github.com/user-attachments/assets/64796145-bec5-4d8d-b25d-4f9744bfa779)


由于有向图的每条边具有起点和终点，而对应的邻接矩阵则可以很好的记录下来，比如：
    对于 1--->5 的边，我们用邻接矩阵对应的列和行（即第一列和第五行记录这条边）
![image](https://github.com/user-attachments/assets/af8649a2-89af-4f88-9db3-7cd436463006)


在这个邻接矩阵中：行表示一条边指向的点，列表示这条边的另一边的点。由于我给的无向图没有边权，因此默认这条边对应的矩阵中[5][1]的点为1
而未连通的的两个点i,j对应的矩阵中[i][j](或者[j][i])值则为初始值0

接下来我们一次对有向图中所有的边遍历一遍，就能得到如下矩阵：

![image](https://github.com/user-attachments/assets/f9443d5b-5d1a-48f3-a10f-621c809416a2)
_________________________________________________________________________________

用c++代码将上面的图进行存储，代码存储在：
https://github.com/hanyannABA/-c-/blob/%E5%9B%BE%E7%9A%84%E5%82%A8%E5%AD%98/%E9%82%BB%E6%8E%A5%E7%9F%A9%E9%98%B5
_________________________________________________________________________________


### 如果是无向图呢？
我们可以将无向图中所有的两点之间的边看作双向的有向图，
举个栗子：
![image](https://github.com/user-attachments/assets/5e075be5-1264-4923-bb67-4e4ca71f0f37)

这是一个无向图，我我们可以将任意一条线段都看作两个指向的箭头
若线段两端的点分别是1和4

![image](https://github.com/user-attachments/assets/428008e2-48b3-4647-b554-5906d5cbb7ca)

用邻接矩阵表示就是：

![image](https://github.com/user-attachments/assets/4b66c088-a781-4dea-9b1f-634669dd347b)

可以很容易看出，对于一个无向图，其对应的邻接矩阵一定是对称的

   
