---
title: "コマンドラインの警告 D9041 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 307d290bb525ee879f29853c6823d5b9565aba4b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9041"></a>コマンド ラインの警告 D9041
無効な値 'value' の '/option';'value'; と仮定した場合追加 '/analyze ' をこの警告を指定するときのコマンド ライン オプション  
  
 コード分析の警告番号が追加、 **/wd**、 **/we**、 **/wo**、または**/wl** を指定せずにコマンドラインオプション**/analyze**コマンド ライン オプションです。 このエラーを解決するを追加するか、 **/analyze**コマンド ライン オプション、または、適切なから無効な警告番号を削除する**/w**コマンド ライン オプションです。  
  
## <a name="example"></a>例  
 次のコマンドラインの例では、警告 D9041 が生成されます。  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 この警告を解決するには、するには追加、 **/analyze**コマンド ライン オプションです。 場合**/analyze**はから無効な警告番号を削除するコンパイラのバージョンでサポートされていない、 **/wd**オプション。  
  
## <a name="see-also"></a>参照  
 [コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)