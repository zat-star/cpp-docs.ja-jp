---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs: C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cbfe1f002c038f5dcc1b3a024891780d56c3572c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool
`vector<bool>::reference` から `bool` への暗黙の変換を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
operator bool() const;
```  
  
## <a name="return-value"></a>戻り値  
 [vector\<bool>](../standard-library/vector-bool-class.md) オブジェクトの要素のブール値。  
  
## <a name="remarks"></a>コメント  
 `vector<bool>` オブジェクトはこの演算子では変更できません。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<vector>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [vector\<bool>::reference クラス](../standard-library/vector-bool-reference-class.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)

