---
title: "仮想 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- virtual_cpp
- virtual
dev_langs:
- C++
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 851f911dd7c49df1d685afe63ef5134cf0d5f175
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="virtual-c"></a>virtual (C++)
`virtual` キーワードは仮想関数または仮想基底クラスを宣言します。  
  
## <a name="syntax"></a>構文  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### <a name="parameters"></a>パラメーター  
 `type-specifiers`  
 仮想メンバー関数の戻り値の型を指定します。  
  
 `member-function-declarator`  
 メンバー関数を宣言します。  
  
 `access-specifier`  
 基底クラスへのアクセス レベルとして `public`、`protected`、または `private` を定義します。 `virtual` キーワードの前または後に指定できます。  
  
 `base-class-name`  
 以前に宣言されたクラス型を識別します。  
  
## <a name="remarks"></a>コメント  
 参照してください[仮想関数](../cpp/virtual-functions.md)詳細についてはします。  
  
 また、次のキーワードを参照してください:[クラス](../cpp/class-cpp.md)、[プライベート](../cpp/private-cpp.md)、[パブリック](../cpp/public-cpp.md)と[保護](../cpp/protected-cpp.md)です。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)
