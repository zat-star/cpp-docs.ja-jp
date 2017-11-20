---
title: '&lt;ccomplex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <ccomplex>
dev_langs: C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 677c2ec66bdf8f7b210f96a30aaf7722b43fb035
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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



