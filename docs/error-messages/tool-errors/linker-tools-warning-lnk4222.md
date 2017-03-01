---
title: "リンカー ツールの警告 LNK4222 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0948dc9de4d6b2c83e408b563e437f16b68f2fa4
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4222"></a>リンカー ツールの警告 LNK4222
エクスポートされたシンボル 'symbol' が序数を割り当てられていない必要があります。  
  
 次のシンボルを序数でエクスポートされない必要があります。  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 これらの関数は常に、名前で存在を使用して`GetProcAddress`します。 これに関する注意事項について、リンカーのエクスポートの種類はイメージが大きくなる可能性があるためです。 これは、序数でのエクスポートの範囲は比較的少数のエクスポートを含む大規模な場合に発生します。 次に例を示します。  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 (2 ~ 99) は単なる空白はそのうちの 98 エクスポート アドレス テーブルに 100 のスロットを必要となります。 反対に  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 2 つのスロットを必要となります。 (にもエクスポートできることに注意してください、 [/export](../../build/reference/export-exports-a-function.md)リンカー オプションです)。
