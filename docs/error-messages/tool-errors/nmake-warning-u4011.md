---
title: "NMAKE の警告 U4011 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ae15a3912fe3172e9dec98e1a90a3a262c47117
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4011"></a>NMAKE の警告 U4011
'target': 依存ファイルの一部が使用できます。ターゲットはビルドされません。  
  
 指定されたターゲットの依存関係が存在しませんまたはのいずれかが最新でないと、依存ファイルを更新するためのコマンドには、0 以外の終了コードが返されました。 /K オプション、nmake (nmake の) セッションが終了した場合は、終了コード 1 を発行して、ビルドの関連付けられていない部分の処理を続行します。  
  
 この警告は、前に警告する[U4010](../../error-messages/tool-errors/nmake-warning-u4010.md)に作成または更新に失敗した依存します。