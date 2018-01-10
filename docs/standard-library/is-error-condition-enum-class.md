---
title: "is_error_condition_enum クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: system_error/std::is_error_condition_enum
dev_langs: C++
helpviewer_keywords: is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8a2fc2d8a353b3e1c2200dcacedfaeadcfa95d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum クラス
[error_condition](../standard-library/error-condition-class.md) をテストする型述語を表します。  
  
## <a name="syntax"></a>構文  
  
```
template <_Enum>
class is_error_condition_enum;
```  
  
## <a name="remarks"></a>コメント  
 型 `_Enum` が型 `error_condition` のオブジェクトを格納するのに適した列挙型の値である場合、この[型述語](../standard-library/type-traits.md)のインスタンスは true を保持します。  
  
 ユーザー定義型のこの型に特殊化を追加できます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<system_error>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)



