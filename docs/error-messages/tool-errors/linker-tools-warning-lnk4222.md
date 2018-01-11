---
title: "リンカー ツールの警告 LNK4222 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4222
dev_langs: C++
helpviewer_keywords: LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a54c452a5df6f99260d6d01fbf4bb9f2f17b955
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4222"></a>リンカー ツールの警告 LNK4222
エクスポートされたシンボル 'symbol' に序数を割り当てないでください。  
  
 次の記号を序数でエクスポートされない必要があります。  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 これらの関数は、名前で常にあるを使用して`GetProcAddress`です。 これに関する注意事項について、リンカーはイメージが大きくなる可能性があるために、エクスポートの種類。 これは、序数でのエクスポートの範囲は比較的少数のエクスポートを含む大規模な場合に発生する可能性があります。 たとえば、オブジェクトに適用された  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 (2 ~ 99) は単なる空白はそのうちの 98 エクスポート アドレス テーブルで 100 のスロットを必要となります。 反対に  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 2 つのスロットを必要となります。 (でもエクスポートできることに注意してください、 [/export](../../build/reference/export-exports-a-function.md)リンカー オプションです)。