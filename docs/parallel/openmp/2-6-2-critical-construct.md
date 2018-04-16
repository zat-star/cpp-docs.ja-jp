---
title: "2.6.2 critical コンストラクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c658b32536404dde1a693582e78bfbedc2823b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="262-critical-construct"></a>2.6.2 critical コンストラクト
**重大**ディレクティブは、一度に 1 つのスレッドに関連付けられている構造化ブロックの実行を制限する構成要素を識別します。 構文、**重大**ディレクティブは、次のようにします。  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 省略可能な*名前*重要な領域を識別するために使用可能性があります。 重要な領域を識別するために使用の識別子は外部リンケージを持ちますされ、ラベル、タグ、メンバー、および通常の識別子で使用される名前空間とは別の名前空間には。  
  
 スレッドは、他のスレッドが同じ名前の重要な領域 (任意の場所でプログラム) を実行していないまでに、重要な領域の先頭に待機します。 名前のないすべて**重大**ディレクティブが指定されていない名前が同じものにマップします。