#include <iostream>
#include <vector>
#include <fstream>
using namespace std;
ifstream fin ("coins2.in");
ofstream fout ("coins2.out");

int main (){
    int x;
    fin >> x;
    vector<int> w;
    int dp[1<<20];
    fill_n(dp, x+1, 1<<20);
    for(int i = 0; i < 4; i++){
        int k;
        fin >> k;
        w.push_back(k);
    }
    dp[x]=0;
    for(int k = x; k> 0; k--){
        for(int i =0; i < w.size(); i++){
            int c = 1;
            while(k-w[i]*c>=0){
                dp[k-w[i]*c]=min(dp[k]+c,dp[k-w[i]*c]);
                c++;
            }
        }
    }
    fout << dp[0]<<endl;
    return;
}
