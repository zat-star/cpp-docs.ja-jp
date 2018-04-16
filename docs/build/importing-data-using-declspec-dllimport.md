---
title: "_Declspec (dllimport) を使用してデータのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ebbc91b9144a7fe8025a34e9c1476ab23b604c46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="importing-data-using-declspecdllimport"></a>__declspec(dllimport) を使ったデータのインポート
使用して、データの場合**_declspec**は、間接レイヤーの役割を削除する便利な項目です。 DLL からデータをインポートするときにまだインポート アドレス テーブルを通過する必要があります。 前に**_declspec (dllimport)**、つまりを DLL からエクスポートされたデータにアクセスするときに、余分なレベルの間接参照を行うには注意する必要がありました。  
  
```  
// project.h  
#ifdef _DLL   // If accessing the data from inside the DLL  
   ULONG ulDataInDll;  
  
#else         // If accessing the data from outside the DLL  
   ULONG *ulDataInDll;  
#endif  
```  
  
 内のデータはエクスポートし、します。DEF ファイル:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   CONSTANT  
```  
  
 DLL の外部にアクセスします。  
  
```  
if (*ulDataInDll == 0L)   
{  
   // Do stuff here  
}  
```  
  
 としてデータをマークする**_declspec**コンパイラに自動的に、間接参照のコードを生成します。 不要になった、上記の手順について心配する必要があります。 既に説明したようには使用しないでください**_declspec (dllimport)** DLL を作成するときにデータを宣言します。 DLL 内の関数では、データ オブジェクトにアクセスするのにインポート アドレス テーブルを使用しないでください。そのため、追加のレベルの間接参照の存在はありません。  
  
 DLL から自動的にデータをエクスポートするには、この宣言を使用します。  
  
```  
__declspec(dllexport) ULONG ulDataInDLL;  
```  
  
## <a name="see-also"></a>参照  
 [アプリケーションへのインポート](../build/importing-into-an-application.md)