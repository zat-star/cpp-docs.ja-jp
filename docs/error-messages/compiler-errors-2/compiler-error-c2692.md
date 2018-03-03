---
title: "コンパイラ エラー C2692 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9253bf70204bfded06189b6688405cabc43bdcf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2692"></a>コンパイラ エラー C2692
'function_name': 完全なプロトタイプ関数が C コンパイラで必要な '/clr' オプション  
  
 マネージ コードを .NET 用にコンパイルするときに、C コンパイラには、ANSI 関数宣言が必要です。 さらに、関数がパラメーターをとらない場合必要があります明示的に宣言する必要が`void`パラメーターの型として。