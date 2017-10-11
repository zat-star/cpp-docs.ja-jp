---
title: "コンパイラ エラー C2588 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2588
dev_langs:
- C++
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6d71e5bfe442f2b3f2225cd4dc6cb88fc73d24a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2588"></a>コンパイラ エラー C2588
':: ~ identifier': 無効なグローバル デストラクター  
  
 デストラクターは、クラス、構造体、または共用体以外のものに対して定義されます。 これは認められていません。  
  
 このエラーは、不足しているクラス、構造体、または共用体の名前スコープ解決演算子の左側にあるによって発生することができます (`::`) 演算子。  
  
 次の例では、C2588 が生成されます。  
  
```  
// C2588.cpp  
~F();   // C2588  
```
