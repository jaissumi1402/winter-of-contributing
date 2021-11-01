## **Basic problems on stack**
## 1.Implement a stack using two queues.

code in c++

```c++
#include <iostream>
#include <queue>
#include <vector>
#include <cstdlib>
using namespace std;
 
// Implement stack using two queues
class Stack
{
    queue<int> q1, q2;
 
public:
    // Insert an item into the stack
    void push(int data)
    {
        // Move all elements from the first queue to the second queue
        while (!q1.empty())
        {
            q2.push(q1.front());
            q1.pop();
        }
 
        // Push the given item into the first queue
        q1.push(data);
 
        // Move all elements back to the first queue from the second queue
        while (!q2.empty())
        {
            q1.push(q2.front());
            q2.pop();
        }
    }
 
    // Remove the top item from the stack
    int pop()
    {
        // if the first queue is empty
        if (q1.empty())
        {
            cout << "Underflow!!";
            exit(0);
        }
 
        // return the front item from the first queue
        int front = q1.front();
        q1.pop();
 
        return front;
    }
};
 
int main()
{
    vector<int> keys = { 1, 2, 3, 4, 5 };
 
    // insert the above keys into the stack
    Stack s;
    for (int key: keys) {
        s.push(key);
    }
 
    for (int i = 0; i <= keys.size(); i++) {
        cout << s.pop() << endl;
    }
 
    return 0;
}
```
Output
```
5
4
3
2
1
Underflow!!
```
Time complexity of above code is O(n)

## 2.Write a program to delete all the vowels from a string.

code in c++
```c++
#include<iostream>
using namespace std;
int main()
{
        string a;
        cout<<"Enter String : ";
        cin>>a;
        for(int i=0;i<a.length(); i++)
        {
                if (a[i]=='a' || a[i]=='e' || a[i]=='i' || a[i]=='o' || a[i]=='u' || a[i]=='A' || a[i]=='E' || a[i]=='I'
|| a[i]=='O' || a[i]=='U')
                {
                        a[i]=' ';
                }
        }
        cout<<"New string is: "<<a<<endl;
        return 0;
}
```
Output
```
Enter String : Hello
New string is: H ll
```
Time complexity of above code is O(n)

## 3. Write a program to reverse a string.
code in c++
```c++
#include <iostream>
#include <string>
using namespace std;
string reverse(string x){
        string b;                              //initializing a new string
        b=x;                                   //storing all character of given string into temporary string
        int index=0;
        for(int i=b.length()-1;i>=0;i--){
             x[index]=b[i];                    //now storing all characters from temporary string into given string in reverse manner
            index++;
        }
        return x;
}
int main() 
{
        string a;
        cout<<"Enter String : ";
        cin>>a;
        cout<<"reversed string is: "<<reverse(a);
        
  }
```
Time complexity of above code is O(n)
## HAPPY LEARNING 🙌✨

### REFERENCES

For preparing this document some refrences were taken for maintaining the authenticity of the code and also for making the topics more informative
The links of blog that were reffered -:


 - [w3resource](https://www.w3resource.com/cpp-exercises/string/index.php)
 - [codesdope](https://www.codesdope.com/practice/cpp-string/)
