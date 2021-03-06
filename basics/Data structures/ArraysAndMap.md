# 数组

## 散列表

利用链表实现：$O(N)$

利用平衡二叉树实现: $O(lgN)$ (工程上利用红黑树实现)

### C++: Map


## ArrayList与可变长度数组

类似链表实现

### C++：Vector

尾部插入数字 `vec.push_back(a)`;

使用下标访问元素: `cout<<vec[0]<<endl`;记住下标是从0开始的。

使用迭代器访问元素.

```C++
vector<int>::iterator it;
for(it=vec.begin();it!=vec.end();it++)
cout<<*it<<endl;
```
插入元素 `vec.insert(vec.begin()+i,a);` 在第i+1个元素前面插入a;

删除元素 `vec.erase(vec.begin()+2)`; : 删除第3个元素

`vec.erase(vec.begin()+i,vec.end()+j);` 删除区间[i,j-1];区间从0开始

向量大小: `vec.size();`

清空:`vec.clear();`

使用二维的数组：
```C++
int out[3][2] = { 1, 2, 3, 4, 5, 6 }; 
vector <int*> v1; 

v1.push_back(out[0]); 
v1.push_back(out[1]); 
v1.push_back(out[2]); 

cout << v1[0][0] << endl;//1 
cout << v1[0][1] << endl;//2 
```

### Java：ArrayList


## 数组与指针


## 基础题

* 1. 不使用额外数据结构判断字符串有无重复字符
  * 需要询问的：是ASCII字符串(是否扩展即128还是256)还是Unicode字符串(每个字符2个字节16位) 
  * 如果允许修改数组：排序后遍历$O(nlgn)$，否则可以循环比较$O(n^2)$
* 2. 给定两个字符串判断其中一个字符串重排后能否形成另一个字符串
  * 需要询问的：除1中条件外，是否区分大小写，空白需要考虑吗
  * 排序后比较
  * 使用一个数组额外对应每个字符，存在于s1中+1，存在s2中-1，遍历两个字符串，为负数直接返回false。
* 3. 知道字符串的空格全部替换为`%20`, 这个字符串尾部有足够空间存放新字符且知道原始字符串的真实长度
  * 扫描两次，从后往前处理（利用index和i两个序号表示） 
* 4. 给定一个字符串，判断它是否是一个回文串的重新排列
  * 对字符出现次数计数，最多只有一个字符出现次数为奇数(仅发生在字符串长度为计数情况) 
  * 利用bit串进行，出现一次对对应位进行一次翻转，**判断仅有一位为1的位操作**：`mask&(mask-1)=0`
* 5. 给定两个字符串，判断能否只通过一次或0次(插入/删除/替换)操作来进行字符串转换
  *  先根据两者字符串长度判断采用插入，删除，还是替换
  *  替换：遍历寻找不同的字符是否只有一个，插入/删除：遍历记录第一个不同，看之后的是否一致，
  *  联想到：编辑距离（dp）
* 6. 将字符串压缩，如aabcccccaaa变为a2b1c5a3，假设字符串只包含大小写字母
  *  遍历并构造一个字符串记录，为优化采用**stringBuilder**
* 7. 给定一个 $N*N$ 的图像矩阵，每个像素4字节，不使用额外空间将其旋转90度
  * 从最外层依次向内交换 
* 8. 若一个矩阵某个元素为0，则将对应行列清零
  * 遍历记录要清零的行和列后清零 
* 9. 假设你可以使用**一次**isSubstring方法(检查某一字符串是否为另一字符串的子串)，现在给定两个字符串，判断s2是否由s1旋转得到，如cdeab可由abcde旋转得到