---
title: "方法: アセンブリの互換性の問題を診断し修復する (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "互換性, アセンブリ間の"
  - "例外, 診断 (不適切な動作を)"
  - "バージョン管理"
  - "バージョン管理, 診断 (競合を)"
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: アセンブリの互換性の問題を診断し修復する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、コンパイル時に参照されたアセンブリのバージョンと実行時に参照されたアセンブリのバージョンが一致しない場合に発生する可能性のあること、およびその問題を回避する方法について説明します。  
  
 アセンブリをコンパイルするとき、`#using` 構文によって他のアセンブリが参照される場合があります。  コンパイル中、これらのアセンブリはコンパイラによってアクセスされます。  これらのアセンブリの情報は、最適化の決定に使用されます。  
  
 しかし、参照先のアセンブリが変更されて再コンパイルされたにもかかわらず、そのアセンブリに依存する参照元のアセンブリを再コンパイルしないと、アセンブリの互換性がなくなる可能性があります。  最初のバージョンで有効だった最適化の決定が、新しいアセンブリのバージョンでは正しくない場合もあります。  このような非互換性によって、さまざまな実行時エラーが発生することがあります。  このような場合に発生する例外はさまざまです。  実行時にエラーがどのように報告されるかは、問題の原因となったコード変更の性質によって異なります。  
  
 このようなエラーは、製品のリリース バージョンに合わせてアプリケーション全体が再度ビルドされる限り、最終製品コードでは問題にはなりません。  公開リリースされるアセンブリには正式なバージョン番号を付けて、このような問題を回避してください。  詳細については、「[アセンブリのバージョン管理](../Topic/Assembly%20Versioning.md)」を参照してください。  
  
### 非互換性エラーの診断と修復  
  
1.  別のアセンブリを参照するコードで実行時の例外や他のエラー条件が発生し、他の原因が見つからない場合は、古いアセンブリが原因である可能性があります。  
  
2.  最初に、例外または他のエラー条件を特定し、再現します。  古い形式による例外が原因で発生する問題は、再現可能です。  
  
3.  アプリケーション内で参照されているアセンブリのタイムスタンプを調べます。  
  
4.  参照されるアセンブリのタイムスタンプがアプリケーションの最後のコンパイルのタイムスタンプよりも新しい場合は、アプリケーションが古くなっています。  この場合は、最新のアセンブリを使用してアプリケーションを再コンパイルし、必要に応じてコードを変更します。  
  
5.  アプリケーションを再実行し、問題を再現する処理を実行し、例外が発生しないことを検証します。  
  
## 使用例  
 次のプログラムは、メソッドのアクセシビリティを下げ、別のアセンブリから再コンパイルしないでそのメソッドにアクセスしようとした場合に発生する問題を示します。  最初に、`changeaccess.cpp` をコンパイルします。  これは、変更される参照アセンブリです。  次に、`referencing.cpp` をコンパイルします。  コンパイルが正常に終了します。  次に、呼び出されるメソッドのアクセシビリティを下げます。  `/DCHANGE_ACCESS` フラグを使用して `changeaccess.cpp` を再コンパイルします。  これによってメソッドは private から protected に変更され、このメソッドを有効に呼び出すことはできなくなります。  `referencing.exe` を再コンパイルしないでアプリケーションを再実行します。  <xref:System.MethodAccessException> という例外が発生します。  
  
```  
// changeaccess.cpp  
// compile with: /clr:safe /LD  
// After the initial compilation, add /DCHANGE_ACCESS and rerun  
// referencing.exe to introduce an error at runtime. To correct  
// the problem, recompile referencing.exe  
  
public ref class Test {  
#if defined(CHANGE_ACCESS)  
protected:  
#else  
public:  
#endif  
  
  int access_me() {  
    return 0;  
  }  
  
};  
  
```  
  
```  
// referencing.cpp  
// compile with: /clr:safe   
#using <changeaccess.dll>  
  
// Force the function to be inline, to override the compiler's own  
// algorithm.  
__forceinline  
int CallMethod(Test^ t) {  
  // The call is allowed only if access_me is declared public  
  return t->access_me();  
}  
  
int main() {  
  Test^ t = gcnew Test();  
  try  
  {  
    CallMethod(t);  
    System::Console::WriteLine("No exception.");  
  }  
  catch (System::Exception ^ e)  
  {  
    System::Console::WriteLine("Exception!");  
  }  
  return 0;  
}  
  
```  
  
## 参照  
 [\#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)   
 [マネージ型](../Topic/Managed%20Types%20\(C++-CLI\).md)