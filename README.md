# dot-project
version 1

#include<iostream>
#include<chrono>
using namespace std;
using namespace std::chrono;
float comute(float a[],float b[],int n)
{
	  float result;
    for(int i=1;i<=n; i++) 
        result+=a[i]*b[i];
    return result;          
}
int main()
{   
    int i,n;
    float a[20001],b[20001];
    cout<<"plz enter number of elements in vector: "<<endl;    
    cin>>n;                                                                         //输入向量元素个数 
	  cout<<"enter vector a:(separate each element with a space)";                                                                       
	  for(i=1; i<=n; i++)                                                                //输入向量a 
        cin>>a[i];
    cout<<"enter vector b:"; 
    for(i=1; i<=n; i++)                                                                //输入向量b 
        cin>>b[i];
	  float *pa=new float [n];
    float *pb=new float [n];
	  auto start = system_clock::now();                                              //开始计时 
    float x=comute(a,b,n); 
	  auto end   = system_clock::now();                                              //结束计时 
    auto duration = duration_cast<microseconds>(end - start);
    cout << "time:"  << double(duration.count()) * microseconds::period::num / microseconds::period::den 
     << "μs" << endl;                                                                  //输出运行时间 
    cout<<x<<endl;
    delete [] pa;
    delete [] pb;
    return 0;
}
