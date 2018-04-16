---
title: "NMAKE の致命的なエラー U1099 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bf8d662960e5857686f3f8301cc8481f350d4b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE の致命的なエラー U1099
スタック オーバーフロー  
  
 処理中のメイクファイルが複雑すぎるため、現在のスタック割り当て (nmake の)。 NMAKE は、0x3000 (12 K) の割り当てがあります。  
  
 NMAKE のスタック割り当てを増やすを実行、 [editbin/stack](../../build/reference/stack.md)ユーティリティの大きなスタック オプションを使用します。  
  
 **editbin/STACK:reserve (nmake の)。EXE**  
  
 ここで*予約*数値を現在のスタック割り当て (nmake の) を超えています。