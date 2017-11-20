---
title: "アクセラレータの修飾子 プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d54c131af740c9c2248c4d923176b0a5c55d9e33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="accelerator-modifier-property"></a>アクセラレータの [修飾子] プロパティ
アクセラレータ テーブルの [修飾子] プロパティに有効なエントリを次に示します。  
  
|値|説明|  
|-----------|-----------------|  
|**None**|ユーザーは、キー値のみを押します。 これが最も効果的の値と共に使用 ASCII/ANSI 001 026、を通じてとして解釈される ^ A ~ ^ Z (ctrl キーを押し、A ~ Z ctrl キーを押し)。|  
|**Alt キー**|ユーザーは、キー値の前に ALT キーを押す必要があります。|  
|**Ctrl キー**|ユーザーは、キー値の前に、CTRL キーを押す必要があります。 ASCII 型では無効です。|  
|**Shift キー**|ユーザーは、キー値の前に、SHIFT キーを押す必要があります。|  
|**Ctrl + Alt**|ユーザーには、CTRL キーとキー値の前に ALT キーを押す必要があります。 ASCII 型では無効です。|  
|**Ctrl + Shift**|ユーザーには、CTRL キーとキー値の前に、SHIFT キーを押す必要があります。 ASCII 型では無効です。|  
|**Alt + Shift**|ユーザーには、ALT キーとキー値の前に、SHIFT キーを押す必要があります。 ASCII 型では無効です。|  
|**Ctrl + Alt + Shift**|ユーザーは、キー値の前に ctrl キーを押し、alt キーと shift キーを押す必要があります。 ASCII 型では無効です。|  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)