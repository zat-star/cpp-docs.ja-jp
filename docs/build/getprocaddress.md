---
title: "GetProcAddress | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetProcAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL [C++], GetProcAddress"
  - "GetProcAddress メソッド"
  - "序数エクスポート [C++]"
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# GetProcAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロセスに DLL を明示的にリンクする場合は、[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) を呼び出して、DLL 内のエクスポート関数のアドレスを取得します。  返された関数ポインターを使って、DLL 関数を呼び出します。  **GetProcAddress** のパラメーターには、**LoadLibrary**、`AfxLoadLibrary`、**GetModuleHandle** のいずかによって返された DLL モジュール ハンドルと、呼び出す関数の名前またはエクスポート序数を渡します。  
  
 DLL 関数の呼び出しにはポインターが使われ、コンパイル時にデータ型はチェックされないため、関数へ渡すパラメーターが正しいことを確認してください。パラメーターが不正な場合、スタック上に割り当てられたメモリ域をオーバーしたり、アクセス違反を起こしたりすることがあります。  型をタイプセーフにする 1 つの方法は、エクスポート関数の関数プロトタイプを見て、関数ポインター用に対応する typedef を作成することです。  たとえば、次のようになります。  
  
```  
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);  
...  
  
HINSTANCE hDLL;               // Handle to DLL  
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
DWORD dwParam1;  
UINT  uParam2, uReturnVal;  
  
hDLL = LoadLibrary("MyDLL");  
if (hDLL != NULL)  
{  
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,  
                                           "DLLFunc1");  
   if (!lpfnDllFunc1)  
   {  
      // handle the error  
      FreeLibrary(hDLL);  
      return SOME_ERROR_CODE;  
   }  
   else  
   {  
      // call the function  
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);  
   }  
}  
```  
  
 **GetProcAddress** の呼び出し時に関数を指定する方法は、ビルドされた DLL の種類によって異なります。  
  
 エクスポート序数を使用できるのは、リンクする DLL がモジュール定義ファイル \(.def\) を使ってビルドされたものであり、その DLL の .def ファイルの **EXPORTS** セクション内の関数に序数が付けられている場合だけです。  関数名ではなくエクスポート序数を使って **GetProcAddress** を呼び出すと、DLL にエクスポート関数が多数含まれる場合は、少し高速になります。エクスポート序数が DLL のエクスポート テーブルの索引の役割を果たすからです。  指定された名前を DLL のエクスポート テーブル内の関数名と比較するのではなく、エクスポート序数を使うと、**GetProcAddress** はその関数をすぐに発見できます。  ただし、エクスポート序数を使って **GetProcAddress** を呼び出すには、.def ファイル内でエクスポート関数に対して割り当てられている序数を知っている必要があります。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [暗黙的なリンク](../Topic/Linking%20Implicitly.md)  
  
-   [リンク方式の使い分け](../build/determining-which-linking-method-to-use.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [\<caps:sentence id\="tgt17" sentenceid\="8c920606bb67e2587dd3c3e5cf977593" class\="tgtSentence"\>FreeLibrary\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [DEF ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)