---
title: "identity 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- utility/std::identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: dd840dba1de5e389e2fa1d8585d677d3be255f8e
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="identity-structure"></a>identity 構造体
テンプレート パラメーターの型定義を指定する構造体。  
  
## <a name="syntax"></a>構文  
```  
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };  
```  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|指定する値。|  
  
## <a name="remarks"></a>コメント  
 このクラスにはパブリック型の定義 `type` が含まれています。これは、テンプレート パラメーターの型と同じです。 必要な型が関数パラメーターに設定されるようにするには、テンプレート関数 [forward](../standard-library/utility-functions.md#forward) と組み合わせて使用します。  
  
 このクラスは、以前のコードとの互換性を保つために、引数 `left` を返すidentity 関数 `operator()` も定義します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<utility>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<utility>](../standard-library/utility.md)




