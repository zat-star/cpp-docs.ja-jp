---
title: "方向フラグ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0a43bac113c013ecb93f5b6e84aa2075a052f8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="direction-flag"></a>方向フラグ
方向フラグは、Intel 80x86 プロセッサ固有の CPU フラグです。 MOVS、MOVSD、MOVSW などの REP (繰り返し) プレフィックスを使用するすべてのアセンブリ命令に適用されます。 方向フラグがオフの場合、適用される命令に渡されたアドレスは増加します。  
  
 C ランタイム ルーチンでは、方向フラグがオフになっていることを前提としています。 C ランタイム関数とともに他の関数を使用している場合は、他の関数が方向フラグを変更しないようにする、または方向フラグを元の状態に復元する必要があります。 入力時に方向フラグがオフになっていると、ランタイム コードがより高速かつ効率的になります。  
  
 文字列操作ルーチンやバッファー操作ルーチンなどの C ランタイム ライブラリ関数では、方向フラグがオフになっていることを想定してあります。  
  
## <a name="see-also"></a>参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)