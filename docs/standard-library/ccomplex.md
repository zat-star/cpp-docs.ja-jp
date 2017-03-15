---
title: '&lt;ccomplex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <ccomplex>
dev_langs:
- C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 15
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 63374ad7a56060da78621e9543f38dcfe8a06ae7
ms.lasthandoff: 02/24/2017

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
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)




