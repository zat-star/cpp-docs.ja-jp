---
title: "マネージ例外の使用についての基本概念 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finally キーワード, マネージ例外"
  - "catch ブロック"
  - "例外, マネージ"
  - "スロー (例外を), マネージ例外"
  - "try-catch 例外処理"
  - "try-catch 例外処理, マネージ アプリケーション"
  - "Visual C++, 処理 (マネージ例外を)"
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# マネージ例外の使用についての基本概念
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、マネージ アプリケーションで例外処理について説明します。  つまり、**\/clr** のコンパイラ オプションを使用してコンパイルされたアプリケーション。  
  
## このトピックの内容  
  
-   [\/clr の"例外](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [CLR の拡張機能の Try ブロックと Catch ブロック](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## 解説  
 **\/clr** オプションを使用すると、CLR の例外、または標準 [C\+\+ 例外処理](../cpp/cpp-exception-handling.md) と [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md) \(SEH\) 処理できます。  CLR 例外がマネージ型によってスローされた例外になります。  [System::Exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx) クラスは、CLR の例外を処理するための便利なメソッドを提供し、ユーザー定義の例外クラスの基本クラスとして推奨されます。  
  
 インターフェイスからのキャッチ例外の派生は **\/clr**でサポートされません。  また、共通言語ランタイムは、スタック オーバーフロー例外をキャッチできません; スタック オーバーフロー例外は、プロセスが終了します。  
  
 マネージ例外処理の相違点の詳細については、アンマネージ アプリケーション、[C\+\+ のマネージ拡張の Exception Handling の動作の違い](../dotnet/differences-in-exception-handling-behavior-under-clr.md)を参照し。  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> \/clr の"例外  
 C\+\+ の式は CLR 型にハンドルをスローするように拡張されています。  次の例は、カスタムの例外の種類を作成し、その型のインスタンスをスローします:  
  
```  
// clr_exception_handling.cpp  
// compile with: /clr /c  
ref struct MyStruct: public System::Exception {  
public:  
   int i;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   throw pMyStruct;  
}  
```  
  
 値型はスローされる前にボックス化する必要があります:  
  
```  
// clr_exception_handling_2.cpp  
// compile with: /clr /c  
value struct MyValueStruct {  
   int i;  
};  
  
void GlobalFunction() {  
   MyValueStruct v = {11};  
   throw (MyValueStruct ^)v;  
}  
```  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> CLR の拡張機能の Try ブロックと Catch ブロック  
 同じ **try**\/**catch** ブロック構造は、CLR およびネイティブ例外をキャッチし、例外の両方に使用できます。:  
  
```  
// clr_exception_handling_3.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyStruct : public Exception {  
public:  
   int i;  
};  
  
struct CMyClass {  
public:  
   double d;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   pMyStruct->i = 11;  
   throw pMyStruct;  
}  
  
void GlobalFunction2() {  
   CMyClass c = {2.0};  
   throw c;  
}  
  
int main() {  
   for ( int i = 1; i >= 0; --i ) {  
      try {  
         if ( i == 1 )  
            GlobalFunction2();  
         if ( i == 0 )  
            GlobalFunction();  
      }  
      catch ( CMyClass& catchC ) {  
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );  
         Console::WriteLine( catchC.d );  
      }  
      catch ( MyStruct^ catchException ) {  
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );  
         Console::WriteLine( catchException->i );  
      }  
   }  
}  
```  
  
### 出力  
  
```  
In 'catch(CMyClass& catchC)'  
2  
In 'catch(MyStruct^ catchException)'  
11  
```  
  
### C\+\+ オブジェクトのアンワインドの順序  
 アンワインドがスローする関数と処理関数とのランタイム スタック上のデストラクターがインストールされている C\+\+ オブジェクトに対して発生します。  CLR 型をヒープに割り当てられているため、アンワインド。これらには適用されません。  
  
 スローされた例外のイベントの順序は次のとおりです。:  
  
1.  ランタイムは、スタックのフィルターを除き、例外をキャッチするために、では適切な catch 句を検索します。  次に、catch 句は構文的な順序で、呼び出し履歴で動的に最初に検索されます。  
  
2.  適切なハンドラーがある場合、スタックはその点にアンワインドされます。  履歴の各関数の呼び出しは、ローカル オブジェクトを破棄し、\_\_finally ブロックは最も外側になってから実行されます。  
  
3.  一度スタックは、catch 句実行されますアンワインドされます。  
  
### キャッチのアンマネージ型  
 アンマネージ オブジェクト型は、スローされると、型 [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx)の例外にラップされます。  **catch** の適切な句を検索するときには、2 とおりの方法があります。  
  
-   ネイティブ C\+\+ 型が発生した場合、例外は、ある型と開けられ、比較されます。  この比較は、ネイティブ C\+\+ 型を通常の方法でキャッチされるようにします。  
  
-   ただし、基本クラスの型 **SEHException** またはの **catch** 句が最初に参照されると、例外を受け取ります。  したがって、CLR 型の句をキャッチする前にネイティブ C\+\+ 型を先にキャッチするすべての catch 句を置く必要があります。  
  
 次の点に注意してください。  
  
```  
catch(Object^)  
```  
  
 および  
  
```  
catch(...)  
```  
  
 両方の型を含む、スローされた例外をキャッチします。  
  
 アンマネージ型の catch \(Object^\) によってスローされたときは、オブジェクトを破棄しません。  
  
 **\/EHs** または **\/EHa**の代わりに [\/EHsc](../build/reference/eh-exception-handling-model.md) のコンパイラ オプションを使用することをスローするか、キャッチ アンマネージ例外が、お勧めします。  
  
## 参照  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)   
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)