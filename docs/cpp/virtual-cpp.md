---
title: "仮想 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- virtual_cpp
- virtual
dev_langs: C++
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 041939197f18861d27d1f99708e27415de2b7787
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)