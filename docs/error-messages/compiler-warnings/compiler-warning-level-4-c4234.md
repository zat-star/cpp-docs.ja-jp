---
title: "コンパイラの警告 (レベル 4) C4234 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4234
dev_langs: C++
helpviewer_keywords: C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68f4b2c3b51caf5e0438c2ead293823885b73157
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4234"></a>コンパイラの警告 (レベル 4) C4234
標準の拡張機能を使用します将来使用するために予約されています 'keyword' キーワード。  
  
 コンパイラは、使用するキーワードをまだ実装されていません。  
  
 この警告は、自動的にエラーになります。 この動作を変更する場合は、使用[#pragma 警告](../../preprocessor/warning.md)です。 たとえば、レベル 4 の警告の問題、c4234  
  
```  
#pragma warning(2:4234)  
```  
  
 をソース コード ファイルに追加します。