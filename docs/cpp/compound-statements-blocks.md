---
title: "複合ステートメント (ブロック) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs:
- C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: 6
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
ms.openlocfilehash: 9dc28fde0ab2cf5b21771347554d0c664b7f462d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="compound-statements-blocks"></a>複合ステートメント (ブロック)
複合ステートメントは、中かっこで囲まれた 0 個以上のステートメントで構成されます (**{}**)。 複合ステートメントは、ステートメントが想定される場所で使用できます。 複合ステートメントは一般に "ブロック" と呼ばれます。  
  
## <a name="syntax"></a>構文  
  
```  
  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>コメント  
 次の例として、複合ステートメントを使用して、*ステートメント*の一部、**場合**ステートメント (を参照してください[if ステートメント](../cpp/if-else-statement-cpp.md)構文の詳細について)。  
  
```  
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
{
    Balance -= Amount;  
}
```  
  
> [!NOTE]
>  宣言が内のステートメントのいずれかを指定できます、宣言は、ステートメントであるため、*ステートメント リスト*です。 その結果、複合ステートメント内で宣言されているが、明示的に静的として宣言されていない名前には、ローカルなスコープと (オブジェクトの場合) 有効期間があります。 参照してください[スコープ](../cpp/scope-visual-cpp.md)ローカル スコープの名前の処理方法の詳細。  
  
## <a name="see-also"></a>関連項目  
 [C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)
