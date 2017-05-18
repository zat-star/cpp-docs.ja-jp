---
title: "コンパイラ エラー C2026 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: c429f81c64b7710b7edc2b8540d98e8c790e4062
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2026"></a>コンパイラ エラー C2026
文字列が大きすぎます。後ろの文字が切り捨てられました。  
  
 文字列で 16380 1 バイト文字の制限を超えていました。  
  
 隣接する文字列の連結された場合、前に、文字列はで 16380 1 バイト文字より長くすることはできません。  
  
 この長さが約&50;% の Unicode 文字列もこのエラーを生成します。  
  
 次のように定義されている文字列を使っている場合は、c2026 エラーが生成されます。  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 ことが分割して次のようになります。  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 カスタム リソースまたは外部ファイル内の非常に大きな文字列リテラル (32 K またはそれ以上) を格納する可能性があります。 参照してください[新しいカスタム リソースまたはデータ リソースを作成する](../../windows/creating-a-new-custom-or-data-resource.md)の詳細。
