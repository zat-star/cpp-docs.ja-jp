---
title: "no_smart_pointers |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_search_pointers
dev_langs: C++
helpviewer_keywords: no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0837a702eb54ac19ba1a034d4c899284aba6cb37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="nosmartpointers"></a>no_smart_pointers
**C 固有の仕様**  
  
 タイプ ライブラリのすべてのインターフェイスに対して、スマート ポインターの作成を抑制します。  
  
## <a name="syntax"></a>構文  
  
```  
no_smart_pointers  
```  
  
## <a name="remarks"></a>コメント  
 既定では、`#import` を使用すると、タイプ ライブラリのすべてのインターフェイスのスマート ポインター宣言を取得できます。 これらのスマート ポインターは型[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)です。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)