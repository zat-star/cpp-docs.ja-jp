---
title: "リンカー ツールの警告 LNK4197 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: 6
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3ef9f4ad3822e6fbe3f323fe985b3d4330753df4
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4197"></a>リンカー ツールの警告 LNK4197
'exportname' が複数回; 指定のエクスポートします。最初の仕様を使用してください。  
  
 複数のエクスポートを指定し、さまざまな方法です。 リンカーは、最初の仕様を使用し、残りの部分は無視されます。  
  
 C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。  
  
 エクスポートが複数回にまったく同じ方法を指定する場合、リンカーは警告を発行しません。  
  
 たとえば、.def ファイルの内容を次には、この警告が発生させます。  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  同じエクスポートが指定されているコマンド ラインで両方 (エクスポートによって:) および .def ファイル内  
  
2.  さまざまな属性を .def ファイルで&2; 回、同じエクスポートが表示されます。
