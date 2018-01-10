---
title: "コンパイラ エラー C3180 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3180
dev_langs: C++
helpviewer_keywords: C3180
ms.assetid: 5281f583-7df7-418a-8507-d4da67ed6572
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4df29d0a9927526b8bc3ec80bc26cf82858e9592
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3180"></a>コンパイラ エラー C3180
'type name': 名前は 'limit' 文字のメタデータの限度を超えています  
  
 コンパイラでは、メタデータ内のマネージ型の名前が切り捨てられます。 切り捨てを行った後、この型はで使用できなくなります、`#using`ディレクティブ (または、別の言語のと同じ)。  
  
 型名の制限には、すべての名前空間の修飾子が含まれています。