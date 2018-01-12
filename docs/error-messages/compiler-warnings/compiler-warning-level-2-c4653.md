---
title: "コンパイラの警告 (レベル 2) C4653 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4653
dev_langs: C++
helpviewer_keywords: C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8eb855e1c11136cd88c1c1e796d9759581e3ceb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4653"></a>コンパイラの警告 (レベル 2) C4653
コンパイラ オプション 'option' はプリコンパイル済みヘッダーです。現在のコマンド ライン オプションが無視されます。  
  
 プリコンパイル済みヘッダーの使用で指定されたオプション ([/Yu](../../build/reference/yu-use-precompiled-header-file.md)) オプションがプリコンパイル済みヘッダーの作成時に指定されたオプションと矛盾しています。 このコンパイルでは、プリコンパイル済みヘッダーの作成時に指定されたオプションを使用します。  
  
 ときに、さまざまなオプションの値、パックの構造体に、この警告が発生することが ([/Zp](../../build/reference/zp-struct-member-alignment.md)) プリコンパイル済みヘッダーのコンパイル時に指定されました。