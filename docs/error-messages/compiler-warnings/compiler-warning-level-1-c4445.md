---
title: "コンパイラの警告 (レベル 1) C4445 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4445
dev_langs:
- C++
helpviewer_keywords:
- C4445
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e351d23d943d53cef3184a826fecc90c5a28359
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4445"></a>コンパイラの警告 (レベル 1) C4445
'function': WinRT またはマネージ型で、仮想関数をプライベートにすることはできません  
  
 仮想関数がプライベートである場合、派生型からアクセスできなくなります。 このエラーを解決するには、仮想メンバー関数のアクセシビリティをプロテクトまたはパブリックに変更します。