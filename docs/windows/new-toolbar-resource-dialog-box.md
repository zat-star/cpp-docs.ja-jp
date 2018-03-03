---
title: "[新規ツールバー] ダイアログ ボックス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.newtoolbarresource
dev_langs:
- C++
helpviewer_keywords:
- New Toolbar Resource dialog box
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c30301b8887013d72e7ae2ab2d70650de7d7f0e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="new-toolbar-resource-dialog-box"></a>[新規ツール バー リソース] ダイアログ ボックス
新規ツールバー ダイアログ ボックスでは、ツール バー リソースを追加するボタンの高さと幅を指定することができます。 既定値は、16 × 15 ピクセルです。  
  
 ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 設定した場合は、**ボタンの幅**512 には、4 つのボタンのみ持つことができます。 513 幅を設定する場合は、3 つのボタンだけができます。  
  
 **ボタンの幅**  
 ビットマップ リソースからツール バー リソースへの変換ツール バー ボタンの幅を入力する場所を提供します。 イメージのトリミングは幅と高さを指定して、標準ツールバーの色 (16 色) を使用する色を調整します。  
  
 **ボタンの高さ**  
 ビットマップ リソースからツール バー リソースへの変換ツール バー ボタンの高さを入力する場所を提供します。 イメージのトリミングは幅と高さを指定して、標準ツールバーの色 (16 色) を使用する色を調整します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>必要条件  
 MFC または ATL  
  
## <a name="see-also"></a>参照  
 [ツール バー ボタン プロパティ](../windows/toolbar-button-properties.md)   
 [ビットマップ ツールバーからへの変換](../windows/converting-bitmaps-to-toolbars.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)

