---
title: "nullptr  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__nullptr keyword (C++)"
  - "nullptr keyword [C++]"
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nullptr  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`nullptr` キーワードは *null ポインター値を*表します。  オブジェクトのハンドル、内部ポインター、またはネイティブ ポインター型がオブジェクトを指さないことを示すために null ポインター値を使用します。  
  
 マネージまたはネイティブ コードの `nullptr` を使用します。  コンパイラはマネージ ネイティブ null ポインター値に適切な異なる手順を生成します。  このキーワードの ISO C\+\+ 標準バージョンの使い方の詳細については、「[nullptr](../Topic/nullptr.md)」を参照してください。  
  
 `__nullptr` キーワードは `nullptr`と同じ意味を持ちますが、ネイティブ コードだけに適用されます。Microsoft 固有のキーワード。  ネイティブ C\/C\+\+ コードの `nullptr` を使用し、[\/clr](../build/reference/clr-common-language-runtime-compilation.md) のコンパイラ オプションを使用すると、コンパイラは `nullptr` がネイティブまたはマネージ null ポインター値を表示するかどうかを判断できません。  コンパイラに意図を明確にするため、マネージ値または `__nullptr` をネイティブ値を指定するように指定するに `nullptr` を使用します。  
  
 `nullptr` キーワードは、Visual Basic の `Nothing` と C\# の `null` と同じです。  
  
## 使用法  
 `nullptr` キーワードはいずれもハンドル、ネイティブ ポインター使用したり、関数の引数を使用できます。  
  
 `nullptr` キーワードは、型ではなく、使用するために以下のサポートされていません。:  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   \(`throw (Object^)nullptr;` の動作が`throw nullptr`\)  
  
 `nullptr` キーワードは、次のポインター型の初期化に使用できます。:  
  
-   ネイティブ ポインター  
  
-   Windows ランタイム ハンドル  
  
-   マネージ ハンドル  
  
-   マネージ内部ポインター  
  
 参照を使用する前にポインターやハンドルの参照が null であるかどうかをテストするために `nullptr` キーワードを使用できます。  
  
 エラー チェック時に null ポインター値を使用する言語間の関数呼び出しが正しく解釈されます。  
  
 ゼロにハンドルを初期化できません; `nullptr` のみ使用できます。  オブジェクトのハンドルへの定数 0 の代入は `Object^`に `Int32` 二重のキャストが生成されます。  
  
## 使用例  
 次のコード例は `nullptr` キーワードがハンドル、ネイティブ ポインターどこでも使用できるか、または関数の引数が使用できることを示します。  この例は、使用する前に参照をチェックするために `nullptr` キーワードが使用できることを示します。  
  
```  
// mcpp_nullptr.cpp  
// compile with: /clr  
value class V {};  
ref class G {};  
void f(System::Object ^) {}  
  
int main() {  
// Native pointer.  
   int *pN = nullptr;  
// Managed handle.  
   G ^pG = nullptr;  
   V ^pV1 = nullptr;  
// Managed interior pointer.  
   interior_ptr<V> pV2 = nullptr;  
// Reference checking before using a pointer.  
   if (pN == nullptr) {}  
   if (pG == nullptr) {}  
   if (pV1 == nullptr) {}  
   if (pV2 == nullptr) {}  
// nullptr can be used as a function argument.  
   f(nullptr);   // calls f(System::Object ^)  
}  
```  
  
## 使用例  
 **例**  
  
 次のコード例は、`nullptr` とゼロがネイティブ ポインターで交換して使用できることを示します。  
  
```  
// mcpp_nullptr_1.cpp  
// compile with: /clr  
class MyClass {  
public:  
   int i;  
};  
  
int main() {  
   MyClass * pMyClass = nullptr;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
  
   pMyClass = 0;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
}  
```  
  
 **出力**  
  
  **pMyClass \=\= " nullptr**  
 **pMyClass \=\= 0**  
 **pMyClass \=\= " nullptr**  
 **pMyClass \=\= 0**   
## 使用例  
 **例**  
  
 次のコード例は `nullptr` として任意の型のハンドルまたはすべての型にネイティブ ポインターとして解釈することを示します。  異なる種類のハンドルでオーバーロードする関数では、あいまいさのエラーが生成されます。  `nullptr`、明示的に型にキャストされなければなりません。  
  
```  
// mcpp_nullptr_2.cpp  
// compile with: /clr /LD  
void f(int *){}  
void f(int ^){}  
  
void f_null() {  
   f(nullptr);   // C2668  
   // try one of the following lines instead  
   f((int *) nullptr);  
   f((int ^) nullptr);  
}  
```  
  
## 使用例  
 **例**  
  
 次のコード例は `nullptr` をキャストすることが許可されると、`nullptr` 値を含むキャストの型へのポインターやハンドルを返します。  
  
```  
// mcpp_nullptr_3.cpp  
// compile with: /clr /LD  
using namespace System;  
template <typename T>   
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type  
  
int main() {  
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)  
  
   // Delete the following line to resolve.  
   f(nullptr);  
  
   f(0);   // T = int, call f(int)  
}  
```  
  
## 使用例  
 **例**  
  
 次のコード例は `nullptr` が関数のパラメーターとして使用できることを示します。  
  
```  
// mcpp_nullptr_4.cpp  
// compile with: /clr  
using namespace System;  
void f(Object ^ x) {  
   Console::WriteLine("test");  
}  
  
int main() {  
   f(nullptr);  
}  
```  
  
 **出力**  
  
  **テスト**   
## 使用例  
 **例**  
  
 次のコード例はハンドルが宣言され、明示的に初期化される場合に、それらが `nullptr`に初期化される既定示します。  
  
```  
// mcpp_nullptr_5.cpp  
// compile with: /clr  
using namespace System;  
ref class MyClass {  
public:  
   void Test() {  
      MyClass ^pMyClass;   // gc type  
      if (pMyClass == nullptr)  
         Console::WriteLine("NULL");  
   }  
};  
  
int main() {  
   MyClass ^ x = gcnew MyClass();  
   x -> Test();  
}  
```  
  
 **出力**  
  
  **NULL**   
## 使用例  
 **例**  
  
 次のコード例は **\/clr**でコンパイルした場合 `nullptr` がネイティブ ポインターに割り当てることができることを示します。  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## 要件  
 コンパイラ オプション: \(必須ではない; **\/ZW**、および **\/clr**を含むすべてのコード生成オプションでサポートされる\)  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../Topic/nullptr.md)