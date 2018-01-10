---
title: "複合ステートメント (ブロック) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs: C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36dc3c25d5f8bbd37ebfaa3458c07f6948492817
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)