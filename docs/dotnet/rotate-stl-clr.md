---
title: "回転 (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::rotate
dev_langs:
- C++
helpviewer_keywords:
- rotate function [STL/CLR]
ms.assetid: 61dc89a9-a928-4eb3-89d6-2f5927df0f13
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 82ede9e68bc15e9e534e1cec75930809197fc133
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rotate-stlclr"></a>rotate (STL/CLR)
2 つの隣接する範囲の要素を交換します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt> inline  
    void rotate(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`rotate`です。 詳細については、次を参照してください。[回転](../standard-library/algorithm-functions.md#rotate)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)