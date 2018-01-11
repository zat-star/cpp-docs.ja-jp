---
title: "リンカ ツール エラー LNK2039 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2039
dev_langs: C++
helpviewer_keywords: LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 441765d85ce65a80102ed94b3f4394ae48c0e29f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2039"></a>リンカ ツール エラー LNK2039
ref クラスをインポートする\<型 >' another.obj で定義されている以外の場合は、インポートまたは定義されており、両方は使用できませんである必要があります  
  
 Ref クラス ' <`type`>' は、指定された .obj ファイルにインポートしますが、別の .obj ファイルにも定義されています。 この条件の実行時エラーまたはその他の予期しない動作が発生することができます。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  確認するかどうか '`type`'、その他の .obj ファイルで定義する必要があります、.winmd ファイルからインポートする必要があるかどうかを確認します。  
  
2.  定義と、インポートのいずれかを削除します。  
  
## <a name="see-also"></a>参照  
 [リンカ ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [リンカー ツール エラー LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)