---
title: "ATL OLE DB コンシューマーの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: defc933014bd287eb48f53635efba12a40960711
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-ole-db-consumer"></a>ATL OLE DB コンシューマーの追加
このウィザードを使用すると、プロジェクトに ATL OLE DB コンシューマーを追加します。 ATL OLE DB コンシューマーは、OLE DB アクセサー クラスとデータ バインディングのデータ ソースにアクセスするために必要なので構成されます。 プロジェクトは、ATL COM アプリケーションまたは ATL のサポート (ATL OLE DB コンシューマー ウィザードが自動的に追加します) を含む MFC または Win32 アプリケーションとして作成されていなければなりません。  
  
 **注**MFC プロジェクトに、OLE DB コンシューマーを追加することができます。 作成する場合は、ATL OLE DB コンシューマー ウィザードは、プロジェクトに必要な COM サポートを追加します。 これは、MFC プロジェクトを作成したときに、選択されていることを前提としています、 **ActiveX コントロール** チェック ボックスを (で、**高度な機能**MFC アプリケーション ウィザードのページ)、これは既定でオンです。 アプリケーションを呼び出すことにより、このオプションを選択する**CoInitialize**と**CoUninitialize**です。 選択しなかった場合**ActiveX コントロール**MFC プロジェクトを作成したときに呼び出す必要がある**CoInitialize**と**CoUninitialize**メイン コードにします。  
  
### <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>プロジェクトに ATL OLE DB コンシューマーを追加するには  
  
1.  クラス ビュー で、プロジェクトを右クリックします。 ショートカット メニューをクリックして**追加** をクリックし、**クラスの追加**です。  
  
2.  Visual C フォルダーをダブルクリックして、 **ATL OLE DB コンシューマー**アイコンまたは選択し、をクリックして**開く**です。  
  
     ATL OLE DB コンシューマー ウィザードが開きます。  
  
3.  」の説明に従って設定を定義する[ATL OLE DB コンシューマー ウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)です。  
  
4.  をクリックして**完了**ウィザードを閉じます。 プロジェクトで、新しく作成された OLE DB コンシューマー コードが挿入されます。  
  
## <a name="see-also"></a>参照  
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)

