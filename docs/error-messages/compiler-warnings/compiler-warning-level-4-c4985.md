---
title: "コンパイラの警告 (レベル 4) C4985 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4a36692420ea9d5547f236c1e5dfeaa269afbb67
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4985"></a>コンパイラの警告 (レベル 4) C4985
'symbol name': 前の宣言に属性が存在しません。  
  
 現在のメソッドの宣言または定義の Microsoft ソース コード注釈言語 (SAL) の注釈が、前の宣言の注釈と異なります。 メソッドの定義と宣言では同じ SAL 注釈を使用する必要があります。  
  
 SAL はユーザーが使用できる注釈のセットを提供して、関数が自身のパラメーターをどのように使用するかを記述します。つまり、これらの注釈は、関数がそのパラメーターについて何を前提としているか、関数が終了時に何を保証するかを示します。 注釈は sal.h ヘッダー ファイルで定義されています。  
  
 通知されるまで、SAL マクロは、プロジェクトには展開されません、 [/analyze](../../build/reference/analyze-code-analysis.md)フラグを指定します。 **/analyze**を指定しないと警告またはエラーが表示されない場合でも、 **/analyze**を指定すると、コンパイラは C4985 をスローする可能性があります。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  メソッドの定義と、そのすべての宣言で、同じ SAL 注釈を使用します。  
  
## <a name="see-also"></a>関連項目  
 [SAL 注釈](../../c-runtime-library/sal-annotations.md)
