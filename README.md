# BoilerPlate_C-

## VSCODE LINUX  
(https://code.visualstudio.com/docs/cpp/cmake-linux)  
1- Make sure CMAke and a compiler is installed (gcc or g++)  
2- install c++ and CMAKE tool extension  
3- inside the folder containing main.cpp open Terminal and type the following (it will open vscode with the current folder)
```
code .
```
4- cmkae: select variant: Debug to do the deveoopement 
5- use F5 to run and use breakpoints to pause 

### Important keywords
| Method    | Example | Description  | 
| ------------- |-------------|-------------|
| #define | #define print(value){std::cout << value << std::endl;} | define print() for all project |
| static | static int s_variable = 2; or static void func(){}| * |

*if you define a variable and function it will be global by default in all your files
 In the workspace and you can define it only once otherwise u will get a dupplicatation error
 How ever you can hide this variable or function from other cpp files using static keyword

### Define data structure and define what to print out
```
struct points{
    int x,y,z;
    //constructor
    points(int x,int y,int z):x(x),y(y),z(z){};
    //copy constructor
    points(const points& point):x(point.x),y(point.y),z(point.z)
    {
        std::cout<<"Copied!!"<< std::endl;
    }

};
//overwrite <<
std::ostream& operator<<(std::ostream& stream,const points& a){
    stream<<a.x<<","<<a.y<<","<<a.z;
    return stream;
}
```

### Data Structures: 
#### Array (static array) 
Array will be stored in stack automatically
It has a fix size and you can not touch the size  
```
// standard Arraya from std (it has all methods such as size(), iterator, sort, ...)
std:: array<int,5> data;
data[0] = 2; access data;
Different methods of iterating over the  array or vector
```
// Normal c style array (not recommended)
int dataOld[5];
dataOld[5]=1;

#### Vectors: sequence containers, representing arrays that can change in size 
Vectors are stored in Heap memory
 access in O(1)   
 The size can change dynamically 
 ```
 std::vector<int> arr; or vector<int> arr = {1,2,3,4};
 ```
 
###### STL methods for arrays and vectors:
1. Iterating
```
 for(int i=0;i<data.size();i++) {
    std::cout<<data[i]<<std::endl;
 }
 //Old way of printing -> using iterator
    for (std::vector<points>::iterator it = P.begin() ; it != P.end(); ++it)
        std::cout<<*it<<std::endl;
 //or    
   for (auto it = P.begin() ; it != P.end(); ++it)
        std::cout<<*it<<std::endl;
 // newest method
print("thirdt method of iterating and printing");
for (const points& i : P)
    std::cout<<i<<std::endl;
```
| Method      | Description         |
| ------------- |:-------------:|
| Data.clear() | clear the memmory but vector adrees is still there |
| Data.sort() | sort the vector |
| Data.size() | size of the vector |


