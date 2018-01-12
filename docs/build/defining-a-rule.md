---
title: "ルールの定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0d6ca616e3685db36d6d24b339a860eab4c6150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="defining-a-rule"></a>規則の定義
*Fromext*依存ファイルの拡張機能を表すと*toext*ターゲット ファイルの拡張機能を表します。  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>コメント  
 拡張機能は、大文字小文字を区別はありません。 表すマクロを呼び出すことができます*fromext*と*toext*; マクロはプリプロセッサによって展開されます。 ピリオド (.) 前*fromext*行の先頭に置く必要があります。 コロン (:) は、0 個以上のスペースまたはタブに続きます。 これは、スペースまたはタブ、コマンドを指定する、セミコロン (;)、コメントを指定するシャープ記号 (#) または復帰改行文字によってのみ実行できます。 他のスペースは許可されません。 コマンドは、記述ブロックのように指定します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [規則の検索パス](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>参照  
 [推論規則](../build/inference-rules.md)