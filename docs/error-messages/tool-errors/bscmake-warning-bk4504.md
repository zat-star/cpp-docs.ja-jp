---
title: "BSCMAKE の警告 BK4504 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: efe5cf36786171c4a663fb329efbc05b91065c7f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE の警告 BK4504
ファイルに含まれる参照が多すぎます。このソースからのこれ以上の参照は無視されます。  
  
 .Cpp ファイルには、複数の 64,000 シンボル参照が含まれています。 BSCMAKE には、ファイルで 64,000 の参照が検出されたが、これ以上のすべての参照が無視されます。  
  
 問題を解決する 2 つのファイルに分割またはより少ない 64,000 を持つ他のファイルのシンボル参照、またはを使用して、`#pragma component(browser)`プリプロセッサ ディレクティブの特定の参照に対して生成されるシンボルを制限します。 詳細については、次を参照してください。[コンポーネント](../../preprocessor/component.md)します。
