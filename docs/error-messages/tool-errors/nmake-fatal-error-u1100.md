---
title: "NMAKE の致命的なエラー U1100 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1100
dev_langs: C++
helpviewer_keywords: U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b489c1276b62e28fd540df369a84835c98da87e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE の致命的なエラー U1100
マクロ 'macroname' はバッチ ルール 'rule' のコンテキストでは無効  
  
 NMAKE が $ ではない特殊なファイル マクロをバッチ モードの規則のコマンドのブロック直接的または間接的に参照する場合、このエラーを生成 < です。  
  
 $< は、使用できる唯一のバッチ モードの規則のマクロです。