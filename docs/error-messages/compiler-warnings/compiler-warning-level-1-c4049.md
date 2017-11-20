---
title: "コンパイラの警告 (レベル 1) C4049 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4049
dev_langs: C++
helpviewer_keywords: C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e749571bcf4c0e1547279a857e50556f766c576
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4049"></a>コンパイラの警告 (レベル 1) C4049
コンパイラの制限: 行番号の出力を中止  
  
 ファイル内の複数の 16,777, 215 (2<sup>24</sup>-1) ソース行です。 コンパイラは、連番が 16,777, 215 を停止します。  
  
 16,777, 215 の行の後のコード。  
  
-   イメージには、行番号のデバッグ情報はありません。  
  
-   いくつかの診断は、不正な行番号で報告されること可能性があります。  
  
-   .asm 一覧 (/FAs) 不正な行番号があります。