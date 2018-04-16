---
title: "コンパイラの警告 (レベル 3) C4023 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4023
dev_langs:
- C++
helpviewer_keywords:
- C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e22ba0ed3d91f75ba73e68817611302d15fa2039
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4023"></a>コンパイラの警告 (レベル 3) C4023
'symbol' : _based ポインターがプロトタイプ宣言されていない関数へ渡されます : パラメーター番号  
  
 プロトタイプ宣言されていない関数に _based ポインターを渡すと、ポインターが正規化され、予期しない結果になります。  
  
 _based ポインターを渡されるプロトタイプ関数を使用すると、この警告が解決することがあります。