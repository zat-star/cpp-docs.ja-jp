---
title: "ATL OLEDB コンシューマーの追加 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL OLE DB コンシューマー"
  - "ATL プロジェクト, 追加 (ATL OLE DB コンシューマーを)"
  - "OLE DB, 追加 (ATL OLE DB コンシューマーをプロジェクトに)"
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# ATL OLEDB コンシューマーの追加
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このウィザードを使用して、ATL OLEDB コンシューマーをプロジェクトに追加します。  ATL OLEDB コンシューマーは、OLEDB アクセサー クラス、およびデータ ソースにアクセスするために必要なデータ連結で構成されます。  ATL COM アプリケーション、または、ATL サポートを含む MFC アプリケーションや Win32 アプリケーションとしてプロジェクトを作成しておく必要があります。ATL サポートは、ATL OLE DB コンシューマー ウィザードを使用すると自動的に追加されます。  
  
 **Note** MFC プロジェクトに OLE DB コンシューマーを追加できます。  その場合、ATL OLE DB コンシューマー ウィザードは必要な COM サポートをプロジェクトに追加します。  ここでは、MFC プロジェクトを作成したときに、MFC アプリケーション ウィザードの **\[高度な機能\]** ページで **\[ActiveX コントロール\]** チェック ボックスをオンにしていることを前提としています。このチェック ボックスは既定でオンになっています。  このオプションをオンにすると、アプリケーションで **CoInitialize** と **CoUninitialize** が必ず呼び出されます。  MFC プロジェクトを作成したときに **\[ActiveX コントロール\]** チェック ボックスをオンにしなかった場合は、メイン コードで **CoInitialize** と **CoUninitialize** を呼び出す必要があります。  
  
### プロジェクトに ATL OLEDB コンシューマーを追加するには  
  
1.  クラス ビューでプロジェクトを右クリックします。  ショートカット メニューの \[追加\] をポイントし、\[クラスの追加\] をクリックします。  
  
2.  \[Visual C\+\+\] フォルダーの \[ATL OLEDB コンシューマー\] アイコンをダブルクリックするか、またはそのアイコンを選択して \[開く\] をクリックします。  
  
     ATL OLEDB コンシューマー ウィザードが開きます。  
  
3.  「[ATL OLEDB コンシューマー ウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)」の説明に従って設定を定義します。  
  
4.  **\[完了\]** をクリックして、ウィザードを閉じます。  新規作成された OLEDB コンシューマー コードがプロジェクトに追加されます。  
  
## 参照  
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)