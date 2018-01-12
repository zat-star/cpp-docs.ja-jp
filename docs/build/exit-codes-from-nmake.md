---
title: "NMAKE の終了コード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13cbe4806d8b3960cbf80df41c7cce6e7657ba7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exit-codes-from-nmake"></a>NMAKE で返される終了コード
(Nmake の) には、次の終了コードが返されます。  
  
|コード|説明|  
|----------|-------------|  
|0|エラー (場合によっては警告)|  
|1|(発行/K を使用する場合にのみ) ビルドが不完全です。|  
|2|プログラム エラー: 次のいずれかの原因として考えられます。|  
||-メイクファイルで構文エラー|  
||のコマンドからエラーまたは終了コード|  
||-ユーザーにより中断|  
|4|システム エラー: メモリ不足|  
|255|ターゲットが最新でありません (/Q を使用する場合にのみ発行)|  
  
## <a name="see-also"></a>参照  
 [NMAKE の実行](../build/running-nmake.md)