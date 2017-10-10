---
title: "致命的なエラー C1005 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1005
dev_langs:
- C++
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e558112619e5cbefd641e7906df941d0869ceddb
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1005"></a>致命的なエラー C1005
コンパイラの中間ファイルの文字列がバッファーの大きさを超えました。  
  
 コンパイラの中間ファイル内の文字列で、バッファーがオーバーフローしました。  
  
 このエラーは、 [/Fd](../../build/reference/fd-program-database-file-name.md) または [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) コンパイラ オプションに渡すパラメーターが 256 バイトを超えている場合に発生することがあります。
