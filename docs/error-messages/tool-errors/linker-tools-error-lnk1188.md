---
title: "リンカ ツール エラー LNK1188 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1188
dev_langs: C++
helpviewer_keywords: LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 81d2988742eb9e8cd6aef134510ac8272d3dd27c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1188"></a>リンカ ツール エラー LNK1188
BADFIXUPSECTION:: 無効な fixup ターゲット 'symbol';考えられる長さのセクションは 0  
  
 VxD リンク中に再配置のターゲットは、セクションがありませんでした。 Link386 (以前のバージョン)、(MASM GROUP ディレクティブによって生成された) OMF グループ レコードが 0 長セクションには、長さが 0 以外の別のセクションを結合に使用されている可能性があります。 COFF 形式は、長さゼロのセクションでは、GROUP ディレクティブをサポートしていません。 リンクでは、この種類の OMF オブジェクトが COFF に自動的に変換、このエラーが発生する可能性があります。