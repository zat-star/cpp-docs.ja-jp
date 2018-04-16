---
title: "画像の書式 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0761acfe02b7d86f9316d06913de15347e9d522
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="image-format"></a>イメージ形式
実行可能イメージの形式は pe 32 + です。 (Dll と Exe) の実行可能イメージは、静的なイメージのデータに対処する 32 ビットの変位相対アドレスを使用できるように、2 ギガバイト単位の最大サイズに制限されます。 このデータには、インポート アドレス テーブル、文字列定数、グローバルな静的データ、およびなどが含まれています。  
  
## <a name="see-also"></a>参照  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)