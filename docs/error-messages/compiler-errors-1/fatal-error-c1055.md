---
title: "致命的なエラー C1055 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1055
dev_langs: C++
helpviewer_keywords: C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 68b9dc5ac8a574111a678086a03e2760941e766f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1055"></a>致命的なエラー C1055
コンパイラの制限: キーが足りません  
  
 ソース ファイルには、多数のシンボルが含まれています。 コンパイラは、シンボル テーブルのハッシュ キー不足になりました。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ソース ファイルを小さなファイルに分割します。  
  
2.  不要なヘッダー ファイルを削除します。  
  
3.  新しいファイルを作成する代わりに一時とグローバル変数を再利用できます。