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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 807574f0f94f989726ca19d3260b9668f6c84055
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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