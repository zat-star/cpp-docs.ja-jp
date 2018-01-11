---
title: "コマンドラインの警告 D9043 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9043
dev_langs: C++
helpviewer_keywords: D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8986926db2c32d9ae5ca73517c74ae9625e6bf5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9043"></a>コマンド ラインの警告 D9043
無効な値 'warning_level' の 'compiler_option';'4999;' と仮定した場合コード分析の警告が警告レベルと関連付けられていません。  
  
## <a name="example"></a>例  
 次の例では、c9043 エラーを生成します。  
  
```  
// D9043.cpp  
// compile with: /analyze /w16001  
// D9043 warning expected  
int main() {}  
```