---
title: "コンパイラ エラー C2458 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2458
dev_langs: C++
helpviewer_keywords: C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 511d6685ff6447793baa14468f6414fec99a3772
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2458"></a>コンパイラ エラー C2458
'identifier': 定義内で再定義されています。  
  
 クラス、構造体、共用体、または列挙型がそれ自体の宣言で再定義します。  
  
 次の例では、C2458 生成されます。  
  
```  
// C2458.cpp  
class C {  
   enum i { C };   // C2458  
};  
```