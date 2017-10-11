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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 97937579c12730fecfa89c69d9e7cf51229b5c6c
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2026"></a>コンパイラ エラー C2026
文字列が大きすぎるため、末尾の文字は切り捨てられます  
  
 文字列で 16380 1 バイト文字の制限を超えていました。  
  
 隣接する文字列の連結された場合、前に、文字列はで 16380 1 バイト文字より長くすることはできません。  
  
 この長さが約 50% の Unicode 文字列もこのエラーを生成します。  
  
 次のように定義された文字列があれば、C2026 が生成されます。  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 分割できますとおり。  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 カスタム リソースまたは外部ファイルで非常に大きな文字列リテラル (32 K 以上) を格納することがあります。 参照してください[新しいカスタム リソースまたはデータ リソースを作成する](../../windows/creating-a-new-custom-or-data-resource.md)詳細についてはします。
