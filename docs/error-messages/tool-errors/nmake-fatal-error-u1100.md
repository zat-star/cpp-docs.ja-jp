---
title: "NMAKE の致命的なエラー U1100 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1100
dev_langs:
- C++
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7c4a42e47a29775bb53fdc0fd2f25c7bdc252f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE の致命的なエラー U1100
マクロ 'macroname' はバッチ ルール 'rule' のコンテキストでは無効  
  
 NMAKE が $ ではない特殊なファイル マクロをバッチ モードの規則のコマンドのブロック直接的または間接的に参照する場合、このエラーを生成 < です。  
  
 $< は、使用できる唯一のバッチ モードの規則のマクロです。