---
title: "ツール バー ボタン プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons (in Toolbar editor), setting properties
- Toolbar editor, toolbar button properties
- status bars, active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 98c78922ee3987bf459f01a62253e9835ad3e377
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="toolbar-button-properties"></a>ツール バー ボタンのプロパティ
ツール バー ボタンのプロパティは次のとおりです。  
  
|プロパティ|説明|  
|--------------|-----------------|  
|**ID**|ボタンの ID を定義します。 ボックスの一覧は、一般的な**ID**名。|  
|**幅**|ボタンの幅を設定します。 16 ピクセルをお勧めします。|  
|**高さ**|ボタンの高さを設定します。 1 つのボタンの高さがツールバーのすべてのボタンの高さを変更することに注意してください。 15 ピクセルをお勧めします。|  
|**プロンプト**|ステータス バーに表示されるメッセージを定義します。 \N と名を追加すると、そのツール バー ボタンにツールヒントが追加されます。 詳細については、次を参照してください。[ツールヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)です。|  
  
 **幅**と**高さ**のすべてのボタンに適用します。 ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 これを 512 ボタンの幅を設定する場合は、4 つのボタンをのみ持つことができ、513 幅を設定する場合は、3 つのボタンをのみ持つことができます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](https://msdn.microsoft.com/library/f45fce5x.aspx)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](https://msdn.microsoft.com/library/xbx3z216.aspx)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](https://msdn.microsoft.com/library/h6270d0z.aspx)です。  
  
## <a name="requirements"></a>要件  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [ツール バー ボタンのプロパティの変更](../windows/changing-the-properties-of-a-toolbar-button.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)

