---
title: "NMAKE の致命的なエラー U1064 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1064
dev_langs:
- C++
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20b6c767145176c459d0b70d96842223218cd0b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1064"></a>NMAKE の致命的なエラー U1064
MAKEFILE が見つかりません、また指定したターゲット  
  
 メイクファイルまたはターゲット (nmake の) のコマンドラインが指定されませんでしたし、現在のディレクトリにはメイクファイルをという名前のファイルが含まれていませんでした。  
  
 NMAKE では、メイクファイルまたはコマンド ライン ターゲット (または両方) が必要です。 Nmake メイクファイルを使用できるようにするには、/F オプションを指定するか、現在のディレクトリのメイクファイルをという名前のファイルを配置します。 NMAKE は、メイクファイルが指定されていない場合は、推論規則を使用して、コマンドラインのターゲットを作成できます。