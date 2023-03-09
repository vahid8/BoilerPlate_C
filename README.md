# BoilerPlate_C-plus-plus
## Running Cmake inside terminal ubuntu
you need to have the cmake list inside folder   
```
mkdir build
cd build
cmake ..
make
```
## VSCODE LINUX  
(https://code.visualstudio.com/docs/cpp/cmake-linux)  
1- Make sure Cmakee and a compiler is installed (gcc or g++)  
2- install c++ and CMAKE tool extension  
3- inside the folder containing main.cpp open Terminal and type the following (it will open vscode with the current folder)
```
code .
```
4- cmkae: select variant: Debug to do the deveoopement 
5- use F5 to run and use breakpoints to pause 

### Size of variables
| Type      | size in (Bytes (8 bit) |
| ------------- |:-------------:|
| sizeof(char) | 1 |
| sizeof(short) | 2 |
| sizeof(int) | 4 |
| sizeof(double) | 8 |
| sizeof(unsigned int) | 4 |
| sizeof(bool) | 1 |
| sizeof(float) | 4 |


### Important keywords
| Method    | Example | Description  | 
| ------------- |-------------|-------------|
| #define | #define print(value){std::cout << value << std::endl;} | define print() for all project |
| static | static int s_variable = 2; or static void func(){}| * |
| struct | a type of class that is public | if you use static for defining vars , they are not members of struct anymore |


*if you define a variable and function it will be global by default in all your files
 In the workspace and you can define it only once otherwise u will get a dupplicatation error
 How ever you can hide this variable or function from other cpp files using static keyword

** Use definitions and structs in Header files

### Struct
pulic class
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

struct Entity{
int x, y;
void print(){ std::cout << x<< ","<< y <<std::endl;}
};
// you can define variables after that as well
int Entity::z;
//or with initilizing the value
int Entity::z=2; 
// Use classes
int main(){
Entity e1;
e1.x = 4;
e1.y=5;
e1.z=7;
e1.print();
}
```

### Data Structures: 
#### Array (static array) 
Array will be stored in stack automatically
It has a fix size and you can not touch the size  
// standard Arrays from std (it has all methods such as size(), iterator, sort, ...)
```
std:: array<int,5> data;
data[0] = 2; access data;
Different methods of iterating over the  array or vector
```
// Normal c style array (not recommended)  
```
int dataOld[5];
dataOld[5]=1;
```

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


