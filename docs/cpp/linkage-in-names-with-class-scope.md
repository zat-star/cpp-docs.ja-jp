---
title: "クラスのスコープを持つ名前にあるリンケージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- classes [C++], scope
- external linkage, scope linkage rules
- class names [C++], linkage
- classes [C++], names
- scope [C++], class names
- class scope [C++], linkage in names with
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8cc10af2fc65de8382d5b8a26ac70cad9b9727e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linkage-in-names-with-class-scope"></a>クラス スコープを持つ名前にあるリンケージ
クラス スコープの名前には、次のリンケージ規則が適用されます。  
  
-   静的クラス メンバーは外部リンケージを持ちます。  
  
-   クラスのメンバー関数は外部リンケージを持ちます。  
  
-   列挙子と `typedef` 名はリンケージを持ちません。  
  
 **Microsoft 固有の仕様**  
  
-   `friend` 関数として宣言された関数には、外部リンケージが必要です。 静的関数を `friend` として宣言すると、エラーが発生します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)