---
title: "コマンドラインの警告 D9043 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9043
dev_langs:
- C++
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4d9ad9941b7ec0f4935ec6bac02fc62f13e662f3
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="command-line-warning-d9043"></a>コマンド ラインの警告 D9043
無効な値 'warning_level' の 'compiler_option';'4999;' と仮定した場合コード分析の警告が警告レベルに関連付けられていません。  
  
## <a name="example"></a>例  
 次の例では、c9043 エラーを生成します。  
  
```  
// D9043.cpp  
// compile with: /analyze /w16001  
// D9043 warning expected  
int main() {}  
```
