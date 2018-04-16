---
title: "プロバイダーの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5521215560c84c19f7b661f0c9662752374b68e4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="creating-the-provider"></a>プロバイダーの作成
#### <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>ATL OLE DB プロバイダー ウィザードを使用して、OLE DB プロバイダーを作成するには  
  
1.  プロジェクトで右クリックします。  
  
2.  ショートカット メニューをクリックして**追加**、クリックして**クラスの追加**です。  
  
3.  **クラスの追加**ダイアログ ボックスで、 **ATL OLE DB プロバイダー**アイコンをクリックして**開く**です。  
  
4.  ATL OLE DB プロバイダー ウィザードで、入力で、プロバイダーの短い名前、**短い名前**ボックス。 次のトピックでは、短い名前"MyProvider"を使用するが、別の名前を使用することができます。 他の名前のボックスは、入力した名前に基づいて設定します。  
  
5.  必要な場合は、また、他の名前を編集します。 だけでなく、オブジェクト名とファイル名には、次の操作を行うことができます。  
  
    -   **コクラス**: COM を使用して、プロバイダーを作成する名前。  
  
    -   **ProgID**: GUID の代わりに使用できるテキスト文字列であるプログラムの識別子。  
  
    -   **バージョン**: ProgID およびコクラスでバージョンに依存するプログラムで ID を生成するために使用  
  
6.  **[完了]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)