---
title: "リンカー ツールの警告 LNK4197 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4197
dev_langs: C++
helpviewer_keywords: LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1fadbf2ba5b18004f0e89142c88a68437842a92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4197"></a>リンカー ツールの警告 LNK4197
'exportname' が複数回; 指定のエクスポートします。最初の仕様を使用してください。  
  
 エクスポートが複数の指定とさまざまな方法です。 リンカーは、最初の仕様を使用し、残りの部分を無視します。  
  
 C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。  
  
 エクスポートが複数回にまったく同じ方法を指定する場合、リンカーは警告を発行しません。  
  
 たとえば、.def ファイルの次の内容では、この警告が発生します。  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  同じエクスポートが指定されているコマンドラインで両方 (エクスポートによって:) および .def ファイル  
  
2.  同じエクスポートは、異なる属性を持つ .def ファイルに 2 回表示されます。