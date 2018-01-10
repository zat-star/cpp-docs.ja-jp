---
title: "コンパイラの警告 (レベル 1) C4729 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4729
dev_langs: C++
helpviewer_keywords: C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 57d6d5dc95ce3ef9cf4890b93ef1ab3abe2d6601
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4729"></a>コンパイラの警告 (レベル 1) C4729
フロー グラフ ベースの警告の関数が大きすぎます。  
  
 この警告が生成されるのは、関数が大きすぎてコンパイルできず、警告を生成する状況を確実にチェックできない場合です。 この警告は、 [/Od](../../build/reference/od-disable-debug.md) コンパイラ オプションを使用している場合にのみ生成されます。  
  
 この警告を解決するには、関数を小さい関数に分割します。