---
title: "コンパイラの警告 (レベル 1) C4659 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4659
dev_langs: C++
helpviewer_keywords: C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: abaef666a5553969ab1290118b8668c50c2bba3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4659"></a>コンパイラの警告 (レベル 1) C4659
\#プラグマ ': 予約されたセグメント 'segment' の使用には、動作が定義されていませんが、#pragma comment (linker,...) を使用します。  
  
 オプションをリンカーに渡す .drectve オプションが使用されました。 代わりにプラグマを使用して[コメント](../../preprocessor/comment-c-cpp.md)リンカー オプションを渡すためです。  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```