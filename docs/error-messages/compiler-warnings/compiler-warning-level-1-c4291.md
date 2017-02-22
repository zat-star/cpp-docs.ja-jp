---
title: "コンパイラの警告 (レベル 1) C4291 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4291"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4291"
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4291
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'宣言' : 初期化コードが例外をスローすると、'new' 演算子を使用しているとメモリを解放しません。  
  
 仮引数付きの [new](../../cpp/new-operator-cpp.md) が使用されていますが、該当する仮引数付きの [delete](../../cpp/delete-operator-cpp.md) がありません。  
  
 **new** 演算子でオブジェクトにメモリを割り当てると、そのオブジェクトのコンストラクターが呼び出されます。  コンストラクターが例外をスローした場合は、オブジェクトに割り当てられていたメモリを解放する必要があります。  **new** 演算子と一致する **operator delete** 関数がない場合、メモリの解放は行われません。  
  
 余分な引数を付けずに **new** 演算子を使用し、[\/GX](../Topic/-GX%20\(Enable%20Exception%20Handling\).md)、[\/EHs](../../build/reference/eh-exception-handling-model.md)、または \/EHa の各オプションでコンパイルして例外処理を有効にすると、コンストラクターが例外をスローしたときに **delete** 演算子を呼び出すコードが生成されます。  
  
 仮引数付きの **new** 演算子、つまり割り当てサイズ以外の引数を伴う形式の **new** 演算子を使用すると、コンストラクターが例外をスローしたときにも、**delete** 演算子を呼び出すコードは生成されます。ただし、これは、メモリを割り当てた仮引数付きの **new** 演算子と一致する仮引数付きの **delete** 演算子がある場合だけです。  たとえば、次のようになります。  
  
```  
// C4291.cpp  
// compile with: /EHsc /W1  
#include <malloc.h>  
  
class CList  
{  
public:  
   CList(int)  
   {  
      throw "Fail!";  
   }  
};  
  
void* operator new(size_t size, char* pszFilename, int nLine)  
{  
   return malloc(size);  
}  
  
int main(void)  
{  
   try  
   {  
      // This will call ::operator new(unsigned int) to allocate heap  
      // memory. Heap memory pointed to by pList1 will automatically be  
      // deallocated by a call to ::operator delete(void*) when  
      // CList::CList(int) throws an exception.  
      CList* pList1 = new CList(10);  
   }  
   catch (...)  
   {  
   }  
  
   try  
   {  
      // This will call the overloaded ::operator new(size_t, char*, int)  
      // to allocate heap memory. When CList::CList(int) throws an  
      // exception, ::operator delete(void*, char*, int) should be called  
      // to deallocate the memory pointed to by pList2. Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291  
   }  
   catch (...)  
   {  
   }  
}  
```  
  
 上の例では、仮引数付きの **new** 演算子と一致する仮引数付きの **delete** 演算子が定義されていないため、警告 C4291 が生成されます。  この問題を解決するには、**main** の前に次のコードを挿入します。  オーバーロードされた **operator delete** 関数のパラメーターは、最初のパラメーターを除き、すべてオーバーロードされた **new** 演算子と一致することに注意してください。  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```