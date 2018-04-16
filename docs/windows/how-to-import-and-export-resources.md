---
title: "方法: インポートおよびエクスポートのリソース |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.resvw.resource.importing
- vc.resvw.resource.importing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [Visual Studio], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a01269928d0e5b52cca6e2301ad681db61289f80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-import-and-export-resources"></a>方法: リソースをインポートおよびエクスポートする
グラフィカル リソース (ビットマップ、アイコン、カーソル、ツール バー)、HTML ファイル、および Visual C++ で使用するためのカスタム リソースをインポートすることができます。 Visual C++ プロジェクトから、同じ種類のファイルを別のファイルにエクスポートして、開発環境の外部で使用することができます。  
  
> [!NOTE]
>  アクセラレータ、ダイアログ ボックス、文字列テーブルなどのリソースの種類は、スタンドアロンのファイルの種類ではないため、インポートまたはエクスポートすることはできません。  
  
### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>1 つのリソースを現在のリソース ファイルにインポートするには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)、リソース スクリプトのノードを右クリックし (* .rc) ファイル、リソースを追加します。  
  
2.  をクリックして**インポート**ショートカット メニューの します。  
  
3.  インポートするビットマップ (.bmp)、アイコン (.ico)、カーソル (.cur)、Html ファイル (.htm)、またはその他のファイルを見つけてそのファイル名を選択します。  
  
4.  をクリックして**OK**で選択したファイルにリソースを追加する**リソース**ビュー。  
  
    > [!NOTE]
    >  どの種類のリソースを選択した場合も、インポート プロセスは同じように実行されます。 インポートされたリソースは、そのリソースの種類の適切なノードに自動的に追加されます。  
  
### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>(Visual C++ の外部で使用するために) ビットマップ、アイコン、またはカーソルを別のファイルとしてエクスポートするには  
  
1.  **リソース**ビューで、エクスポートするリソースを右クリックします。  
  
2.  をクリックして**エクスポート**ショートカット メニューの します。  
  
3.  **リソースのエクスポート** ダイアログ ボックスで、現在のファイル名をそのまま使用するか、新しい名前を入力します。  
  
4.  ファイルを保存し、をクリックする場所のフォルダーに移動**エクスポート**です。  
  

  
 必要条件  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)