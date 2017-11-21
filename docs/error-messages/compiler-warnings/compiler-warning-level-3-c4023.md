---
title: "コンパイラの警告 (レベル 3) C4023 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4023
dev_langs: C++
helpviewer_keywords: C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 170a76381dac09ad0543b30e71aedb306b514379
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4023"></a>コンパイラの警告 (レベル 3) C4023
'symbol' : _based ポインターがプロトタイプ宣言されていない関数へ渡されます : パラメーター番号  
  
 プロトタイプ宣言されていない関数に _based ポインターを渡すと、ポインターが正規化され、予期しない結果になります。  
  
 _based ポインターを渡されるプロトタイプ関数を使用すると、この警告が解決することがあります。