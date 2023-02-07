# BoilerPlate_C-

## VSCODE LINUX  
(https://code.visualstudio.com/docs/cpp/cmake-linux)  
1- Make sure CMAke and a compiler is installed (gcc or g++)  
2- install c++ and CMAKE tool extension  
3- inside the folder containing main.cpp open Terminal 
```
code .
```
4- cmkae: select variant: Debug to do the deveoopement 
5- use F5 to run and use breakpoints to pause 

## Data Structures: 
#### Array (static array) 
Array will be stored in stack automatically
It has a fix size and you can not touch the size  
```
// standard Arraya from std (it has all methods such as size(), iterator, sort, ...)
std:: array<int,5> data;
data[0] = 2;

// Normal c style array (not recommended)
int dataOld[5];
dataOld[5]=1;
```
#### Vectors: sequence containers, representing arrays that can change in size 
 access in O(1)   
 The size can change dynamically 
 ```
 std::vector<int> arr; or vector<int> arr = {1,2,3,4};   
 arr.size();   
 
 ```
 

