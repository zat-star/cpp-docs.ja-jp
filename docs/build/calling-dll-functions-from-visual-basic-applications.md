---
title: "DLL 関数の Visual Basic アプリケーションからの呼び出し方 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "__stdcall キーワード [C++]"
  - "呼び出し (DLL 関数を VB アプリケーションから) [C++]"
  - "DLL 関数 [C++]"
  - "DLL 関数 [C++], 呼び出し"
  - "DLL [C++], 呼び出し"
  - "関数呼び出し [C++], DLL 関数"
  - "関数 [C++], 呼び出し (DLL 関数を Visual Basic から)"
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DLL 関数の Visual Basic アプリケーションからの呼び出し方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

VBA \(Visual Basic アプリケーション\) や Pascal、Fortran などの他の言語で書かれたアプリケーションから C\/C\+\+ DLL 内の関数を呼び出すには、コンパイラによって装飾された名前ではなく正しい呼び出し規約を使ってその関数をエクスポートする必要があります。  
  
 `__stdcall` は、関数の正しい呼び出し規約を作成します。つまり、呼び出された関数がスタックをクリアし、パラメーターは右から左へ渡されます。ただし、関数名は異なる方法で装飾されます。  このため、**\_\_declspec\(dllexport\)** が DLL 内のエクスポート関数で使用される場合は、装飾名がエクスポートされます。  
  
 `__stdcall` 方式で装飾された名前には、シンボル名の前に \_ \(アンダースコア\)、シンボルの後に @ \(アット マーク\) が付けられ、その後に引数リストのバイト数 \(必要なスタック空間\) が付けられます。  結果として、宣言時の関数は次のようになります。  
  
```  
int __stdcall func (int a, double b)  
```  
  
 これを装飾すると、次のようになります。  
  
```  
_func@12  
```  
  
 C の呼び出し規約 \(`__cdecl`\) による装飾では、名前は `_func` となります。  
  
 装飾名を取得するには、[\/MAP](../build/reference/map-generate-mapfile.md) を使用します。  **\_\_declspec\(dllexport\)** を使うと、以下の処理が行われます。  
  
-   関数が C の呼び出し規約 \(**\_cdecl**\) に従ってエクスポートされる場合、先頭のアンダースコア \(\_\) は名前のエクスポート時に除去されます。  
  
-   エクスポートされる関数が C の呼び出し規約を使わない場合 \(`__stdcall` など\) は、装飾名がエクスポートされます。  
  
 スタックがクリアされた場所をオーバーライドする方法はないので、`__stdcall` を使う必要があります。  `__stdcall` を使って装飾を外すには、.def ファイルの EXPORTS セクションにエイリアスを使って、その名前を指定する必要があります。  関数宣言の例を次に示します。  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 .DEF ファイルの内容は、次のとおりです。  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 Visual Basic で書かれたプログラムから DLL を呼び出す場合は、ここで示したエイリアスの手法を .def ファイル内で使用する必要があります。  エイリアスが Visual Basic プログラムの中で宣言されている場合は、.def ファイル内でのエイリアスは不要です。  Visual Basic プログラムでは、[Declare](../Topic/Declare%20Statement.md) ステートメントにエイリアス句を追加することで実現されます。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [DLL からのエクスポート](../build/exporting-from-a-dll.md)  
  
-   [DEF ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\) を使った DLL からのエクスポート](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C 言語の実行形式で使う C\+\+ 関数のエクスポート](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [エクスポート方式の使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [装飾名](../Topic/Decorated%20Names.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)