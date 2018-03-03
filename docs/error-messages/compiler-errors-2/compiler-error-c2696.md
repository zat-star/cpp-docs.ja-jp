---
title: "コンパイラ エラー C2696 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4d6efbf8dcf10d1608bb1a54b843a49d42cb22a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2696"></a>コンパイラ エラー C2696
マネージ型 'type' の一時オブジェクトを作成することはできません。  
  
参照`const`アンマネージ プログラム コンパイラ コンス トラクターを呼び出すし、スタック上に一時オブジェクトを作成することが原因です。 ただし、マネージ クラスは、スタックに作成されません。  
  
C2696 は古い形式のコンパイラ オプションを使用して到達のみ**/clr:oldSyntax**です。  
