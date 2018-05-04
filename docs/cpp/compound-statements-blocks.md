---
title: 複合ステートメント (ブロック) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a8823935ee2f871cdc033aec23f05fc108244e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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