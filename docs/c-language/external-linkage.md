---
title: "外部リンケージ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: dcd269984d3b56728a5a135a380aacb7efae8c98
ms.lasthandoff: 02/24/2017

---
# <a name="external-linkage"></a>外部リンケージ
ID のファイル スコープ レベルの最初の宣言で **static** ストレージ クラス指定子を使用していない場合、オブジェクトに外部リンケージがあります。  
  
 関数の ID の宣言に *storage-class-specifier* がない場合、そのリンケージは、*storage-class-specifier* `extern` で宣言されている場合とまったく同じように決定されます。 オブジェクトの ID の宣言にファイル スコープがあり、*storage-class-specifier* が含まれていない場合、リンケージは外部になります。  
  
 外部リンケージを持つ識別子の名前は、外部リンケージを持つ同じ名前の他の宣言で指定されるものと同じ関数またはデータ オブジェクトを指定します。 2 つの宣言を同じ翻訳単位または異なる翻訳単位に配置できます。 オブジェクトまたは関数にグローバル有効期間もある場合、オブジェクトまたは関数はプログラム全体で共有されます。  
  
## <a name="see-also"></a>関連項目  
 [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)
