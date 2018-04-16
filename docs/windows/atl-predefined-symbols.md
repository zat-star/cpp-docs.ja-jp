---
title: "ATL の定義済みシンボル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- symbols, ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d56fcfa8fb65f183acfe96c3981023d06f5e524a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-predefined-symbols"></a>ATL の定義済みシンボル
ATL ヘッダー ファイルでこれらのシンボルが定義されているが、標準の Windows アプリケーションの関数とアクションをサポートします。 これらのシンボルは、ダイアログ ボックスで主に使用されます。 ダイアログ ボックス コントロールで作業しているときに、[ダイアログ エディター](../windows/dialog-editor.md)、コモン コントロールに関連付けられたプロパティ ウィンドウでこれらのシンボルが表示されます。 たとえば、ダイアログ ボックスに [キャンセル] ボタンがある場合は、そのコマンドに関連付けられるシンボル IDCANCEL で、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
|||  
|-|-|  
|IDABORT|コントロール: ダイアログ ボックスの 中止 ボタン|  
|IDC_STATIC|Control: 静的コントロール|  
|IDCANCEL|コントロール: ダイアログ ボックスの キャンセル ボタン|  
|IDIGNORE|コントロール: ダイアログ ボックス 無視 ボタン|  
|IDNO|制御: ダイアログ ボックスがないボタン|  
|IDOK|コントロール: ダイアログ ボックスの OK ボタン|  
|IDR_ACCELERATOR1|リソース: アクセラレータ テーブル|  
|IDRETRY|コントロール: ダイアログ ボックスの 再試行|  
|IDS_PROJNAME|現在のアプリケーション名を文字列:|  
|IDYES|コントロール: ダイアログ ボックスの はい ボタンします。|  
  
## <a name="requirements"></a>必要条件  
 ATL  
  
## <a name="see-also"></a>参照  
 [定義済みシンボル Id](../windows/predefined-symbol-ids.md)   
 [シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)