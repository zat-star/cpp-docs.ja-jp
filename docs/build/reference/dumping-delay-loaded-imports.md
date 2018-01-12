---
title: "遅延読み込みしたインポートのダンプ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3800d4863bc1aa3e3c847ff0cea886be2fede985
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dumping-delay-loaded-imports"></a>遅延読み込みしたインポートのダンプ
遅延読み込みしたインポートのダンプを使用して[dumpbin/imports](../../build/reference/imports-dumpbin.md)標準インポートよりも少しずつ異なる情報を表示します。 これらは、ダンプ/imports の独自のセクションに分離され、明示的に遅延読み込みしたインポートとしてラベルが付けられます。 イメージに存在する情報をアンロードする場合は、それが表示されます。 バインド情報がある場合は、インポートのバインド アドレスと DLL のターゲットの日付/時刻スタンプが表示されます。  
  
## <a name="see-also"></a>参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)