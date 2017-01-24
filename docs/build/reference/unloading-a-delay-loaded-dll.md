---
title: "遅延読み込みした DLL のアンロード | Microsoft Docs"
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
  - "__FUnloadDelayLoadedDLL2"
  - "遅延読み込み (DLL を), アンロード"
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 遅延読み込みした DLL のアンロード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定の遅延読み込みヘルパー関数では、遅延読み込み記述子が、pUnloadIAT フィールドに元のインポート アドレス テーブル \(IAT: Import Address Table\) のポインターとコピーを持つかどうかを調べます。  これらを持つ場合は、ポインターをインポート遅延記述子に対するリストに保存します。  これにより、ヘルパー関数は名前で DLL を検索し、明示的にアンロードできます。  
  
 遅延読み込みした DLL の明示的アンロードには、以下の構造体と関数を使用します。  
  
```  
//  
// Unload support from delayimp.h  
//  
  
// routine definition; takes a pointer to a name to unload  
  
ExternC  
BOOL WINAPI  
__FUnloadDelayLoadedDLL2(LPCSTR szDll);  
  
// structure definitions for the list of unload records  
typedef struct UnloadInfo * PUnloadInfo;  
typedef struct UnloadInfo {  
    PUnloadInfo     puiNext;  
    PCImgDelayDescr pidd;  
    } UnloadInfo;  
  
// from delayhlp.cpp  
// the default delay load helper places the unloadinfo records in the   
// list headed by the following pointer.  
ExternC  
PUnloadInfo __puiHead;  
```  
  
 UnloadInfo 構造体は、演算子 **new** と **delete** の代わりに **LocalAlloc** と **LocalFree** を使用する C\+\+ クラスで実装します。  これらのオプションは、\_\_puiHead を使用して標準リンク リストの先頭に保存されます。  
  
 \_\_FUnloadDelayLoadedDLL を呼び出すと、指定した名前が読み込み済みの DLL のリスト内で検索されます \(完全に一致する名前だけが検索されます\)。  指定した名前が見つかると、pUnloadIAT の IAT のコピーが実行中の IAT の先頭にコピーされ、サンク ポインターが復元されます。ライブラリは **FreeLibrary** によって解放され、一致する **UnloadInfo** レコードがリストからリンク解除され、削除された後、TRUE が返されます。  
  
 \_\_FUnloadDelayLoadedDLL2 関数の引数では、大文字と小文字が区別されます。  たとえば、次のように指定します。  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 次のようには指定しないでください。  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## 参照  
 [Understanding the Helper Function](http://msdn.microsoft.com/ja-jp/6279c12c-d908-4967-b0b3-cabfc3e91d3d)