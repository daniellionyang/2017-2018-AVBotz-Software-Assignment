#include <iostream>
#include <fstream>
using namespace std;
ifstream fin ("coins.in");
ofstream fout ("coins.out");

int main(){
    double x;
    fin >> x;
    x=(int)(x*100);
    int q,d,n,c;
    q=x/25;
    x-=q*25;
    d=x/10;
    x-=d*10;
    n=x/5;
    x-=n*5;
    c=x;
    fout << q+d+n+c << std::endl;
    return;
}
