---
title: "コンパイラ エラー C2834 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2834
dev_langs: C++
helpviewer_keywords: C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b85b01fa832b0d14d01b6b7cbb5ef65107177ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2834"></a>コンパイラ エラー C2834
'operator 演算子' はグローバルに修飾する必要があります。  
  
 `new`と`delete`演算子はクラスに関連付けられて、その場所します。 バージョンを選択するスコープ解決演算子を使用することはできません`new`または`delete`別のクラスからです。 複数のフォームを実装する、`new`または`delete`演算子は、余分の仮パラメーターを持つ演算子のバージョンを作成します。