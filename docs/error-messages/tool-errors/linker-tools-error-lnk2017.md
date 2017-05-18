---
title: "リンカ ツール エラー LNK2017 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2017
dev_langs:
- C++
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
caps.latest.revision: 7
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
ms.openlocfilehash: bd4a94411967a93d84311c89cbde1e48096c8047
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2017"></a>リンカ ツール エラー LNK2017
'symbol' の再配置 'セグメント' への再配置は無効です。  
  
 32 ビット アドレスの 64 ビット イメージを構築しようとするとします。 これを行うには、次の操作を行う必要があります。  
  
-   固定の読み込みアドレスを使用します。  
  
-   イメージは、3 GB に制限します。  
  
-   指定[への再配置](../../build/reference/largeaddressaware-handle-large-addresses.md)します。
