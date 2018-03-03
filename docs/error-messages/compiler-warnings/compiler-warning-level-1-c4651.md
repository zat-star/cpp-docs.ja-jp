---
title: "コンパイラの警告 (レベル 1) C4651 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dce099d657341ebc957c95ab0cd14f508f9e36ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4651"></a>コンパイラの警告 (レベル 1) C4651
'定義' プリコンパイル済みヘッダーに定義されていますが、現在のコンパイルではありません。  
  
 このコンパイルされていない場合、プリコンパイル済みヘッダーが生成されたが、定義が指定されました。  
  
 プリコンパイル済みのヘッダー内ではなく、コードの残りの部分定義が有効になります。  
  
 プリコンパイル済みヘッダーがで指定してビルドされていた場合、コンパイラで/Yu コンパイルが指定していない場合にこの警告が生成されます。  /Yu コマンドラインに指定してを追加するには、この警告が解決されます。