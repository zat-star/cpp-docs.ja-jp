---
title: "コンパイラの警告 C4801 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4801"
ms.assetid: 05b29dff-15ef-42ca-9712-dc993afc4fd6
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 C4801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

参照渡しは検証可能ではありません: 理由  
  
 追跡参照をローカル変数に保存し、検証可能として返すことはできません。  
  
 作成時から戻り時までを通じて検証ツールが参照を追跡できる場合、および参照が配列の要素またはクラスのメンバーへの参照の場合にのみ、検証可能な参照として返すことができます。  
  
 詳細については、「[Peverify.exe \(PEVerify ツール\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md)」を参照してください。  
  
 検証可能にするためには、作成時から戻り時までを通じて参照をスタックに残す必要があります。  
  
 C4801 は、常にエラーとして表示されます。この警告は、`#pragma warning` または **\/wd** を使用してオフにできます。詳細については、「[warning](../../preprocessor/warning.md)」または「[\/w、\/Wn、\/WX、\/Wall、\/wln、\/wdn、\/wen、\/won \(警告レベル\)](../../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
## 使用例  
 検証ツールがアドレス トークンを確認できない場合、参照は検証不可能な参照と見なされるため、C4801 が生成されます。  次の例では C4801 エラーが生成されます。  
  
```  
// C4801.cpp  
// compile with: /clr:safe /c  
int% f(int% p) {  
   return p;   // C4801  
}  
```  
  
## 使用例  
 次の例では C4801 エラーが生成されます。  
  
```  
// C4801_b.cpp  
// compile with: /clr:safe /c  
  
int% f(int i, array<int>^ ar) {  
   int x;  
   int% bri = x;   // cannot return a byref to a local.  
   if (i < ar->Length) {  
      bri = ar[i];   // this byref is ok.  
   }  
  
   return bri;   // C4801 not returned within the basic block  
}  
```  
  
## 使用例  
 逆参照を実行して参照値を try ブロックで返そうとする場合も C4801 が発生します。  この場合、try ブロックの終わりでスタックがクリアされ、スタックのすべての戻り値が破棄されるため、結果的にコードは検証できなくなります。  代わりに、例外がスローされないようにするには、参照型を逆参照して変数に割り当てます。  次に、関数の終わりで参照型をもう一度逆参照して返します。  
  
 次の例では C4801 エラーが生成されます。  
  
```  
// C4801_c.cpp  
// compile with: /clr:safe  
using namespace System;  
  
ref class StackEmptyException : public System::Exception {};  
ref class StackFullException : public System::Exception {};  
  
template <typename T>  
ref struct Stack {  
  
   Stack() {  
      topElem = -1;   // initialize stack  
      stackPtr = gcnew array<T>(10);  
   }  
  
   void push(const T%);  
   T% top();  
  
private:  
   int topElem;    
   array<T>^ stackPtr;    
};  
  
template <typename T>   
T% Stack<T>::top() {  
   try {  
      return stackPtr[topElem];   // C4801  
      // Try the following line instead.  
      // T% deadstore = stackPtr[topElem] ;  
   }  
  
   catch (System::IndexOutOfRangeException ^ e) {  
      throw gcnew StackEmptyException();  
   }  
  
   catch (System::Exception ^ e) {  
      throw;  
   }  
  
   return stackPtr[topElem] ;  
}  
  
int main() {  
   typedef Stack<Int32> IntStack;  
   IntStack ^ is = gcnew IntStack();  
  
   int i = 1;  
   while (1) {  
      try {  
         is->push(i++);  
      }  
      catch (System::Exception ^ e) {  
         break;  
      }  
      Console::Write("{0} ", is->top());  
   }  
}  
```