---
title: "generate_n (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::generate_n
dev_langs: C++
helpviewer_keywords: generate_n function [STL/CLR]
ms.assetid: 2f56e649-7a6f-4861-ae49-d0b25f5cd50c
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 15a6d68913bd64d8f5022efa4344c1e3749451f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="generaten-stlclr"></a>generate_n (STL/CLR)
範囲内の指定された数の要素に関数オブジェクトによって生成される値を割り当て、最後に割り当てられた値を 1 つ超えた位置を返します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _OutIt, class _Diff, class _Fn0> inline  
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`generate_n`です。 詳細については、次を参照してください。 [generate_n](../standard-library/algorithm-functions.md#generate_n)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)