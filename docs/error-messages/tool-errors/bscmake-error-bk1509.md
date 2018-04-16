---
title: "BSCMAKE エラー BK1509 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK1509
dev_langs:
- C++
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4d5fe0a83c5fbc3c4793699975d2045df5fbd8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1509"></a>BSCMAKE エラー BK1509
ヒープ スペースがありません。  
  
 BSCMAKE は、仮想メモリを含め、メモリ不足になりました。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ディスク領域を解放します。  
  
2.  スワップ ファイルのサイズを増やします。  
  
3.  Windows のスワップ ファイルのサイズが増加します。  
  
4.  による/Ei BSCMAKE が必要とするメモリを減らすか、一部を排除/Es 入力ファイルまたはマクロの本体を排除する/Em ください。