---
title: "コンパイラの警告 (レベル 1) C4951 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 199df135d5d2c00255037e5a1b31db80e2683d4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4951"></a>コンパイラの警告 (レベル 1) C4951
プロファイル データ が収集されてから、'function' が編集されました。関数のプロファイル データは使用されません。  
  
 [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)への入力モジュールの関数が編集されたため、プロファイル データが無効になりました。 入力モジュールは、 **/LTCG:PGINSTRUMENT** の後に再コンパイルされ、***/LTCG:PGINSTRUMENT***の操作時にモジュールに含まれていたものとは異なる制御フローを使用した関数 ( **function** ) が含まれています。  
  
 これは、情報提供の警告です。 この警告を解決するには、 **/LTCG:PGINSTRUMENT**を実行してすべてのテストを再実行し、 **/LTCG:PGOPTIMIZE**を実行します。  
  
 **/LTCG:PGOPTIMIZE** が使用されていた場合、この警告はエラーに置き換わることがあります。