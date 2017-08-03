---
title: "リンケージなし | Microsoft Docs"
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
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 28491a83dd80d78ecd15702fd50ce8796cfa0ca9
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="no-linkage"></a>リンケージなし
ブロック内の識別子の宣言に `extern` ストレージ クラス指定子が含まれていない場合、その識別子はリンケージを持たず、関数に対して一意になります。  
  
 次の識別子にはリンケージがありません。  
  
-   オブジェクトまたは関数以外として宣言された識別子  
  
-   関数パラメーターとして宣言された識別子  
  
-   `extern` ストレージ クラス指定子なしで宣言されたオブジェクトのブロック スコープ指定子  
  
 識別子にリンケージがない場合、同じスコープ レベルで同じ名前を再度 (宣言子または型指定子で) 宣言すると、シンボルの再定義エラーが発生します。  
  
## <a name="see-also"></a>関連項目  
 [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)
