---
title: "遅延読み込みした DLL のアンロード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0962059e6e55ce68133960cc9f8d1de8c7f0ef61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="unloading-a-delay-loaded-dll"></a>遅延読み込みした DLL のアンロード
既定値が指定した遅延読み込みヘルパーは、遅延読み込み記述子がポインターの元のインポート アドレス テーブル (IAT) のコピーと pUnloadIAT フィールドを確認します。 その場合へのポインターをインポート遅延記述子のリストで保存します。 これにより、その DLL を明示的にアンロードをサポートするために名前で DLL を検索するヘルパー関数。  
  
 次に、関連付けられている構造体と遅延読み込みした DLL を明示的にアンロードするための関数を示します。  
  
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
  
 UnloadInfo 構造が使用する C++ クラスで実装されている**LocalAlloc**と**LocalFree** 、演算子として実装**新しい**と演算子**削除**それぞれします。 これらのオプションは、リストの先頭として _puihead を使用して、標準のリンク リストに保持されます。  
  
 通話 __FUnloadDelayLoadedDLL は名前を検索しようとしています (厳密な一致が必要です)、読み込まれた Dll のリストで指定します。 見つかると、pUnloadIAT 内の IAT のコピーがコピー、ライブラリを使用して解放がサンクのポインターを復元する実行中の IAT の上にある、 **FreeLibrary**、一致する**UnloadInfo**からレコードのリンクを解除一覧および削除され、TRUE が返されます。  
  
 関数 __FUnloadDelayLoadedDLL2 への引数は、大文字小文字を区別します。 たとえば、次のように指定。  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 および not。  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## <a name="see-also"></a>関連項目  
 [ヘルパー関数について](understanding-the-helper-function.md)