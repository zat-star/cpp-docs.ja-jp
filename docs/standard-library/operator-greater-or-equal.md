---
title: operator&gt;= | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- operator>=
- std::>=
- std.operator>=
- '>='
- std.>=
- std::operator>=
dev_langs:
- C++
helpviewer_keywords:
- '>= operator, comparing specific objects'
- operator >=
- operator>=
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
caps.latest.revision: 9
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
ms.openlocfilehash: 915c180caefa7f39cc0c9defcff688b3ed6520a0
ms.lasthandoff: 02/24/2017

---
# <a name="operatorgt"></a>operator&gt;=
> [!NOTE]
>  このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。  
  
 **operator>=** をオーバーロードしてテンプレート クラス [Container](../standard-library/sample-container-class.md) の&2; つのオブジェクトを比較します。  
  
## <a name="syntax"></a>構文  
  
```  
 
    template <class Ty>  
bool operator>=(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>戻り値  
 **!**(_*Left* < \_*Right*) を返します。  
  
## <a name="see-also"></a>関連項目  
 [\<sample container>](../standard-library/sample-container.md)


