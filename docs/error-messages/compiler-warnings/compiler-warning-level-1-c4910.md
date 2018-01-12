---
title: "コンパイラの警告 (レベル 1) C4910 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f758e2e15d5492724e9b819622202831d4e9f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910
'\<識別子 >': '関数' と 'extern' 明示的なインスタンス化に互換性がありません  
  
 という名前の明示的なテンプレート インスタンス化*\<識別子 >*両方によって変更、`__declspec(dllexport)`と`extern`キーワード。 ただし、これらのキーワードは、相互に排他的です。 `__declspec(dllexport)` キーワードは、テンプレート クラスのインスタンス化を意味しますが、 `extern` キーワードは、テンプレート クラスを自動的にインスタンス化しないことを意味します。  
  
## <a name="see-also"></a>参照  
 [明示的なインスタンス化](../../cpp/explicit-instantiation.md)   
 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)   
 [一般的な規則と制約](../../cpp/general-rules-and-limitations.md)