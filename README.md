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