---
title: "auto_rename |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: auto_rename
dev_langs: C++
helpviewer_keywords: auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76062a4a1eb44019b8677692ba895c5dcf9850cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="autorename"></a>auto_rename
**C 固有の仕様**  
  
 潜在的な名前の競合を解決するため、変数名に 2 つのアンダースコア (__) を追加して C++ の予約語の名前を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
auto_rename  
```  
  
## <a name="remarks"></a>コメント  
 この属性は、変数名として C++ の予約語 (キーワードまたはマクロ) を使用しているタイプ ライブラリをインポートするときに使用します。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)