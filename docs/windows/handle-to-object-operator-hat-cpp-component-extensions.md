---
title: "オブジェクト演算子 (^) へのハンドル (C++ コンポーネント拡張) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "オブジェクトの ^ ハンドル [C++]"
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# オブジェクト演算子 (^) へのハンドル (C++ コンポーネント拡張)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*ハンドル宣言子* \(`^`、「ハット」と読みます\) は、[指定子](../cpp/overview-of-declarators.md)の型を変更します。この指定子の型は、宣言されたオブジェクトがアクセス不能になったとシステムが判断すると、そのオブジェクトが自動的に削除されることを意味します。  
  
## 宣言されたオブジェクトへのアクセス  
 ハンドル宣言子を指定して宣言した変数は、オブジェクトへのポインターのように動作します。  ただし、変数はオブジェクト全体を指し示します。オブジェクトのメンバーを指すことはできません。また、ポインター演算をサポートしません。  オブジェクトにアクセスするには間接演算子 \(`*`\) を使用し、オブジェクトのメンバーにアクセスするには矢印のメンバー アクセス演算子 \(`->`\) を使用します。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 コンパイラは、COM *参照カウント* メカニズムを使用して、オブジェクトがもう使用されず、削除してよいかどうかを判断します。  これが可能なのは、Windows ランタイム インターフェイスから派生するオブジェクトが実際に COM オブジェクトであるためです。  参照カウントは、オブジェクトが作成されるかコピーされるとインクリメントされ、オブジェクトが null に設定されるかスコープから外れるとデクリメントされます。  参照カウントがゼロになると、オブジェクトは直ちに自動的に削除されます。  
  
 ハンドル宣言子の利点は、煩雑でエラーが発生しやすいプロセスであるオブジェクトについて、COM では参照カウントを明示的に管理する必要があるということです。  つまり、参照カウントをインクリメントおよびデクリメントするには、オブジェクトの AddRef\(\) メソッドと Release\(\) メソッドを呼び出す必要があります。  ただし、ハンドル宣言子を使用してオブジェクトを宣言する場合、Visual C\+\+ コンパイラでは、参照カウントを自動的に調整するコードを生成します。  
  
 オブジェクトをインスタンス化する方法の詳細については、「[ref new](../windows/ref-new-gcnew-cpp-component-extensions.md)」を参照してください。  
  
## 要件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 システムは、CLR *ガベージ コレクター* メカニズムを使用して、オブジェクトがもう使用されず、削除してよいかどうかを判断します。  共通言語ランタイムが、オブジェクトを割り当てるヒープを保持し、プログラムでマネージ参照 \(変数\) を使用します。それによりヒープ内のオブジェクトの場所が示されます。  オブジェクトがもう使用されなくなると、オブジェクトがヒープで占有していたメモリが解放されます。  ガベージ コレクターは、解放済みメモリの使用を改善するために、定期的にヒープを圧縮します。  ヒープを圧縮すると、ヒープのオブジェクトを移動できます。これにより、マネージ参照によって参照される場所が無効になります。  ただし、ガベージ コレクターは、すべてのマネージ参照の場所を認識しており、ヒープ内のオブジェクトの現在の場所を示すようにマネージ参照を自動的に更新します。  
  
 ネイティブ C\+\+ ポインター \(`*`\) と参照 \(`&`\) は、マネージ参照ではないため、それらが指し示すアドレスをガベージ コレクターは自動的に更新できません。  この問題を解決するには、ガベージ コレクターが認識しており自動的に更新できる変数を、ハンドル宣言子を使用して指定します。  
  
 Visual C\+\+ 2002 と Visual C\+\+ 2003 では、`__gc *` を使用して、マネージ ヒープ上のオブジェクトを宣言していました。新しい構文では、`__gc *` が `^` で置き換えられています。  
  
 詳細については、「[方法: ネイティブ型のハンドルを宣言する](../dotnet/how-to-declare-handles-in-native-types.md)」を参照してください。  
  
### 例  
 **例**  
  
 このサンプルは、マネージ ヒープ上で参照型のインスタンスを作成する方法を示しています。また、このサンプルでは、1 つのハンドルを別のハンドルで初期化することができ、その結果、ガベージ コレクトされたマネージ ヒープ上で同じオブジェクトへの参照が 2 つ作成されることも示しています。  1 つのハンドルに [nullptr](../windows/nullptr-cpp-component-extensions.md) を割り当てても、ガベージ コレクションでオブジェクトが示されないことに注意してください。  
  
```  
// mcppv2_handle.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   MyClass() : i(){}  
   int i;  
   void Test() {  
      i++;  
      System::Console::WriteLine(i);  
   }  
};  
  
int main() {  
   MyClass ^ p_MyClass = gcnew MyClass;  
   p_MyClass->Test();  
  
   MyClass ^ p_MyClass2;  
   p_MyClass2 = p_MyClass;  
  
   p_MyClass = nullptr;  
   p_MyClass2->Test();     
}  
```  
  
 **出力**  
  
 **1**   
**2** **例**  
  
 次の例では、マネージ ヒープ上のオブジェクト \(オブジェクトの型はボックス化された値型\) へのハンドルを宣言する方法を示しています。  また、このサンプルでは、ボックス化されたオブジェクトから値型を取得する方法も示します。  
  
```  
// mcppv2_handle_2.cpp  
// compile with: /clr  
using namespace System;  
  
void Test(Object^ o) {  
   Int32^ i = dynamic_cast<Int32^>(o);  
  
   if(i)  
      Console::WriteLine(i);  
   else  
      Console::WriteLine("Not a boxed int");  
}  
  
int main() {  
   String^ str = "test";  
   Test(str);  
  
   int n = 100;  
   Test(n);  
}  
```  
  
 **出力**  
  
  **Not a boxed int**  
 **100** **例**  
  
 このサンプルでは、任意のオブジェクトを指し示す void\* ポインターを使用した C\+\+ の共通の表現形式が Object^ で置き換えられることを示しています。Object^ は、どの参照クラスへのハンドルも保持できます。  また、配列やデリゲートなど、すべての型がオブジェクト ハンドルに変換できることも示しています。  
  
```  
// mcppv2_handle_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections;  
public delegate void MyDel();  
ref class MyClass {  
public:  
   void Test() {}  
};  
  
void Test(Object ^ x) {  
   Console::WriteLine("Type is {0}", x->GetType());  
}  
  
int main() {  
   // handle to Object can hold any ref type  
   Object ^ h_MyClass = gcnew MyClass;  
  
   ArrayList ^ arr = gcnew ArrayList();  
   arr->Add(gcnew MyClass);  
  
   h_MyClass = dynamic_cast<MyClass ^>(arr[0]);  
   Test(arr);  
  
   Int32 ^ bi = 1;  
   Test(bi);  
  
   MyClass ^ h_MyClass2 = gcnew MyClass;  
  
   MyDel^ DelInst = gcnew MyDel(h_MyClass2, &MyClass::Test);  
   Test(DelInst);  
}  
```  
  
 **出力**  
  
  **Type is System.Collections.ArrayList**  
 **Type is System.Int32**  
 **Type is MyDel** **例**  
  
 このサンプルは、ハンドルが逆参照できること、および逆参照されるハンドル経由でメンバーにアクセスできることを示しています。  
  
```  
// mcppv2_handle_4.cpp  
// compile with: /clr  
using namespace System;  
value struct DataCollection {  
private:  
   int Size;  
   array<String^>^ x;  
  
public:  
   DataCollection(int i) : Size(i) {  
      x = gcnew array<String^>(Size);  
      for (int i = 0 ; i < Size ; i++)  
         x[i] = i.ToString();  
   }  
  
   void f(int Item) {  
      if (Item >= Size)  
      {  
         System::Console::WriteLine("Cannot access array element {0}, size is {1}", Item, Size);  
         return;  
      }  
      else  
         System::Console::WriteLine("Array value: {0}", x[Item]);  
   }  
};  
  
void f(DataCollection y, int Item) {  
   y.f(Item);  
}  
  
int main() {  
   DataCollection ^ a = gcnew DataCollection(10);  
   f(*a, 7);   // dereference a handle, return handle's object  
   (*a).f(11);   // access member via dereferenced handle  
}  
```  
  
 **出力**  
  
  **Array value: 7**  
 **Cannot access array element 11, size is 10** **例**  
  
 このサンプルでは、ネイティブ参照 \(`&`\) をマネージ型の `int` メンバーにバインドできないことを示しています。これは、ガベージ コレクトされたヒープに `int` が格納される可能性があり、またネイティブ参照がマネージ ヒープ上のオブジェクトの移動を追跡しないためです。  解決策は、ローカル変数を使用すること、または、`&` を `%` に変更して、追跡参照にすることです。  
  
```  
// mcppv2_handle_5.cpp  
// compile with: /clr  
ref struct A {  
   void Test(unsigned int &){}  
   void Test2(unsigned int %){}  
   unsigned int i;  
};  
  
int main() {  
   A a;  
   a.i = 9;  
   a.Test(a.i);   // C2664  
   a.Test2(a.i);   // OK  
  
   unsigned int j = 0;  
   a.Test(j);   // OK  
}  
```  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md)