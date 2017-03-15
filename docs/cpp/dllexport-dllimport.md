---
title: "dllexport、dllimport | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "dllimport_cpp"
  - "dllexport_cpp"
  - "dllexport"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], dllexport"
  - "__declspec キーワード [C++], dllimport"
  - "dllexport __declspec キーワード"
  - "dllimport __declspec キーワード"
ms.assetid: ff95b645-ef55-4e72-b848-df44657b3208
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# dllexport、dllimport
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `dllexport` および **dllimport** ストレージ クラス属性は C および C\+\+ 言語への Microsoft 固有の拡張機能です。  それらの属性を使用すると、関数、データ、オブジェクトを DLL との間でエクスポートおよびインポートできます。  
  
## 構文  
  
```  
  
        __declspec( dllimport ) declarator  
__declspec( dllexport ) declarator  
```  
  
## 解説  
 これらの属性は、DLL のクライアント \(実行可能ファイルまたは別の DLL\) に対する DLL のインターフェイスを明示的に定義します。  関数を `dllexport` として宣言すると、少なくともエクスポートした関数の指定には、モジュール定義 \(.def\) ファイルが不要になります。  `dllexport` 属性は `__export` キーワードに置き換わるものです。  
  
 クラスを declspec\(dllexport\) とマークした場合、そのクラス階層内のクラス テンプレートの特殊化は暗黙的に declspec\(dllexport\) とマークされます。  つまり、クラス テンプレートが明示的にインスタンス化され、クラスのメンバーの定義が必要になります。  
  
 関数を `dllexport` とマークすると、その関数は装飾名で公開されます。  C\+\+ の関数の場合、この処理には名前のマングルが含まれます。  C 関数または `extern "C"` として宣言されている関数の場合、この処理には呼び出し規約に基づいたプラットフォーム固有の装飾が含まれます。  C と C\+\+ コードでの名前の装飾については、「[装飾名](../Topic/Decorated%20Names.md)」を参照してください。  `__cdecl` 呼び出し規約を使用する エクスポートされた C 関数や C\+\+ `extern "C"` 関数には、名前の装飾が適用されません。  
  
 修飾されていない名前をエクスポートするには、EXPORTS セクションに非装飾名を定義したモジュール定義 \(.def\) ファイルを使用してリンクできます。  詳細については、「[EXPORTS](../Topic/EXPORTS.md)」を参照してください。  修飾されていない名前をエクスポートする別の方法は、ソース コードで `#pragma comment(linker, "/export:``alias``=``decorated_name``")` ディレクティブを使用することです。  
  
 `dllexport` または **dllimport** を宣言するときは、[拡張属性構文](../cpp/declspec.md)と `__declspec` キーワードを使用する必要があります。  
  
## 使用例  
  
```cpp  
// Example of the dllimport and dllexport class attributes  
__declspec( dllimport ) int i;  
__declspec( dllexport ) void func();  
```  
  
 または、コードをより読みやすくするために、マクロ定義を使用できます。  
  
```cpp  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllImport int j;  
DllExport int n;  
```  
  
 詳細については次を参照してください:  
  
-   [定義と宣言](../cpp/definitions-and-declarations-cpp.md)  
  
-   [dllexport と dllimport を使用したインライン C\+\+ 関数の定義](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
-   [一般的な規則と制約](../cpp/general-rules-and-limitations.md)  
  
-   [C\+\+ クラスでの dllimport と dllexport の使用](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)