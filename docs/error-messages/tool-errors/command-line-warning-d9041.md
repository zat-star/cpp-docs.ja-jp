---
title: "コマンドラインの警告 D9041 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9041
dev_langs: C++
helpviewer_keywords: D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9f80de8e9bbbf7c754ac8e13061ef3ae50c4715a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>関連項目  
 [コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)