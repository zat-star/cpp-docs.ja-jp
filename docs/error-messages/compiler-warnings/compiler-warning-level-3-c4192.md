---
title: "コンパイラの警告 (レベル 3) C4192 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4192
dev_langs: C++
helpviewer_keywords: C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 022c0e0aac8d231963ddf6d5d3715d55f726a8b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4192"></a>コンパイラの警告 (レベル 3) C4192
タイプ ライブラリ 'library' のインポート中に 'name' を自動的に除外  
  
 A`#import`ライブラリには、項目が含まれています*名前*、つまりも Win32 システム ヘッダーで定義します。 などの制限によりタイプ ライブラリの名**IUnknown** GUID は、多くの場合で定義されているタイプ ライブラリでは、システム ヘッダーの定義を複製します。 `#import`これらの項目を検出し、.tlh ファイルと .tli ヘッダー ファイルに組み込むことを拒否します。  
  
 この動作をオーバーライドするには使用`#import`属性[no_auto_exclude](../../preprocessor/no-auto-exclude.md)と[include()](../../preprocessor/include-parens.md)です。