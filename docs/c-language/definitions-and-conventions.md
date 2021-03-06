---
title: "定義と規則 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02a6cc8ffcb5748544191673de8f07e87449e806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="definitions-and-conventions"></a>定義と規則
終端は構文定義内のエンドポイントです。 他の解決はありません。 終端には、予約語およびユーザー定義の識別子が含まれます。  
  
 非終端要素は、構文内でプレースホルダーになっており、この構文概要の他の場所で定義されます。 定義は再帰的に行うことができます。  
  
 省略可能な構成要素には添字 "opt" を付けます。 たとえば、オブジェクトに適用された  
  
```  
  
{  
expression <SUB>opt</SUB> }  
```  
  
 中かっこで囲まれた省略可能な式を示します。  
  
 構文の表記規則により、構文のコンポーネントごとに異なるフォント属性が使用されます。 シンボルとフォントは次のとおりです。  
  
|属性|説明|  
|---------------|-----------------|  
|*nonterminal*|斜体は、非終端要素を示します。|  
|**const**|太字で示される終端要素は、示されたとおりに入力する必要があるリテラル予約語およびシンボルです。 このコンテキストの文字は、常に大文字と小文字が区別されます。|  
|opt|後ろに opt が続く非終端要素は、常に省略可能です。|  
|既定のタイプフェイス|このタイプフェイスで記述されているか、示されているセット内の文字は、C ステートメント内で終端要素として使用できます。|  
  
 非終端要素に続くコロン (**:**) は、定義の説明を示します。 単語 "one of" で始まる場合を除き、代替定義は個別の行に表示されます。  
  
## <a name="see-also"></a>参照  
 [C 言語の構文概要](../c-language/c-language-syntax-summary.md)