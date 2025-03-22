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

用c++代码将上面的图进行存储，代码如下：
____________________________________________________________________
#include <bits/stdc++.h>
using namespace std;

int mat[10][10]={0};


//邻接矩阵
void create_Amat(int (&mat)[10][10], int begin, int end){
    mat[end][begin]=1;
}


//输出邻接矩阵
void show_Amat(int (&mat)[10][10]){
    for (int i=0; i<10; i++){
        for (int j=0; j<10; j++){
            cout<<mat[i][j]<<" ";
        }
        cout<<endl;
    }
}


int main(){


    int n; cin>>n;//输入要存入的边数
    int begin, end;
    for (int i=0; i<n; i++){
        cin>>begin>>end;//遍历边（的起点和终点）
        create_Amat(mat, begin, end);
    }

    show_Amat(mat);

}
____________________________________________________________________________
