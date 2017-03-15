---
title: "明示的なリンク | Microsoft Docs"
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
  - "明示的なリンク [C++]"
ms.assetid: 1e13d960-a195-4e6d-9864-7d8f3a701f4b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 明示的なリンク
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

明示的リンクの場合、アプリケーションは実行時に DLL を明示的に読み込むために、関数呼び出しをする必要があります。  DLL と明示的にリンクするには、アプリケーションは、以下の手順を実行します。  
  
-   **LoadLibrary** \(または、同様の関数\) を呼び出して、DLL を読み込み、モジュール ハンドルを取得します。  
  
-   **GetProcAddress** を呼び出して、アプリケーションが呼び出す各エクスポート関数への関数ポインターを取得します。  アプリケーションは、ポインターを通じて DLL の関数を呼び出すので、コンパイラは外部参照を生成しません。このため、インポート ライブラリとリンクする必要はありません。  
  
-   DLL の終了時に **FreeLibrary** を呼び出します。  
  
 たとえば、次のようになります。  
  
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
  
## 目的に合ったトピックをクリックしてください  
  
-   [暗黙的なリンク](../Topic/Linking%20Implicitly.md)  
  
-   [リンク方式の使い分け](../build/determining-which-linking-method-to-use.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
-   [FreeLibrary と AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [Windows が使用する DLL 検索パス](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## 参照  
 [DLL と実行形式のリンク](../build/linking-an-executable-to-a-dll.md)