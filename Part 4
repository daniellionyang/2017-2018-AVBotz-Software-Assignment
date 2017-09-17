#include <fstream>
#include <iostream>
using namespace std;
ifstream fin ("sum.in");
ofstream fout ("sum.out");
int r,c;
int Scatman[10000][10000];
int adj[10000][10000];

bool bound(int x, int y){return x>=0 && x<r && y>=0  && y<c;}

void IftheScatmancandoitsocanyou(){
    for(int i = 0; i < r; i++){
        for(int j = 0; j < c; j++){
            fin >> Scatman[i][j];
            adj[i][j]=1<<30;
        }
    }
    for(int x = 0; x<r; x++){
        for(int y = 0; y<c; y++){
            if(bound(x-1, y)) adj[y+c*x][y+c*(x-1)] = Scatman[x-1][y];
            if(bound(x+1, y))adj[y+c*x][y+c*(x+1)] = Scatman[x+1][y];
            if(bound(x, y+1))adj[y+c*x][y+1+c*x] = Scatman[x][y+1];
            if(bound(x, y-1))adj[y+c*x][y-1+c*x] = Scatman[x][y-1];
        }
    }
    
}

int dijakstra(){
    int dist[r*c];
    bool visited[r*c];
    for(int i = 0; i < r*c; i++)dist[i]=1<<30;
    memset(visited, 0, sizeof(visited));
    dist[0] = 0;
    for (int i = 0; i < r*c; i++){
        int index = -1;
        int minimum = 1<<30;
        for(int j = 0; j < r*c; j++){
            if(visited[j]==0&&dist[j]<minimum){
                minimum=dist[j];
                index = j;
            }
        }
        visited[index] = 1;
        int k =index+1;
        if (visited[k]==0&&(k-1)%c!=c-1) dist[k]=dist[index]+adj[index][k] < dist[k]?dist[index]+adj[index][k] :dist[k];
        k =index-1;
        if (visited[k]==0&&(k+1)%c!=0) dist[k]=dist[index]+adj[index][k] < dist[k]?dist[index]+adj[index][k] :dist[k];
        k =index+c;
        if (visited[k]==0&&k<r*c) dist[k]=dist[index]+adj[index][k] < dist[k]?dist[index]+adj[index][k] :dist[k];
        k =index-c;
        if (visited[k]==0&&k>=0) dist[k]=dist[index]+adj[index][k] < dist[k]?dist[index]+adj[index][k] :dist[k];
    }
    return dist[r*c-1]+Scatman[0][0];
}


int main(){
    fin >> r >> c;
    IftheScatmancandoitsocanyou();
    fout << dijakstra()<<endl;
}
