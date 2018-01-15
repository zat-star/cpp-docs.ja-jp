---
title: "char_traits&lt;char32_t&gt; 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
dev_langs: C++
helpviewer_keywords: char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a6b315da89f94da232f5d0ed44a9e3351f41824
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="chartraitsltchar32tgt-struct"></a>char_traits&lt;char32_t&gt; 構造体
テンプレート構造体 **char_traits\<CharType>** を `char32_t` 型の要素に特殊化した構造体。  
  
## <a name="syntax"></a>構文  
  
```
template <>  
struct char_traits<char32_t>;
```  
  
## <a name="remarks"></a>コメント  
 特殊化により、構造体でこの型 `char32_t` のオブジェクトを操作するライブラリ関数を利用できます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<string>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [\<string>](../standard-library/string.md)   
 [char_traits 構造体](../standard-library/char-traits-struct.md)