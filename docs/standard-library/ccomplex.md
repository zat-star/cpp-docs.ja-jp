---
title: '&lt;ccomplex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <ccomplex>
dev_langs:
- C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb279929a460c43bb7ca564615fde494e3a0eb99
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;
C++ 標準ライブラリ ヘッダー [\<complex>](../standard-library/complex.md) をインクルードします。これにより、標準 C ライブラリ ヘッダー \<complex.h> がインクルードされ、関連する名前が `std` 名前空間に追加されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
#include <ccomplex>  
  
```  
  
## <a name="remarks"></a>コメント  
 このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。  
  
 \<complex.h> で宣言される名前 `clog` は `std` 名前空間に定義されていません。これは、[\<iostream>](../standard-library/iostream.md) で宣言されている `clog` と競合する可能性があるためです。  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)



