---
title: "リンカー ツールの警告 LNK4037 |Microsoft ドキュメント"
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4037
dev_langs: C++
helpviewer_keywords: LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c93eab2faf81e4cd743eae4befa2f842c100589
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4037"></a>リンカー ツールの警告 LNK4037

>'*シンボル*' がありません。 無視されます。

装飾名*シンボル*を使用して順序付けされませんでした、 [/order](../../build/reference/order-put-functions-in-order.md)プログラムで見つかりませんオプションを指定します。 仕様の確認*シンボル*順序応答ファイルにします。 詳細については、次を参照してください。、 [/ORDER (関数の順序に Put)](../../build/reference/order-put-functions-in-order.md)リンカー オプション。

> [!NOTE]
> 静的関数名は、パブリック シンボル名ではないために、リンクで静的関数を注文することはできません。 ときに**/order**は指定が静的である注文の応答ファイル内の各シンボルに対してこのリンカー警告が生成されるか、見つかりませんでした。