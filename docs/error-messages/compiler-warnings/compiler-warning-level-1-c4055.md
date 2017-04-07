---
---
# <a name="compiler-warning-level-1-c4055"></a>コンパイラの警告 (レベル 1) C4055  
  
'conversion' : 'type1' データ ポインターが 'type2' 関数ポインターへキャストされています  
  
**古い形式:**この警告は、Visual Studio 2017 およびそれ以降のバージョンによっては生成されません。

 データポインターが、誤って関数ポインターにキャストされています。 これは /Za ではレベル 1 の警告になり、/Ze ではレベル 4 の警告になります。  
  
 次の例では C4055 が生成されます。  
  
```C  
// C4055.c  
// compile with: /Za /W1 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
   return (PFUNC)pi;   // C4055  
}  
```  
  
 これは、/Ze ではレベル 4 の警告です。  
  
```C  
// C4055b.c  
// compile with: /W4 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
return (PFUNC)pi;   // C4055  
}  
```