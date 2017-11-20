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
ms.openlocfilehash: ff07a7fd5af7c9e4d73d9a4ce679edc7ab5e6b43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4192"></a>コンパイラの警告 (レベル 3) C4192
タイプ ライブラリ 'library' のインポート中に 'name' を自動的に除外  
  
 A`#import`ライブラリには、項目が含まれています*名前*、つまりも Win32 システム ヘッダーで定義します。 などの制限によりタイプ ライブラリの名**IUnknown** GUID は、多くの場合で定義されているタイプ ライブラリでは、システム ヘッダーの定義を複製します。 `#import`これらの項目を検出し、.tlh ファイルと .tli ヘッダー ファイルに組み込むことを拒否します。  
  
 この動作をオーバーライドするには使用`#import`属性[no_auto_exclude](../../preprocessor/no-auto-exclude.md)と[include()](../../preprocessor/include-parens.md)です。